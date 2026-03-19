# 图宾根大学【中英⚡机器学习数学｜2020 Tübingen Mathematics for Machine Learning】 p20 P20 (A) Linear algebra 19： Convex set induces a norm -BV1VhbMzKEts_p20-

![](img/b1d871bdeff1f1a438d5a175ccc68f19_0.png)

When I introduced norms and in particular， when we looked at P norms。

 we have been studying the unit balls of pen norms。



![](img/b1d871bdeff1f1a438d5a175ccc68f19_2.png)

And we have seen that if p is larger than1 or equals to1。

 then the unit ball is typically a nice and convex set。

 whereas if p is smaller than one so between0 and1， the unit ball had this sort of odd shape。

 which was not convex。

![](img/b1d871bdeff1f1a438d5a175ccc68f19_4.png)

![](img/b1d871bdeff1f1a438d5a175ccc68f19_5.png)

![](img/b1d871bdeff1f1a438d5a175ccc68f19_6.png)

![](img/b1d871bdeff1f1a438d5a175ccc68f19_7.png)

And at that part in the lecture， I said we're going to look into this more deeply。

 Now this is what we're going to do today。

![](img/b1d871bdeff1f1a438d5a175ccc68f19_9.png)

What I want to do today is a bit of an advanced result。That says， first of all。

 that if you have a norm， its unit ball is a convex set。



![](img/b1d871bdeff1f1a438d5a175ccc68f19_11.png)

But the other way around， if you have a convex set that is symmetric in a certain way you can use that convex set to define a norm on RD and this is a concept that might be very useful in machine learning because sometimes it is hard to write down a norm analytically and sometimes you can simply define a norm by saying here's the convex set and then I want to look at the corresponding norm。



![](img/b1d871bdeff1f1a438d5a175ccc68f19_13.png)

![](img/b1d871bdeff1f1a438d5a175ccc68f19_14.png)

![](img/b1d871bdeff1f1a438d5a175ccc68f19_15.png)

![](img/b1d871bdeff1f1a438d5a175ccc68f19_16.png)

![](img/b1d871bdeff1f1a438d5a175ccc68f19_17.png)

And norms in machine learning are really important because they convey sort of the inductive bias that your algorithm has。

 and by this principle it allows you to construct norms beyond the standard couple of norms that are out there。



![](img/b1d871bdeff1f1a438d5a175ccc68f19_19.png)

![](img/b1d871bdeff1f1a438d5a175ccc68f19_20.png)

![](img/b1d871bdeff1f1a438d5a175ccc68f19_21.png)

![](img/b1d871bdeff1f1a438d5a175ccc68f19_22.png)

Admittedly this is another result that you probably would have seen in your undergrad lecture。

 but I like it， it's fun， so simply try to follow。

![](img/b1d871bdeff1f1a438d5a175ccc68f19_24.png)

![](img/b1d871bdeff1f1a438d5a175ccc68f19_25.png)

Before we can dive into the state what the actual theorem is。

 I want to recap what a convex set is just to make sure。



![](img/b1d871bdeff1f1a438d5a175ccc68f19_27.png)

![](img/b1d871bdeff1f1a438d5a175ccc68f19_28.png)

So。Definition。We consider。Consider a real electro space。



![](img/b1d871bdeff1f1a438d5a175ccc68f19_30.png)

D。And now we consider a set S。

![](img/b1d871bdeff1f1a438d5a175ccc68f19_32.png)

So S is any set in our vectors phase。So S is called。Convex。



![](img/b1d871bdeff1f1a438d5a175ccc68f19_34.png)

If。For all T t between sorry T is between 0 and1。

![](img/b1d871bdeff1f1a438d5a175ccc68f19_36.png)

Bread it nicer。

![](img/b1d871bdeff1f1a438d5a175ccc68f19_38.png)

Z is smaller than t smaller than one。

![](img/b1d871bdeff1f1a438d5a175ccc68f19_40.png)