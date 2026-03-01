# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p15 15_01_05_阿姆达尔定律.zh_en -BV1tz421i7Ev_p15-

![](img/8acdd52c0ceb24bc76cb8779e2c66d12_0.png)

Omdale's law is about the diminishing returns that occur with parallelization。

  previously I talked about how Python in particular has the global interpreter lock or gill。

 which eliminates the ability to distribute amongst many cores。

 but let's say even if you do have the ability to distribute let's say Java code or C sharpharp code across all the cores。

 you still have these diminishing returns and you can see that essentially even in the case of let's say。

 a 95% parallel operation which is maybe like a deep learning type operation。

 that there's diminishing returns that occur， depending on how much you actually distribute the load across the cores and eventually what happens is that even in the case of highly parallel code。

 you actually tap out and so in this particular example here， you can see there's double the speed。

In this example that's highly parallel and after let's say 50 cores。

 then you're really not getting that big of a benefit anymore likewise。

Even if it is massively parallel it's only a linear or very gradual rate of speed up that is not proportional to the number of cores you have so in a nutshell the big takeaway with parallelization is that because of the nature of having to shift the processing power around all the different cores you're losing things in the process of parallelizing your code。

 you have to lock the code you have to distribute it and in fact most code isn't purely parallel there could be a sleep or a time out or there could be waiting for the network or waiting for a disk and so in the real world multicore programming often doesn't give you that big of a ROI in terms of everyday task it's really the specialized tasks like for example。

 deep learning that would be an example where you do get a lot of benefit for doing things in a highly parallel fashion so it really depends when you're doing parallel。

processing what type of problem you're working with and also the environment that you're running it on。

 whether you do have the ability to access all the cores， but there is no free lunch。

 you are going to have diminishing returns with parallelization。



![](img/8acdd52c0ceb24bc76cb8779e2c66d12_2.png)

![](img/8acdd52c0ceb24bc76cb8779e2c66d12_3.png)