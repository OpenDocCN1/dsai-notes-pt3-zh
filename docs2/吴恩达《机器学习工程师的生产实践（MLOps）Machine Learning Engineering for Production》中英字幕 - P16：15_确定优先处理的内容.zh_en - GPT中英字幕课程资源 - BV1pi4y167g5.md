# 吴恩达《机器学习工程师的生产实践（MLOps）Machine Learning Engineering for Production》中英字幕 - P16：15_确定优先处理的内容.zh_en - GPT中英字幕课程资源 - BV1pi4y167g5

In the last video you learned about brainstorming and tagging your data with different attributes let's see how you can use this to prioritize where to focus your attention Here here's the example we had previously with four tags and the accuracy of the algorithm。

 human level performance and what's the gap between the current accuracy and human level performance rather than deciding to work on car noise because the gap to HLP is biggest one other useful factor to look at is what's the percentage of data with that tag let's say that 60% of your data。



![](img/1effc72fc58ce7593e60ff455fa99628_1.png)

![](img/1effc72fc58ce7593e60ff455fa99628_2.png)

![](img/1effc72fc58ce7593e60ff455fa99628_3.png)

![](img/1effc72fc58ce7593e60ff455fa99628_4.png)

![](img/1effc72fc58ce7593e60ff455fa99628_5.png)

Is clean speech？4% is。

![](img/1effc72fc58ce7593e60ff455fa99628_7.png)

Data with car noise， 30% has people noise and 6% is low bandwidth with audio。

 This tells us that if we could take clean speech and raise our accuracy from 94 to 95% on all the clean speech then multiply 1% with 60% this tells us that if we could improve our performance on clean speech to human level performance。

 our overall speech system would be 0。6% more accurate because we would do 1% better on 60% of the data so this will raise average accuracy by 0。

6% on car noise if we can improve。

![](img/1effc72fc58ce7593e60ff455fa99628_9.png)

![](img/1effc72fc58ce7593e60ff455fa99628_10.png)

![](img/1effc72fc58ce7593e60ff455fa99628_11.png)

![](img/1effc72fc58ce7593e60ff455fa99628_12.png)

![](img/1effc72fc58ce7593e60ff455fa99628_13.png)

![](img/1effc72fc58ce7593e60ff455fa99628_14.png)

![](img/1effc72fc58ce7593e60ff455fa99628_15.png)

![](img/1effc72fc58ce7593e60ff455fa99628_16.png)

![](img/1effc72fc58ce7593e60ff455fa99628_17.png)

The performance by 4%。On 4% of the data。

![](img/1effc72fc58ce7593e60ff455fa99628_19.png)

Multiping that out。 That gives us a。16% improvement。And multiplying these out as well， we get 0。

6% and well， this is essentially 0% because we can't make that any better and so whereas previously we had said there's a lot of room for improvement in con noise in this slightly richer analysis we see that because people noise accounts for such a large fraction of the data。

 it may be more worthwhile to work on either people noise。



![](img/1effc72fc58ce7593e60ff455fa99628_21.png)

![](img/1effc72fc58ce7593e60ff455fa99628_22.png)

![](img/1effc72fc58ce7593e60ff455fa99628_23.png)

![](img/1effc72fc58ce7593e60ff455fa99628_24.png)

![](img/1effc72fc58ce7593e60ff455fa99628_25.png)

![](img/1effc72fc58ce7593e60ff455fa99628_26.png)

Or maybe on clean speech because there's actually larger potential for improvements in both of those than for speech with car noise。

 so to summarize when prioritizing what to work on。



![](img/1effc72fc58ce7593e60ff455fa99628_28.png)

![](img/1effc72fc58ce7593e60ff455fa99628_29.png)

![](img/1effc72fc58ce7593e60ff455fa99628_30.png)

You might decide on the most important categories to work on based on how much room for improvement there is。

 such as compared to human level performance or according to some baseline comparison。

 how frequently does that category appear， you can also take an account how easy it is to improve accuracy in that category。

 for example， if you have some ideas for how to improve the accuracy of speech with car noise。

 maybe your data augmentation that might cause you to prioritize that category more highly than some other category where you just don't have as many ideas for how to improve the system and then finally how important it is to improve performance on that category for example you may decide that improving performance with car noise is especially important because when you're driving you have a stronger desire to do search especially search on maps and find addresses without needing to use your hands if your hands。



