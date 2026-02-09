# 约翰霍普金斯大学《数据科学R语言基础｜Data Science： Foundations using R》中英字幕（deepseek - P162：26_基于证据的数据分析第4部分.zh_en - GPT中英字幕课程资源 - BV1tsFQemEts

![](img/a85aaf0f832c0ce22314944383fe7096_0.png)

So the other question is who reproduces research and I think this is I don't know I'm not in this area of kind of genomics and computational biology I don't know how much this is an issue。

 but it's a big issue for me order for repro me to be effective in any way。

 someone has to do something right so if I just say I publish this paper and it's reproducible。

 that doesn't necessarily mean anything until you get your hands on someone gets their hands on the data of the code and looks at it and does something and maybe even reproduce。

So someone has to do something， you have to rerun the analysis。

Check the code whenever it tries of alternative approaches。

So I think and this is kind of in my sense， is kind of the analog of replication kind of inherited from that tradition。

 but the question of who is something and what is their goal。

 who is this someone and what are their goals is very important to think and the way I kind of characterize it is that there's kind of three different types of people who may want to reproduce your research so if you're the original investigator over here。

 you say that the truth is a。

![](img/a85aaf0f832c0ce22314944383fe7096_2.png)

There's one group the general public which it doesn't care。That's some。

So that's the largest group of people。Then there's white scientists who either agree with you。

 maybe that they agree that they think the truth is A， also but they may think the truth is B。

 okay so that's fine。Everyone's got a hypothesis about how the world works。

And then it's just people over here， which believes that the truth is just whatever because it's not whatever you're saying。

And。sizeize the boxes， it's proportional to kind the likelihood that the people in that box will reproduce your work。

Scientists， I think are likely to reproduce it but they're kind of busy doing the wrong thing。

So there's an issue here which is that this， in my opinion， is not really science。

They don't have a specific idea of how the world works。

 they just want to know that it's different from whatever you're saying。

And so they are very interested in reproducing my work。

 Ive had it and thankfully my work's mostly been I mean almost all has been reproducible so I'm fine with that。

 but it can has the potential to make your personal life miserable。



![](img/a85aaf0f832c0ce22314944383fe7096_4.png)

So。So so far， my thinking is that so reprocing brings transparency， which is critical。

And it also increases the transfer of knowledge， there's a lot of discussion about how to get people to share data which is important。

 data sharing is key， obviously reproducibility， but I think the key question of can we trust this analysis that we see out there is not fundamentally addressed by reproducibility。

And so furthermore， reproducibility is this very downstream type of element。

 and a lot of these secondary types of analyses are colored by the interests and motivations of others and I still color the youth。



![](img/a85aaf0f832c0ce22314944383fe7096_6.png)

So that brings us to what I call evidencebased data analysis and so I think no one everyone here is familiar with the idea that you a true data analysis involves all stringing together a whole lot of things。

 lots of tools， lots of methods as this long pipeline of stuff that you have to do to do any real data analysis and so a lot of times the methods are standard。

 know everyone does the same thing for a given piece of the pipeline or there's no standard。

 then you just kind of make up whatever you want to do and the basic idea is I think and to that I want to kind of translate to kind of a lot of biomedical science is that if we should just use thoroughly applied thoroughly studied methods that we kind of agree upon our subgroupers of scientific the scientific community that these are the appropriate methods to use you don't have to be perfect but we have to kind of hopefully do like the 85% solution。

呃。And there should be evidence to justify the application of certain methods and as statisticians we do this all the time。

 we compare different methods either by simulation or theory or whatnot， and we kind of say， well。

 which method is more appropriate in certain in a given circumstance？



![](img/a85aaf0f832c0ce22314944383fe7096_8.png)

So just a very quick example， this is a histogram that I generated an R。

 I just had hist X and of course the histogram is just a smoother and the most important thing and a smoother is the bandwidth right and so I just made this histogram so how did the bandwidth get chosen？

So it turns out there was a paper written by Sturgs in 1926 publishedlishing Ja paper was actually a very generous term as he was like this law。

 but Lou suggested that the bandwidth should be done according to this formula basically。Later on。

 when the kind of kernel smoothing became popular， Dave Scott wrote a paper in biometricco。

 which talked about choosing the bandwidth based on kind integrated mean squared atypeight measures。

So anyways， the default ban was just programmed in and there it is All right。

 no one argues for the most part with。Sometimes when it make get smaller， bigger that's fine。

 but usually the default is pretty good and there's actually some research behind what that bandwidth should be。



![](img/a85aaf0f832c0ce22314944383fe7096_10.png)