# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p01 0_数据科学导论.zh_en -BV1r483zbEzN_p1-

![](img/4579c7e40ba9b72032c671aac97a01cd_0.png)

Hello， I'm Dr。 Amy McCum， and I want to take a couple minutes to talk to you about data science。



![](img/4579c7e40ba9b72032c671aac97a01cd_2.png)

Now data science is a term that's widely used， I think the general accepted definition is you are informing decision making with data。



![](img/4579c7e40ba9b72032c671aac97a01cd_4.png)

Well， from that perspective， if you look at the price of gas。

Before you decide which gas station to pull into you're applying data science and I don't think that's what we really mean。

 so I would like to just offer my own opinion on what kind of the essential elements of what data science is when we're referring to that in probably the consulting space in government contracting in the commercial sector。



![](img/4579c7e40ba9b72032c671aac97a01cd_6.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_7.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_8.png)

So I think there are three elements to data science。

 I think the first element is a foundation in probability。



![](img/4579c7e40ba9b72032c671aac97a01cd_10.png)

And statistics。

![](img/4579c7e40ba9b72032c671aac97a01cd_12.png)

Hopefully what you've learned in this course so far is that understanding some basics about probability。

 how do we do counting， how do we represent numbers on a number line。

 what is a distribution function， what's a density。

 how does that inform our understanding of creating limitations to probability for limits to probability for rare events？

How do we then move that into statistical hypothesis testing， How do we do simulation。

 How do we do regression， right， all of these things， you know and regression is basically a model。

 all of these things are based on an understanding of probability and statistics。 So yes。

 while you can go and make a decision as to which gas station you want to go to based on the price of gas。



![](img/4579c7e40ba9b72032c671aac97a01cd_14.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_15.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_16.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_17.png)

Anyth more sophisticated than that， whatcon of requires you to understand numbers and understand it not just from the perspective of calculus。

 but from probability and statistics， so you know what the risk of future observations are going to be or you can make inference or you can make models or you can do things to kind of have a better understanding of the impact of your decisions with data。

 so I would say the first requirement for data science is probability in statistics。



![](img/4579c7e40ba9b72032c671aac97a01cd_19.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_20.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_21.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_22.png)

The second criteria that I would argue goes into data science is。



![](img/4579c7e40ba9b72032c671aac97a01cd_24.png)

Coding。

![](img/4579c7e40ba9b72032c671aac97a01cd_26.png)

Or maybe you call it scripting。Maybe you call it programming。

And what I would argue is that what's most common is R。



![](img/4579c7e40ba9b72032c671aac97a01cd_28.png)

And Python。

![](img/4579c7e40ba9b72032c671aac97a01cd_30.png)

Now R is a statistical computing language so you'll probably find that there's more available packages for more sophisticated things to do in statistics with R for example I do social network analysis if you want to do statistical analysis of networks at least today as of the recording of this video you really need to do that in R that's where the packages are that's where the tools are Python has some additional features in terms of web scraping in terms of ways you can manipulate data structures and so has some advantages as well。

 I would also argue that Python is far more common right now and that's the trend that's growing but either one。

 I think once you learn R， you can pick up Python or vice versa people tend to like kind of get stuck in that language why is that important Well it's important to give you the power to actually do something with the probability and statistics and to do something on your own if you go and buy an expensive statistical programming software license you have to learn that user interface。



![](img/4579c7e40ba9b72032c671aac97a01cd_32.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_33.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_34.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_35.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_36.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_37.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_38.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_39.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_40.png)

You have to know how to use it to conduct whatever tests you're choosing to do so you have less flexibility those software licenses are usually cost prohibited for you as an individual practitioner so maybe if you're working for a company or a university or something like that they have those licenses but R and Python are free and I like to say free is a very good price it also is more up to dateate because as you as you go and somebody comes up with a new method or a new package or new feature they're instantly available so I'll give you an example with networks we can look at a dependent network right here's a social network and is that a function statistically of relationships people have or demographics people have or locations they have right that's called we use an exponential random graph model it's an extension regression to do that。