![](img/1effc72fc58ce7593e60ff455fa99628_32.png)

![](img/1effc72fc58ce7593e60ff455fa99628_33.png)

![](img/1effc72fc58ce7593e60ff455fa99628_34.png)

![](img/1effc72fc58ce7593e60ff455fa99628_35.png)

![](img/1effc72fc58ce7593e60ff455fa99628_36.png)

![](img/1effc72fc58ce7593e60ff455fa99628_37.png)

![](img/1effc72fc58ce7593e60ff455fa99628_38.png)

![](img/1effc72fc58ce7593e60ff455fa99628_39.png)

![](img/1effc72fc58ce7593e60ff455fa99628_40.png)

![](img/1effc72fc58ce7593e60ff455fa99628_41.png)

![](img/1effc72fc58ce7593e60ff455fa99628_42.png)

![](img/1effc72fc58ce7593e60ff455fa99628_43.png)

I are supposed to be holding the steering wheel。There is no mathematical formula that will tell you what to work on。

 but by looking at these factors， I hope you'd be able to make more fruitful decisions once you've decided that there's a category or maybe a few categories where you want to improve the algorithm's performance。

 one fruitful approach is to consider adding data or improving the quality of that data for that one or maybe a small handful of categories。

 so for example， if you want to improve performance on speech with carnoise you might go out and collect more data with con noise or if you have a way of using data augmentation to get more data from that category that would be another way to improve your algorithm's performance。

 one topic that will discuss next week is how to improve label accuracy or data quality you learn more about this when we talk about the data phase of the machine learning Project lifecycle。



![](img/1effc72fc58ce7593e60ff455fa99628_45.png)

![](img/1effc72fc58ce7593e60ff455fa99628_46.png)

![](img/1effc72fc58ce7593e60ff455fa99628_47.png)

![](img/1effc72fc58ce7593e60ff455fa99628_48.png)

![](img/1effc72fc58ce7593e60ff455fa99628_49.png)

![](img/1effc72fc58ce7593e60ff455fa99628_50.png)

![](img/1effc72fc58ce7593e60ff455fa99628_51.png)

![](img/1effc72fc58ce7593e60ff455fa99628_52.png)

![](img/1effc72fc58ce7593e60ff455fa99628_53.png)

![](img/1effc72fc58ce7593e60ff455fa99628_54.png)

![](img/1effc72fc58ce7593e60ff455fa99628_55.png)

![](img/1effc72fc58ce7593e60ff455fa99628_56.png)

In machine learning， we always would like to have more data。

 but going out to collect more data generically can be very time consuming and expensive by carrying out an analysis like this。



![](img/1effc72fc58ce7593e60ff455fa99628_58.png)

![](img/1effc72fc58ce7593e60ff455fa99628_59.png)

![](img/1effc72fc58ce7593e60ff455fa99628_60.png)

When you are then going through this iterative process of improving your learning algorithm。

 you can be much more focused in exactly what types of data you collect because if you decide to collect more data with car noise or maybe people noise you can be much more specific in going out to collect more of just that data or using data augmentation without wasting time trying to collect more data from a low bandwidth with cellphone connection and this focus on improving your data on the tags that you have determined are most fruitful for you to work on that can help you be much more efficient in how you improve your learning algorithms performance I found this type of error analysis procedure very useful for many of my projects and I hope it will help you too in building production ready machine learning systems。



![](img/1effc72fc58ce7593e60ff455fa99628_62.png)

![](img/1effc72fc58ce7593e60ff455fa99628_63.png)

![](img/1effc72fc58ce7593e60ff455fa99628_64.png)

![](img/1effc72fc58ce7593e60ff455fa99628_65.png)

![](img/1effc72fc58ce7593e60ff455fa99628_66.png)

![](img/1effc72fc58ce7593e60ff455fa99628_67.png)

![](img/1effc72fc58ce7593e60ff455fa99628_68.png)

![](img/1effc72fc58ce7593e60ff455fa99628_69.png)

Next， one of the most common challenges we run into is Skewed datasets。

 let's go to the next video to go through some techniques for managing skewed datasets。

