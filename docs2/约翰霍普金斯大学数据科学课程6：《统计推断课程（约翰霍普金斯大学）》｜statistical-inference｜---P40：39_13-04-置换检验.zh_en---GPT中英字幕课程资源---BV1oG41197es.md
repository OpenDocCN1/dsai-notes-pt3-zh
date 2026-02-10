# 约翰霍普金斯大学数据科学课程6：《统计推断课程（约翰霍普金斯大学）》｜statistical-inference｜ - P40：39_13 04 置换检验.zh_en - GPT中英字幕课程资源 - BV1oG41197es

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_0.png)

We're going to end the class on something that is an incredibly useful tool for data scientists。

 so called permutation test。

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_2.png)

And these are used for group comparisons， so let's start with a motivating example of group comparisons where it may not be immediately obvious what to do。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_4.png)

So。In this example。Researchers took batches of insects and applied different pesticides to them。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_6.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_7.png)

Labeled as sprays here。And they counted the number of dead insects in each batch。

 so for each spray they got a collection of counts that represented the efficacy of that pesticide。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_9.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_10.png)

Let's consider looking at insect spray B versus insect spray C。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_12.png)

Consider the null hypothesis that the distribution of the observations from each group is the same。

 in other words， which label a particular count received was irrelevant。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_14.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_15.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_16.png)

So operationally， think about a data frame with the counts down one column and the spray group labels down another column。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_18.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_19.png)

We would calculate a statistic such as the difference in the average number of insects killed。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_21.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_22.png)

For group B and subtract that off from group C， that would be our observed test statistic。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_24.png)

Now consider permuting the group labels， just taking that vector of labels and permuting it。

 for example， with just the command sample in R， which if you give a vector with no arguments。

 the command sample just。

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_26.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_27.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_28.png)

Randomly permutees the entries。

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_30.png)

Then you could recalculate the statistic。

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_32.png)

For each permutation， you could use any statistic you'd like。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_34.png)

For example， it could be the mean difference in counts between the two groups。

 it could be the geometric means or even a T statistic。

 you can use a T statistic and not compare it with a T null distribution。

 you could compare it to a permutation based null distribution。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_36.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_37.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_38.png)

To calculate a P value， you simply want to calculate the percentage of simulations where the simulated statistic was more extreme in the favor of the alternative than the observed。

 so more extreme in the difference of means settings would be having a greater difference in the means towards the direction of the alternative。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_40.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_41.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_42.png)

This will yield a permutation based P value。Let's go through an example， and I think it'll be much。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_44.png)

I'm not going to dwell too much on this slide， but I just want to say that permutation tests are very powerful and so much so that they keep being reinvented in different settings。

 for example， the rank sun test of famous test and statistic is a permutation test where you've replaced your data in some fashion by ranks rather than the original raw values。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_46.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_47.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_48.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_49.png)

Fisher's exact test， which you might have heard of is exactly a permutation based test where simply our data type is binary。

 and there's a specific test statistic you're using。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_51.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_52.png)

If you use the raw data and then you're just doing an ordinary permutation test。

 I would also add that there's a separate entity called randomization test when you explicitly had randomization your group labels were randomized。

 for example on our insect spray test batches might have had sprays randomized to them so it might be considered a randomization test operationally。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_54.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_55.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_56.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_57.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_58.png)

Your randomization test is going to be performed in the same way as a permutation test。

 however you might have stronger conclusions from your randomization test and the way in which you interpret your randomization test might be a little bit different。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_60.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_61.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_62.png)

I would also add you can use permutation strategies and regression。

 so you just simply permute a regressor and this is a different way to get a null distribution than using the normal distributions that we'll cover in our regression class as the next part of the specialization。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_64.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_65.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_66.png)

And permutation tests work very well in multivariate settings because you can calculate sort of maximum statistics that control family wise error rates。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_68.png)

We're not going to go over too much of any of this。

 we simply want you to be able to go through a simple permutation test。

 get the ideas so later on you can build on top of this foundation。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_70.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_71.png)

Let's go through an example where we just illustrate doing permutation tests。

 first I'm going to subset the data just so I have insects sprays B and C。

 my Y is going to be my outcome， the count of dead insects。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_73.png)

My group is just going to be group labels or spray in this case， pesticide in this case。

 so why element1 received is the count of dead insects for insect spray element1 of the vector group and the same thing for element2 of y and element 2 group。

 in other words my y and my group vectors are perfectly lined up。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_75.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_76.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_77.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_78.png)

So my test statistic is just the average difference。

 mean the average number of dead insects from group B minus the average number of dead insects in group。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_80.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_81.png)

C averaged over batches。

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_83.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_84.png)

My actual observed statistic is just my test sta applied to my outcome and group here the two are lined up correctly。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_86.png)

Now I'm going to break that lineup。By permuting， so now when I apply my test statistic。

I'm going to give it my why， but my group labels permed， so I'm doing sample group。

 which permuteates my group labels， and I'm going to do that 10，000 times to get 10。

000 test statistics where I have broken any association between Y and group by permuting my group labels。

 this is under the null hypothesispo that my group label is unrelated to my outcome。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_88.png)

This means that the。13。25 is the difference in the average count of dead insects for B minus dead insects for C。

 so in excess of 13 dead insects on average killed per batch for B versus C。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_90.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_91.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_92.png)

Let's now calculate the percentage of our peermuted test statistics that are larger or more extreme in favor of the alternative than our observed statistic。

 and it turns out in this data set we get zero。

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_94.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_95.png)

So across 10，000 permutations， we couldn't find a reconfiguration of the group labels that led to a more extreme value of the test statistic than our observed statistic。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_97.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_98.png)

Or more formally， the P value is very small。Close to 0。 And so we。

Reject an hypothesis for any reasonable level of alpha。

I would note the P value is not exactly zero because we can think of at least one permutation that is as big as our observed statistic。

 namely the permutation that gives us back our original data。

 This is kind of a minor point because we're going to do thousands and thousands of simulations and whether or not we add that one in or not is kind of irrelevant when we compare our P value to any normal critical value like 5%。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_100.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_101.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_102.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_103.png)

Here I'm showing the null distribution generated by our permutations。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_105.png)

Basically， this is serving the same role that our T distribution or standard Z distribution does in hypothesis testing where we're willing to assume that either the data is normal or we're appealing to the central limit theorem。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_107.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_108.png)

We'll see that our null distribution in this case is centered at zero and goes from minus 10 to plus 10。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_110.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_111.png)

So the fact that we see a minus 10 means that when we permed group labels。

 we saw test statistics as low as minus 10。

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_113.png)

What I put here as a vertical line is the observed statistic and you'll see it's way far out in the tail of our null distribution。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_115.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_116.png)

Suggesting that likely the null distribution is not the correct true distribution in that B really is very different from C。

 I think we can just see that from the histogram， but now we can quantify it with a P value。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_118.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_119.png)

And we can perform a formal hypothesis test。

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_121.png)

Whether in bootstrapping where you're looking at the sampling distribution of a statistic or in permutation testing where you're looking at a formal inference based on an idea of exchangeability of group labels。

 in either case， I think it's very important to do these histograms or density estimates to see your resampled distributions。



![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_123.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_124.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_125.png)

![](img/7ecd1e1f172ac4d9773aa2dfb595acc7_126.png)