![](img/4579c7e40ba9b72032c671aac97a01cd_42.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_43.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_44.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_45.png)

Well there's a new package that came out a couple years ago called stochastic T exponentialial random graph models well that package wasn't available in your most advanced statistical software tools。

 it's a package though that's available in R if you download it to your computer。

 you can get that today。

![](img/4579c7e40ba9b72032c671aac97a01cd_47.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_48.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_49.png)

As with all of the other exponential random graph model features and functionality that are not in any professional licensed statistical software that I'm aware of。

Okay so having that ability to code script， programming and R Python。

 I would argue is an important skill set that you need to have as a data scientist。

 and so the more proficiency you get in one or both， the better。



![](img/4579c7e40ba9b72032c671aac97a01cd_51.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_52.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_53.png)

The third component is the science。

![](img/4579c7e40ba9b72032c671aac97a01cd_55.png)

What is the science in data science， right？ It's not just run numbers， right？

 It's understanding a scientific process for gaining insights。

 And that's what I'm going to spend the rest of this video talking about。

 But I just want to make the point that if we agree on these three features， these three functions。



![](img/4579c7e40ba9b72032c671aac97a01cd_57.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_58.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_59.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_60.png)

It's important that any data scientist has a firm foundation and probability in statistics。

 they have some proficiency in programming， and they understand methodology。



![](img/4579c7e40ba9b72032c671aac97a01cd_62.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_63.png)

So what methodology should we use to frame these problems， Well， I'm going to give you an acronym。

 I'm going to give you the road。

![](img/4579c7e40ba9b72032c671aac97a01cd_65.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_66.png)

To success， ROAD， what does that mean？

![](img/4579c7e40ba9b72032c671aac97a01cd_68.png)

Well， that is requirement。

![](img/4579c7e40ba9b72032c671aac97a01cd_70.png)

Or research question。

![](img/4579c7e40ba9b72032c671aac97a01cd_72.png)

So。

![](img/4579c7e40ba9b72032c671aac97a01cd_74.png)

Let's just give you something notional like。I'm interested in a understanding how tariffs。



![](img/4579c7e40ba9b72032c671aac97a01cd_76.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_77.png)

Impact。Agriculture trade。

![](img/4579c7e40ba9b72032c671aac97a01cd_79.png)

Right so you know at the time that I'm recording this video。

 there was a bunch of controversy over Donald Trump's trade war with China and the impact it was going to have on agricultural prices。

 so he imposed a 10% tariff and he was threatening to increase that tariff to 25%。

 I'm not being political here I'm just stating the facts and I really don't have any political bias either way。



![](img/4579c7e40ba9b72032c671aac97a01cd_81.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_82.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_83.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_84.png)

From a data driven approach， right？We can observe people on both parties。

 whether you're Republican or Democrat and supporters of Trump tariffs are going to say， well yeah。

 we need to draw a hard line with China because we need to negotiate a better position。

 there's trade imbalance， et et ceter。're all numbers all being supported and then the people that are opposing it say。

 hey know if we look through history， tariffs haven't been good。

 they've all been bad we see that you farmers are going to be hurting because as the costs go up。

 the amount of exports to China are going to go down eta。

 et et cea right so my point is that when you look at the debate。

 the debate people are arguing based on opinions， and there's an assumption。

 one assumption is that that the tariffs are going to increase costs and cost farmers money。

 the other assumption is that it's going to bring them to negotiations and it's going to have a better impact and that maybe other markets are going to open up and and create opportunities for these farmers and it's going to be awa。



![](img/4579c7e40ba9b72032c671aac97a01cd_86.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_87.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_88.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_89.png)

