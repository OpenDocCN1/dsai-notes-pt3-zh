# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P28：27_特征缩放.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_0.png)

Now let's talk about feature scaling。This will involve adjusting a variable scale to allow comparison of variables with different scales。



![](img/8cf8e1c15fa2dd174e8bee065d3472ea_2.png)

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_3.png)

Now， different continuous features will often have different scales in real- world data think if one is between0 and 10。

 such as working with the price of the product and the other is between 10，000 and 50，000。

 such as the number of stores that are selling that product and you're using both those variables to create a prediction for what's going to be the total sales。

 we may want to bring those on similar scales。

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_5.png)

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_6.png)

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_7.png)

And why this might be an issue well make clear by looking at the graph in the next slide。



![](img/8cf8e1c15fa2dd174e8bee065d3472ea_9.png)

So imagine we're using an algorithm。That bases at risk patients。

 so we're talking about at risk patients are each of these dots。



![](img/8cf8e1c15fa2dd174e8bee065d3472ea_11.png)

According to where a new patient falls on the graph that we have here to the left。



![](img/8cf8e1c15fa2dd174e8bee065d3472ea_13.png)

And whether that patient is near to more at risk patients or near to。



![](img/8cf8e1c15fa2dd174e8bee065d3472ea_15.png)

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_16.png)

Healthier， less risk risky patients。This is an actual algorithm。

 all we're doing is finding the nearest neighbor and the algorithm is called K nearest neighbors。

 which we'll learn later on。

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_18.png)

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_19.png)

To make it even more extreme， just to hammer in on this point。

 imagine that the age was measured in seconds， so the units are seconds rather than years。

 so every year would represent 31。5 million units。

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_21.png)

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_22.png)

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_23.png)

So if we kept surgeries on its original scale。Then the difference between。



![](img/8cf8e1c15fa2dd174e8bee065d3472ea_25.png)

20 and21， the age would be 31。5 million units。

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_27.png)

But the difference between a patient having only one surgery versus them having， let's say。

10 surgeries would be only 9 units away。

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_29.png)

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_30.png)

Which would probably indicate right， more surgeries would indicate a higher risk patient。

 but because the age difference between 20 and 21 is 31。5 million units。



![](img/8cf8e1c15fa2dd174e8bee065d3472ea_32.png)

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_33.png)

The person will be grouped with whoevers the same age， no matter their number of surgeries。

 because the scale is thrown so far off by how close they are to someone of the same age compared to how close they are with someone of the same number of surgeries。



![](img/8cf8e1c15fa2dd174e8bee065d3472ea_35.png)

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_36.png)

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_37.png)

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_38.png)

So we can scale to ensure that these numbers have the same magnitude of units。

 and that's the idea so that we can take into account the age and the number of surgeries on a similar scale。



![](img/8cf8e1c15fa2dd174e8bee065d3472ea_40.png)

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_41.png)

And it would look similar to the graph that we have on the right。

 but the numbers would actually be transformed by some scalar depending on the scaling approach that we use。

 which we'll see a couple of options in the next slide。



![](img/8cf8e1c15fa2dd174e8bee065d3472ea_43.png)

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_44.png)

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_45.png)

So some common approaches to scaling。Include standard scaling， which is a great means of scaling。

 which may be familiar to those that have gotten Z scores in the past。



![](img/8cf8e1c15fa2dd174e8bee065d3472ea_47.png)

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_48.png)

Where all we do is subtract the mean and divide by the standard deviation to give measures of this spread in standardized units。



![](img/8cf8e1c15fa2dd174e8bee065d3472ea_50.png)

And this is just to be aware of possible to be affected by outliers where the mean could be dragged out by an outlier。

 as well as a standard deviation being expanded by an outlier。

 but probably not as strongly as our next one， and we'll get into this in a second。

 which is the min Mac scaling。 And that will put the pro to this is we'll put all your values between 0 and one。



![](img/8cf8e1c15fa2dd174e8bee065d3472ea_52.png)

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_53.png)

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_54.png)

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_55.png)

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_56.png)

The way that it scales is by subtracting the minimum value from that column and then dividing by the max minus the minimum。

 So if you think about the minimum value is 3，3-3 is 0 over， and let's say the max is 100 over 97。

 whereas somewhere in the middle， let's say 40。

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_58.png)

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_59.png)

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_60.png)

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_61.png)

40-3 would be 37， and that would be 37 over 97 would be our new value。

 So it's good if you want all your values to be between 0 and1。

 but it can be heavily influenced by outliers。 Imagine all your values are between 0 and 10。

 except for one that's at 10000。 That's your max。 and then all the values between 0 and 10 would be squished together。



![](img/8cf8e1c15fa2dd174e8bee065d3472ea_63.png)

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_64.png)

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_65.png)

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_66.png)

Finally， robust scaling is similar to min Max， but instead it's going to focus on the innercotile range。



![](img/8cf8e1c15fa2dd174e8bee065d3472ea_68.png)

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_69.png)

That's going to allow to avoid any skew from the outliers as we just mentioned。

 and this is going to be robust to outliers， but will not ensure that you can remain between zero and1。



![](img/8cf8e1c15fa2dd174e8bee065d3472ea_71.png)

![](img/8cf8e1c15fa2dd174e8bee065d3472ea_72.png)