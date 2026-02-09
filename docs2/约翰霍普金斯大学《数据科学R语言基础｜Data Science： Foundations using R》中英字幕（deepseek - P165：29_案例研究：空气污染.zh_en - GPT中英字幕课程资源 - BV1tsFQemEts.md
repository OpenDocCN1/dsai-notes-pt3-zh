# 约翰霍普金斯大学《数据科学R语言基础｜Data Science： Foundations using R》中英字幕（deepseek - P165：29_案例研究：空气污染.zh_en - GPT中英字幕课程资源 - BV1tsFQemEts

![](img/d26d3f6ee33d50e7bffd9462696efc69_0.png)

This reproducible research case study involves trying to identify the harmful elements of particulate matter air pollution so one thing that you have to understand is that when you look at air pollution in particular if you look at particulate matter pollution。

 the particles are just you can think of them as just dust that you inhale。

 but the dust is not just one monolithic piece of of dirt or soot。

 it's actually composed of many different chemical constituents。

 the metals inert things like salts and other kinds of components and so there's a thought that you know。

One possibility is that some subset of those constituents are the really harmful elements。

 and if we figure out which one of those subsets are harmful。

Then we can think about trying to regulate the sources that generate those chemical constituents now it's very hard to do this and the research involved in this area is still fairly preliminary。

 so there's a lot of interest in trying to identify the harmful chemical constituents of particulate matter because in theory that could lead us to targeting or tailoring things like regulations that can control the sources of air pollution that are the most harmful to human health。

PM is composed of many different chemical constituents and it's important to understand actually that the EPA or the environmental protection you can see monitors the chemical constituents of particulate matter and has been doing so since roughly 1999 or 2000 on a national basis and there's a general understanding that perhaps some of the components of PM might be more harmful than others。

 and if that were true。

![](img/d26d3f6ee33d50e7bffd9462696efc69_2.png)

And that would likely imply that some sources of particulate matter are more dangerous than others because some sources of particulate matter generate certain combinations of chemical constituents and some sources generate other accommodations of chemical constituents and so the idea is that if we can identify the particularly harmful chemical constituents of particulate matter。

 then that may lead us to strategies for to better strategies for controlling sources the sources of particulate matter。

 one thing that you need to understand is the way that particulate matter is regulated or controlled now is we just regulate the the total amount of particles in the air。

 without regard to where the of PM， what the sources of PM are or where they're coming from。

And we could so this strategy does improve public health because we know that particulate matter as a whole is harmful。

 but it doesn't perhaps lead to the most efficient strategy and the most helpful strategy in terms of public health because we don't control things with respect to toxic elements are which elements are the most toxic。



![](img/d26d3f6ee33d50e7bffd9462696efc69_4.png)

So I just want to talk about one particular study and one case study of this type of research and I'll talk a little bit more about how it relates to reproducibility in a few slides。

 but the basis of this case study is the national morbidity mortality and air pollution study or the NMP study and this was a national study of the shortterm health effects of ambient air pollution so this particular national study focused on particulate matter or PM10。

 so particles is less than 10 microns in diameter and ozone so for this lecture I'm just going to talk about PM10。

The health outcomes in the study were mortality from all causes and hospitalizations for cardiovascular and respiratory diseases。

 so I've got some links to some of the key publications from the NMP study and in this entire study was funded by the Health Effects Institute。



![](img/d26d3f6ee33d50e7bffd9462696efc69_6.png)

One of the interesting aspects of the NMps study was that it was one of the most reproducible air pollution studies ever conducted。

 and particularly the investigators in N， the original investigators in NMps decided to make the data and the results and the softwareftware code available through a website called the Internet based health and Air pollutionllution Surveance System or IHPS。

 and so on that website you can find the air pollution data， the weather data， the software。

 the results and many other things。On that can be downloaded for free。

Since the data have been made available to the public。

 many studies have been conducted based on this data that were independent of the original N mapps。

 and so one particular study counted over 67 publications based on the NMps data。

 and so the data and the code that had been made available to the public has served as an important testbed for methodological development in this area。



![](img/d26d3f6ee33d50e7bffd9462696efc69_8.png)

So one recent study that was published in the journal environmentalronal health Perspecs involved the cardiovascularcular effects of nickel and ambient air。

 so nickel is a common component of particulate matter it's a transition metal and it's thought to be very harmful and in particular cause cardiovascular types of effects and so this study they found strong evidence that nickel in particulate matter modified the short termm effect of PM10 across 60 US communities。

 so basically what this is saying is that what they found is that in communities where the particulate matter had a larger concentration of nickel in relative to other elements that those communities saw kind of worse health risks from PM10 than other communities that had kind of less nickel in them so the idea is so so to think the inference that one might draw from that is that nickel is a one or maybe the only toxic element in PM10 and if your particles are composed。

of more nickel， then they're going to be more harmful to you。

 So that's the evidence that they brought in this paper or part of the evidence that they brought in this paper。

When they looked at other chemical contitus of particular matter。

 it didn't seem to have the same kind of modifying effect。 so if you looked at， for example。

 two cities and where one city had much higher concentrations of sulfate， for example。

 that did not lead to greater health risks compared to a city that had lower concentrations of sulfate so the main one of the main modifying effects came from this nickel element and so the result was very attractive because it seemed to identify one or just a few elements that led to the kind higher health risk of PM10 and so almost like there was a single element that needed to be or just a very small number of elements that could be regulated or controlled and so there was so there was thought that perhaps this was too simple to be true。