But neither of those parties have the data。And so if you can identify what is the point of disagreement with two opposing parties or what are the two decisions and the tradeoffs between them。

 if you can isolate， well what is the requirement， what is the research a question that kind of gets at that decision you're trying to make。

 you have to define that first， that's the first step， that is the research question。



![](img/4579c7e40ba9b72032c671aac97a01cd_91.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_92.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_93.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_94.png)

Okay。Well， it's not clear that I can just go and grab some magical data source and tell you what the tariffs are doing。

 The next step is I have to operationalize， operationalize。



![](img/4579c7e40ba9b72032c671aac97a01cd_96.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_97.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_98.png)

With data。There's no perfect data source， there's never a perfect data source。



![](img/4579c7e40ba9b72032c671aac97a01cd_100.png)

So what I have to do is I have to make some assumptions as far as what's the valid data。



![](img/4579c7e40ba9b72032c671aac97a01cd_102.png)

Maybe I go to data。gov。

![](img/4579c7e40ba9b72032c671aac97a01cd_104.png)

And I look at some data， maybe I don't have， or maybe it's too costly to look at all agriculture trade。

 so I might just look at soy because soy exports is one of the larger agriculture goods that is then exported to China。



![](img/4579c7e40ba9b72032c671aac97a01cd_106.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_107.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_108.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_109.png)

Maybe I don't have it at the farmer to farmer level。

 so maybe I'm going to look at aggregate data across the US。

 maybe I'm going to just look at California and say you know， California is close to China。

 let me just use California as a proxy for all of America now。



![](img/4579c7e40ba9b72032c671aac97a01cd_111.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_112.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_113.png)

I'm not making a judgment as whether that's right or wrong。

 What you're going to find is regardless of whatever decision you make to operationalize data。

If you go and show a person that has position，'re like， I don't want to go Republican Democrat。

 but there's position A and position B， right， if you go and show somebody that believes in position A。



![](img/4579c7e40ba9b72032c671aac97a01cd_115.png)

Of finding the supports position B， what's the first thing they're going to do？

I'm can go right there， and they can say that wasn't a good data source。

 doesn't matter if it's a good data source。Doesn't matter if they would have agree to it before。

 at the point where you're finished with the analysis。

 they're going to come here and they're going to say。

 I question your assumptions just because it doesn't conform to what they preconceived。



![](img/4579c7e40ba9b72032c671aac97a01cd_117.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_118.png)

And that's just human nature。So what I'm saying is when you define the requirement of the research question。

 you need to operationalize with the data and ideally whoever your client is。

 you get them to agree that that is in fact the research question we should be answering。



![](img/4579c7e40ba9b72032c671aac97a01cd_120.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_121.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_122.png)

And that is a viable data source before they ever see a conclusion。



![](img/4579c7e40ba9b72032c671aac97a01cd_124.png)

Okay。Once you've identified the problem and the data source。

 now it becomes fairly simple to identify the analysis。



![](img/4579c7e40ba9b72032c671aac97a01cd_126.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_127.png)

Method。

![](img/4579c7e40ba9b72032c671aac97a01cd_129.png)

Now， sophisticated doesn't necessarily matter at this point， right sometimes visual。



![](img/4579c7e40ba9b72032c671aac97a01cd_131.png)

Exploration is perfectly good you know I did a project where know there was an organization that had teams and they were basically responding to certain types of events or crises they were like know there would be an incident on a given location in the client site and so the team would have to like get alerted and they'd have to go out there and do whatever it is they did in respond to the crisis so depending on the type of mission there was a planned level of time that that mission was supposed to take and then of course they would record data on how long it actually took the team to do that and so I simply made a scatter plot of the plan versus the actual and you would tend to see that that was correlated but then I looked at the residuals and I highlighted the residuals with red dots and so you could kind of see hey these teams were taking two standard deviations more than we expected these teams were doing in half the time as expected and and that was just simply the question was is there any。



![](img/4579c7e40ba9b72032c671aac97a01cd_133.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_134.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_135.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_136.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_137.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_138.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_139.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_140.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_141.png)

