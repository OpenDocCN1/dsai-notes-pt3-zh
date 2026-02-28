# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p07 07_01_04_探索摩尔定律的终结.zh_en -BV1tz421i7Ev_p7-

![](img/49d991c71d884c5806e23790ffe23a25_0.png)

Let's talk about the end of Moore's law。 One of the best ways to describe what's happening is to follow along with what Dr。

 David Patterson is doing at UC Berkeley。 he's an architect as well for the TPU。

 which is a Tensorflow processing unit and what he says is that the end ofgrowth of single program speed really occurred right around this period of the last 40 years so at first in the 1980s。

 there was this 22% increase once the risk processor was around。

 we got a 52% increase then things started to slow down a little bit and you can see here right around let's say 2003。

 theres a 23% growth rate because multicore machines come in and they're not as efficient at scaling things because you're going to lose efficiency due to Ammdo's law and here we see Omdo's law which effectively says the parallel portion of your code has diminishing returns finally you get to current which is。

a 3% increase so there's some big problems， but it creates opportunities so one of the ways that people are taking advantage of this dead end is to look at Asics and these stand for application specific integrated circuits and a good example of an AsIic is something that many people already have on their machine is a GPU and specifically things like NviDdia GPU there's been a whole toolkit designed around it to do parallel coding and that toolkit is called KUa there's other vendors that are starting to jump in and get involved and compete with the coUa infrastructure like AMD also there's new players like TpUus which are actually even going beyond what a GPU does and specifically generating workloads that work with let's say the TensorF machine learning framework so here's an example of a TU and production for Google started in 2015 they use for search for translation for。

You can see a whole rack here。Now what's the difference well a CPUU is really designed to do a lot of different things so it's a general purpose processing unit now if you look at a GPU though it's been specifically designed to do things in parallel really and that's the big difference between a CPU and a GPU is a GPU is designed to be parallel where a CPU is really designed to do lots of different things and execute different things on a computer。

Now if we look at a TPU， one of the things that's interesting is a TPU is even more dense than a GPU and you can see that a TPU is actually doesn't even care about doing only parallelization。

 it's focused on parallelization for a specific workload so really this is one of the advantages of these AsIs is that you as maybe a software vendor you could control the whole stack and you could actually design something that works with the software you have。

 the cloud you have and also the processor you have。



![](img/49d991c71d884c5806e23790ffe23a25_2.png)