嗯。So Francesco Diinci and myself and some colleagues decided to look at the data again and to see what was driving the association between PM10 risk and this nickel and another transition metal called theadium so we looked at the data。

 we reexamine the N mapps data and linked it with PM chemical constituent data and one particular thought that we had was that one of the cities in the US that has extremely high levels of nickel is New York City。

And so there's one possibility is that because New York City has such very high levels。

 would the results of such an analysis be driven by the high levels of nickel in New York City？

So here's a simple scatter plot on the X axis， we have the long-term average nickel concentrations in a community and on the y axis we have the essentially the risk。

 a percent the percent increase in mortality for a unit increase in particulate matter。

 so you can think of this as the particulate matter risk of mortality and one of the things that you might notice is that there does appear to be a correlation between long-term average nickel concentrations in a community and their PM risk in the sense that in the scatter plot。

 as you go to the right， there's the risk seems to increase a little bit。Now， on the other hand。

 one of the other things you might see in this plot is that there are some there appear to be some outliers in the on the right hand side of the plot。

 there are three or a few points that are。Very highly kind of skewed to the right and so one and it turns out that the three rightmost points are all counties in New York City。

 so New York City is composed of five counties and so the three that are kind of at the rightmost point of the plot are three counties in New York City。



![](img/d26d3f6ee33d50e7bffd9462696efc69_10.png)

So here's the regression line that you can fit to this data。

 it's a simple linear regression line and you can see that it's positively sloped indicating a positive correlation so that more nickel is associated with a greater risk of mortality from PM and in the original paper the regression line was statistically significant with the P value of less than 。

01 and so that's very interesting it would seem to imply that in communities with higher nickel concentrations you have greater risk of mortality。

However， if you just remove the kind of outlying points in particular the points that are in New York City。

 which has very high nickel levels， and you'd redo the regression line。

 you'll see that the blue line is what you get and one of the important things about those three points to the right is they're called high leverage points and so the regression line can be very sensitive to high leverage points and so just removing three of them out of this data can bring the regression line down a little bit so that you get the blue line and that it's no longer statistically significant in this case the P values is about 0。

31。And so one of the things that you can see is that just a few points can make a big difference when looking at a correlation like this。



![](img/d26d3f6ee33d50e7bffd9462696efc69_12.png)

Another analysis that we did is we went through and recomputed the slope of the regression line。

When you。When you removed an individual county or a community in this study。

 remember there were 60 communities in the original。

 So what we did is we just went through each and just redid the analysis by removing one community。

 just to see if there were any particular community that the analysis was sensitive to and you can see that all the black dots here represent the kind of slopes of the regression line when you remove a given community and because they're all kind of clustered around the same value。

 you can see that for the most part， the regression line is not sensitive to removing any individual community from the data。

 However， the red dot the red dot and line at the very bottom indicates the kind of slope estimate and the 95% confidence interval。

 when you remove New York and you can see that when you remove the community of New York the slope estimate goes down quite a bit and the confidence interval goes up gets quite a bit wider than all the other dots。

And so that's another indication that the slow estimateimate of that regression line is very sensitive to just having the data points from New York City in there。



![](img/d26d3f6ee33d50e7bffd9462696efc69_14.png)

So in this analysis that we published again in environmental health perspectives。

 there are a couple things that we learned， first of all， we did confirm。

 of course that New York does have very high levels of nickel and vanadium。

 much higher than pretty much any other US community。

 and that there's evidence of a positive relationship between nickel concentrations and PM risk。

 even if you remove the data from New York City， the relationship is still positive。

 however the strength of this relationship is highly sensitive to the observations from a single city。

 and so the idea is that the evidence that you can bring from the data is really dependent on just a few data points。

 and so it's important to realize that although we still see this positive association between nickel and PM risk of mortality the the key conclusion that you might draw from this re-analysis is that the strength of the evidence is perhaps not as strong as you would like due to the kind of very sensitive nature of the evidence to a single community。



![](img/d26d3f6ee33d50e7bffd9462696efc69_16.png)

![](img/d26d3f6ee33d50e7bffd9462696efc69_17.png)

So some of the lessons that we've learned from this case study are that is that the reproducibility of the NNap study from the very beginning。

 first of all， it allowed for the secondary now， the original secondary analysis to occur to investigate this novel hypothesis that nickel is a harmful chemical constituent of PM。

 and so that's very good and the idea that it allowed other people to explore new ideas and so the paper by Liman at all。

 is one example of such a kind of a secondary analysis， the reproducibility of the study of course。

 allowed critique of this new analysis and bring to the table additional new analysis that was published by Diinci at all。

And so one of the lessons that we learned from this paper of course。

 is that the original hypothesis that Nicholas harmfulm was not really invalidated。

 but merely that the evidence that was originally presented was perhaps not as strong as originally suggested and that more work needs to be done to investigate this hypothesis so one of the really important lessons learned from this case study is that you know reproducibility makes any scientific discussion much more informed and much more timely。

 you can see that in this case you know a hypothesis was proposed that nickel was a harmful element of PM people brought data to address the hypothesis they presented the evidence from the data other people another set of investigators took the same data tried to look at the hypothesis confirmed that there was a positive association but thought there was some weakness in the presentation of the evidence and the strength of the evidence and so there was a back and forth that was highly informed because everyone's using data and everyone'。



![](img/d26d3f6ee33d50e7bffd9462696efc69_19.png)

There's transparency in the analysis and people can see what others have done and so this is how science defaults。

 this is how ideas come forward， this is how good ideas come to light and bad ideas are kind of put to rest and that's how a good kind of scientific exchange and occurs in how science kind of moves forward moves forward so reproducibility is key so all this entire process because it makes the entire process informed and move in a timely manner that's transparent。