Degregation or problems in the teams。

![](img/4579c7e40ba9b72032c671aac97a01cd_143.png)

We were operationalizing it with planned and actual times because that was fairly easy to collect The analysis method was visual and the decision point was where should the leader of the overall of all the teams。

 where should they focus their leader attention， their executive attention。

 do they focus it on maybe teams that are taking longer to perform to say， hey。

 what was going on in this mission， they could then select the missions and say， hey。

 why this take longer， did you use a new tool was there a personnel turn， what are the insights。

 that's where you're more likely to find problems and the ones that were half the time。

 that's where you might find successes that you can capitalize and extend to the rest of the organization So that's an example of a data science drivenriven insight。



![](img/4579c7e40ba9b72032c671aac97a01cd_145.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_146.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_147.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_148.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_149.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_150.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_151.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_152.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_153.png)

And there was no advanced statistics， it was very simple visual。

 but you might use other things right， like maybe you have to do a hypothesis test。



![](img/4579c7e40ba9b72032c671aac97a01cd_155.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_156.png)

Or regression。

![](img/4579c7e40ba9b72032c671aac97a01cd_158.png)

That's probably the limit of most people doing basic statistics。

 but then maybe you get a little more sophisticated and you start doing machine learning。

 computer vision， natural language processing， graph。



![](img/4579c7e40ba9b72032c671aac97a01cd_160.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_161.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_162.png)

Analytics。And what you'll find in most data science master's programs is there's going to be some sort of foundational course in like probability and statistics and they might introduce you to artificial intelligence or machine learning they might give you some awareness of data engineering or cloud platforms or something like that just so you kind of better understand this step in the scientific process。

 but beyond that foundation then you're going to see many electives which basically are arming you with different unique analytic methods right。



![](img/4579c7e40ba9b72032c671aac97a01cd_164.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_165.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_166.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_167.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_168.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_169.png)

So analysis methods， but it doesn't mean that the better the method or the more sorry。

 the more sophisticated the method， the better it is。

 the best method is the one that most clearly answers the research question with the available data。



![](img/4579c7e40ba9b72032c671aac97a01cd_171.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_172.png)

The last step in our road to success is the decision。



![](img/4579c7e40ba9b72032c671aac97a01cd_174.png)

Right what is the decision to be made now， usually when I'm working with clients and I start going through this and I get to what decision are you going to make with the data。

 I get a deer in the headlights look， what do you mean what decision am I going to make？



![](img/4579c7e40ba9b72032c671aac97a01cd_176.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_177.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_178.png)

Well， why are we doing this？Why， why do you care about this research question。

 Hopefully it's to solve a problem， right， If I'm going through this process on this issue of of tariffs and how they impact trade。

 hopefully I'm coming down to a decision as to do we go with a 25% tariff。

 Do we hold off on the 25% tariff and keep it at 10%， Do we lift the 10% tariff， right？

 Those are kind of decisions and at decision space， we want to define。



![](img/4579c7e40ba9b72032c671aac97a01cd_180.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_181.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_182.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_183.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_184.png)

All of this， in advance of doing a single thing analytically。

 we don't want to collect a single data point， I don't want to waste any of my time until that is laid out。

 why。

![](img/4579c7e40ba9b72032c671aac97a01cd_186.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_187.png)

We'll find that when you actually pin somebody down on the decision。

 they might find they have no ability to make a decision。

 so why are they going to invest in the time and resources to go through this process or。



![](img/4579c7e40ba9b72032c671aac97a01cd_189.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_190.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_191.png)

Maybe they haven't fully thought through that decision， and if you identify what the decision is。

 it might revise what the requirements are。

![](img/4579c7e40ba9b72032c671aac97a01cd_193.png)

It might revise what data we need to use in order to convince decision makers。

