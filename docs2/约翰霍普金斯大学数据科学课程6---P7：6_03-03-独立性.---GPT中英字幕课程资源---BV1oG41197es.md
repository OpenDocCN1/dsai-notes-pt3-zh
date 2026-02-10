# 约翰霍普金斯大学数据科学课程6：《统计推断课程（约翰霍普金斯大学）》｜statistical-inference｜ - P7：6_03 03 独立性.zh_en - GPT中英字幕课程资源 - BV1oG41197es

![](img/f3ea028738b8e20d0c827b103c127849_0.png)

Let's cover briefly the subject of independence。We alluded to this earlier in that we said that a is independent of B if the probability of a given B is equal to the probability A for an event B that has positive probability。



![](img/f3ea028738b8e20d0c827b103c127849_2.png)

![](img/f3ea028738b8e20d0c827b103c127849_3.png)

![](img/f3ea028738b8e20d0c827b103c127849_4.png)

Another definition of the independence is that the probability A and B are independent if the probabilitybative A intersect B works out to be the product of their probabilities。



![](img/f3ea028738b8e20d0c827b103c127849_6.png)

![](img/f3ea028738b8e20d0c827b103c127849_7.png)

This then begins a very important lesson， you can't just multiply probabilities Will nilly。

 you have to multiply independent probabilities associated with independent events。



![](img/f3ea028738b8e20d0c827b103c127849_9.png)

![](img/f3ea028738b8e20d0c827b103c127849_10.png)

Let's go through a numerical example， what is the probability of getting two consecutive heads？



![](img/f3ea028738b8e20d0c827b103c127849_12.png)

Let's define a as the probability of getting ahead on F1 and B is the probability of getting ahead on F2 both probabilities are 0。

5 in this case we're assuming a fair coin。

![](img/f3ea028738b8e20d0c827b103c127849_14.png)

![](img/f3ea028738b8e20d0c827b103c127849_15.png)

A intersect B is the event of getting heads on flips one and two。



![](img/f3ea028738b8e20d0c827b103c127849_17.png)

In this case， because the events are independent， the probability of A inter sec B is the product of the probabilities and so we would say that it's 0。

25， people do this calculation rather naturally。

![](img/f3ea028738b8e20d0c827b103c127849_19.png)

![](img/f3ea028738b8e20d0c827b103c127849_20.png)

![](img/f3ea028738b8e20d0c827b103c127849_21.png)

The problem is when people multiply probabilities when they shouldn't。



![](img/f3ea028738b8e20d0c827b103c127849_23.png)

A particularly stark instance of incorrectly multiplying probabilities occurred in volume 309 of science。



![](img/f3ea028738b8e20d0c827b103c127849_25.png)

Which was reporting on a physician who was on trial for giving expert testimony in a criminal trial。

The criminal trial involved a mother。Who had had two children die from sudden infant death syndrome？

The expert testimony took the prevalence of Southern sudden infant death syndrome as one out of 8。

500， and then multiplied them together to find the probability of two children having sudden infant death syndrome with the same mother。

 based on this evidence， and I presume other evidence the mother on trial was convicted of murder。



![](img/f3ea028738b8e20d0c827b103c127849_27.png)

![](img/f3ea028738b8e20d0c827b103c127849_28.png)

![](img/f3ea028738b8e20d0c827b103c127849_29.png)

![](img/f3ea028738b8e20d0c827b103c127849_30.png)

![](img/f3ea028738b8e20d0c827b103c127849_31.png)

Relevan to this class， the principal mistake was to multiply probabilities for events that were not necessarily independent。



![](img/f3ea028738b8e20d0c827b103c127849_33.png)

And it makes sense that in this case， to assume that the events would be dependent because any biological process that has a genetic or familial environmental component is likely to be dependent within families。



![](img/f3ea028738b8e20d0c827b103c127849_35.png)

![](img/f3ea028738b8e20d0c827b103c127849_36.png)

![](img/f3ea028738b8e20d0c827b103c127849_37.png)

In this class， the main way we're going to use independence is that we're going to assume that a collection of random variables are independent and from the same distribution。

 we call such random variables independent and identically distributed。

 so you might think of several coin flips as IID because they are independent one coin flip is independent from the next one。

 and they all arise from the same distribution 0。5 for heads and 0。5 for tails。



![](img/f3ea028738b8e20d0c827b103c127849_39.png)

![](img/f3ea028738b8e20d0c827b103c127849_40.png)

![](img/f3ea028738b8e20d0c827b103c127849_41.png)

![](img/f3ea028738b8e20d0c827b103c127849_42.png)

![](img/f3ea028738b8e20d0c827b103c127849_43.png)

IID sampling is our default model for a random sample。

 so whether we have an actual random sample or not。

 we often use random sampling or the model of IID as a conceptual model to analyze our data。

 it'll be our principal mode of analysis for this class。



![](img/f3ea028738b8e20d0c827b103c127849_45.png)

![](img/f3ea028738b8e20d0c827b103c127849_46.png)

![](img/f3ea028738b8e20d0c827b103c127849_47.png)