And so that is why that road to success is a very important first step before you go at any process。

 and it follows the scientific process。 If you look at the scientific process。

 it's observe the world around you。

![](img/4579c7e40ba9b72032c671aac97a01cd_195.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_196.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_197.png)

For a hypothesis。

![](img/4579c7e40ba9b72032c671aac97a01cd_199.png)

For collect some data。Conduct your analysis。

![](img/4579c7e40ba9b72032c671aac97a01cd_201.png)

And then draw your insights。That's essentially what we're doing with the scientific process。



![](img/4579c7e40ba9b72032c671aac97a01cd_203.png)

I would argue to just focus that more for data science， if we want to have the science。

 you need to have your road to success。

![](img/4579c7e40ba9b72032c671aac97a01cd_205.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_206.png)

Now there's one caveat。The road to success is very much focused on decision making。



![](img/4579c7e40ba9b72032c671aac97a01cd_208.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_209.png)

Decision support。And I would argue that that is the number one application of what people mean or what they're asking for when they want data science。



![](img/4579c7e40ba9b72032c671aac97a01cd_211.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_212.png)

But there is one other type of data science that I think is worth discussing briefly， and that is。



![](img/4579c7e40ba9b72032c671aac97a01cd_214.png)

Reporting。

![](img/4579c7e40ba9b72032c671aac97a01cd_216.png)

Right， so what is reporting Well， let's say I'm trying to tackle a problem and I don't really understand what's going on。

 I don't know what the state of the variables are。 I don't know what's happening like I have a human resource system and in the human resource system the enterprise resource planning tool that I have is out there it captures a whole bunch of variables on employees a variety of companies have defined found useful some more than others right and so there's a whole bunch of data out there so I may want to do data visualization of what those variables are。

 I may want to search for patterns in those variables right and that's not I don't have an intended research question I don't have the set of data set that I'm looking for I don't know what method analysis I have no decisions that I'm trying to make what I'm doing is I'm looking for patterns I'm looking for for relationships in these sorts of things and that's reporting I'm just trying to visualize the data。



![](img/4579c7e40ba9b72032c671aac97a01cd_218.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_219.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_220.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_221.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_222.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_223.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_224.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_225.png)

So that I can inform a road， but I'm not going to make decisions off of just a random dashboard of data points。

 I'm using that to kind of shape my understanding to be able to plan a road to success another value of reporting is going to be there's mandatory oversight so like in federal government for example。

 when Congress sends out funding for various programs they have an oversight where where those agencies then have to report data back to Congress and maybe that data is not necessary to inform the head of that agency on any decisions they're making on benefits to citizens or how they help people in the country but they do have to report how they're spending the money back to Congress right and so that's kind of informing some leadership even there's no decision involved。



![](img/4579c7e40ba9b72032c671aac97a01cd_227.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_228.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_229.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_230.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_231.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_232.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_233.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_234.png)

And then unfortunately I don't particularly like this。

 but sometimes clients are looking at reporting because they want to write a report card that says how awesome they are to their boss。

 and that's another use of data science that may me more common than not in many applications。



![](img/4579c7e40ba9b72032c671aac97a01cd_236.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_237.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_238.png)

Okay so just a recap when we're looking at data science right。

 we have a foundation of probability in statistics， we understand some programming， we apply science。

 what do I mean by science really the science is the road to success。

 you're able to identify a requirement operationalize with data。

 select a method of analysis that's appropriate， define what that decision is you implement that road to success in the planning phase before you collect a single data point do a single method of analysis。



![](img/4579c7e40ba9b72032c671aac97a01cd_240.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_241.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_242.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_243.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_244.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_245.png)

And you're using it to drive decision support。That's really what data science is。

 but you can use these same tools to answer reporting。

 which is a common ask of data scientists Thank you for listening。



![](img/4579c7e40ba9b72032c671aac97a01cd_247.png)

![](img/4579c7e40ba9b72032c671aac97a01cd_248.png)