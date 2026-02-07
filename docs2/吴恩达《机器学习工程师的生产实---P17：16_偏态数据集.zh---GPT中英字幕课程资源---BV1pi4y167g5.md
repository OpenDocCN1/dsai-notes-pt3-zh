# 吴恩达《机器学习工程师的生产实践（MLOps）Machine Learning Engineering for Production》中英字幕 - P17：16_偏态数据集.zh_en - GPT中英字幕课程资源 - BV1pi4y167g5

Data sets where the ratio of positive to negative examples is very far from 5050 are called skewed data sets。

 Let's look at some special techniques for handling them。 Let me start with a manufacturing example。

 If a manufacturing company makes smartphones。😊。

![](img/3ada8f4f2e02c4ae5d586902471977e4_1.png)

Hopefully the vast majority of them are not defective， so if 99。

7% have no defect and are labeled y equals0 and only a small fraction is labeled y equals 1。



![](img/3ada8f4f2e02c4ae5d586902471977e4_3.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_4.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_5.png)

Then。Print zero。

![](img/3ada8f4f2e02c4ae5d586902471977e4_7.png)

Which is not a very impressive learning algorithm。

![](img/3ada8f4f2e02c4ae5d586902471977e4_9.png)

Will achieve 99%。7% accuracy or medical diagnosis， which was the example we went through in an earlier video。

 if 99% of patients don't have a disease， then an algorithm that predicts no one ever has a disease will have 99% accuracy。



![](img/3ada8f4f2e02c4ae5d586902471977e4_11.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_12.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_13.png)

Or speech recognition if you're building a system for wake word detection。

 sometimes also called trigger word detection， these are systems that listen and see if you say a special word like Alexa or okay Google or hey Siri most of the time that special wake word or trigger word is not being spoken by anyone at that moment in time So when I had built wakeake word detection systems。

 the datas were actually quite skewed one of the datas I use。



![](img/3ada8f4f2e02c4ae5d586902471977e4_15.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_16.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_17.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_18.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_19.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_20.png)

Had 96。7% negative examples and 3。3% positive examples when you have a very sked data set like this。

 raw accuracy is not that useful a metric to look at because Prince0 can get very high accuracy。



![](img/3ada8f4f2e02c4ae5d586902471977e4_22.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_23.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_24.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_25.png)

Instead it's more useful to build something called a confusion matrix。

 a confusion matrix is a matrix where one axis is labeled with the actual label。

 so is the ground truth label y equals0 or y equals1 and whose other axis is labeled with the prediction so was your learning algorithm's prediction y equals0。



![](img/3ada8f4f2e02c4ae5d586902471977e4_27.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_28.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_29.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_30.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_31.png)

Or y equals1。

![](img/3ada8f4f2e02c4ae5d586902471977e4_33.png)

So if you're building a confusion matrix you fill in with each of these four cells。

 the total number of examples， say the number of examples in your depth set and your development set that fell into each of these four buckets。



![](img/3ada8f4f2e02c4ae5d586902471977e4_35.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_36.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_37.png)

Let's say that 905 examples in your development set had a ground true label of y equals0 and your algorithm got it right then you might write 905 there these examples are called true negatives because they were actually negative and your algorithm predicted it was negative Next。

 let's throw in the true positives which are the examples where the actual ground truth of label is one and the prediction is one。

 maybe there are 68 of them。

![](img/3ada8f4f2e02c4ae5d586902471977e4_39.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_40.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_41.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_42.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_43.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_44.png)

True positives， the false negatives are the examples where your algorithm thought it was negative。



![](img/3ada8f4f2e02c4ae5d586902471977e4_46.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_47.png)

But it was wrong， the actual label is positive， so these are false negatives， so the 18 of that。



![](img/3ada8f4f2e02c4ae5d586902471977e4_49.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_50.png)

And lastly， false positives are the ones where your algorithm them thought it was positive。

 but that turned out to be false， so9。

![](img/3ada8f4f2e02c4ae5d586902471977e4_52.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_53.png)

False positives。The precision。

![](img/3ada8f4f2e02c4ae5d586902471977e4_55.png)

Of learning algorithm， if I sum up over the columns。905 plus 9 is 914 and 18 plus 68 is 86。

 so this is indeed a pretty sked data where out of 1000 examples。

 there were 914 negative examples and just 86。

![](img/3ada8f4f2e02c4ae5d586902471977e4_57.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_58.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_59.png)

Positive example， so 8。6% positive， 91。4% negative。



![](img/3ada8f4f2e02c4ae5d586902471977e4_61.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_62.png)

The precision。Of yourre learning algorithm。

![](img/3ada8f4f2e02c4ae5d586902471977e4_64.png)

Is defined as follows， it of all the examples that the a thought were positive examples。

 what fraction did they get right？

![](img/3ada8f4f2e02c4ae5d586902471977e4_66.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_67.png)

So precision as is defined as true positives divided by true positives plus false。



![](img/3ada8f4f2e02c4ae5d586902471977e4_69.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_70.png)

Positives， in other words。It looks at this row。

![](img/3ada8f4f2e02c4ae5d586902471977e4_72.png)

So of all the examples that your album thought had a label of1， which is 68 plus9 of them。

 68 of them were actually right， so the precision is 68。



![](img/3ada8f4f2e02c4ae5d586902471977e4_74.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_75.png)

Over 68 plus 9， which is 88。3%。 In contrast， the recall。



![](img/3ada8f4f2e02c4ae5d586902471977e4_77.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_78.png)

Os。

![](img/3ada8f4f2e02c4ae5d586902471977e4_80.png)

Of all the examples， that were actually positive。 What fraction did your album get right。

 So recall is defined as true positives， defined by true positives plus。😊。



![](img/3ada8f4f2e02c4ae5d586902471977e4_82.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_83.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_84.png)

False negatives， which in this case is 68 over 68 plus 18， which is 79。1。



![](img/3ada8f4f2e02c4ae5d586902471977e4_86.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_87.png)

Percent。And。The metrics of precision and recall are more useful than raw accuracy when it comes to evaluating the performance of learning algorithms on very skewed data sets。

 let's see what happens if your learning algorithm outputs zero all the time it turns out it won't do very well on recall。

 taking this example of where we had 914 negative examples and 86 positive examples。

 if the algorithm outputs zero all the time。

![](img/3ada8f4f2e02c4ae5d586902471977e4_89.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_90.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_91.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_92.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_93.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_94.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_95.png)

This is what the confusion matrix will look like， 914 times it outputs 0 with a ground truth of0 and 86 times it outputs0 with a ground truth of 1。



![](img/3ada8f4f2e02c4ae5d586902471977e4_97.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_98.png)

So precision is true pauses divided by true pauses plus。



![](img/3ada8f4f2e02c4ae5d586902471977e4_100.png)

False positives， which in this case， turns out to be zero over。



![](img/3ada8f4f2e02c4ae5d586902471977e4_102.png)

0 plus 0。

![](img/3ada8f4f2e02c4ae5d586902471977e4_104.png)

Which is not defined and unless your algorithm actually output no positive labels at all。

 you get some of the number that hopefully isn't0 over zero， but more importantly。

 if you look at recall， which is true positives over true positives plus false negatives。

 this turns out to be。

![](img/3ada8f4f2e02c4ae5d586902471977e4_106.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_107.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_108.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_109.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_110.png)

0 over0 plus 86， which is0。

![](img/3ada8f4f2e02c4ae5d586902471977e4_112.png)

Pscent， and so the print zero algorithm achieves。

![](img/3ada8f4f2e02c4ae5d586902471977e4_114.png)

0% recall， which gives you an easy way to flag that this is not detecting any useful positive examples and the learning algorithm with some precision。

 even the high value of precision is not that useful usually if this recall is so low。



![](img/3ada8f4f2e02c4ae5d586902471977e4_116.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_117.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_118.png)

So the standard metrics when I look at when comparing different models on S datasets are precision and recall。



![](img/3ada8f4f2e02c4ae5d586902471977e4_120.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_121.png)

Where looking at these numbers helps you figure out。



![](img/3ada8f4f2e02c4ae5d586902471977e4_123.png)

And of all the examples， did I truly positive examples。

 what fraction did the algorithm manage to catch？

![](img/3ada8f4f2e02c4ae5d586902471977e4_125.png)

Sometimes you have one model with a better。

![](img/3ada8f4f2e02c4ae5d586902471977e4_127.png)

Recall and a different model with a better precision so how do you compare two different models then's a common way of combining precision and recall using this formula。

 which is called the F1 school。

![](img/3ada8f4f2e02c4ae5d586902471977e4_129.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_130.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_131.png)

One intuition behind the F1 score is that。

![](img/3ada8f4f2e02c4ae5d586902471977e4_133.png)

You want an algorithm to do well on both precision and recall。



![](img/3ada8f4f2e02c4ae5d586902471977e4_135.png)

And if it does worse on either precision or recall， that's pretty bad。

 And so F1 is a way of combining precision and recall that emphasizes whichever of P or R precisional recall is worse in mathematics。

 this is technically called a harmonic mean between precision and recall。

 which is like taking an average， but placing more emphasis on whichever is the lower number。

 So if you compute the F1 score of these two models， it turns out it to be 83。

4% using the formula below here， and model2 has a very bad recall， So it's F1 score is actually。



![](img/3ada8f4f2e02c4ae5d586902471977e4_137.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_138.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_139.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_140.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_141.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_142.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_143.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_144.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_145.png)

Quite low as well， and this lets us。

![](img/3ada8f4f2e02c4ae5d586902471977e4_147.png)

Tell maybe more clearly that Model1 appears to be a superior model than Model 。



![](img/3ada8f4f2e02c4ae5d586902471977e4_149.png)

For your application， you may have a different weighting between precision and recall and so F1 isn't the only way to combine precision and recall it's just one metric that's commonly used for many applications Let me step through one more example where precision and recall。



![](img/3ada8f4f2e02c4ae5d586902471977e4_151.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_152.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_153.png)

Is useful so far we've talked about a binary classification problem with Sked datas it turns out to also frequently be useful for multiclass classification problems if you are detecting defects in smartphones。

 you may want to detect scratches on them or dense or pit marks。

 this is what it looks like if someone took a screwdriver and poke a cell phone。



![](img/3ada8f4f2e02c4ae5d586902471977e4_155.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_156.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_157.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_158.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_159.png)

Or discoloration of the cellphone's LCD screen or other material。

 maybe all four of these defects are actually quite rare that you might want to develop an algorithm that can detect all four of them。

 one way to evaluate how your algorithm is doing on all four of these defects。



![](img/3ada8f4f2e02c4ae5d586902471977e4_161.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_162.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_163.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_164.png)

Each of which can be quite rare would be to look at precision and recall of each of these four types of defects individually In this example。

 the learning algorithm has 82。1% precision on finding scratches and 99。

2% recall you find in manufacturing that many factories will want high recall because you really don't want to let the phone go out that is defective。

 but if an algorithm has slightly lower precision that's okay because through a human reexamining the phone they will hopefully figure out that the phone is actually okay So many factories will emphasize high recall and by combining precision and recall using F1。



![](img/3ada8f4f2e02c4ae5d586902471977e4_166.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_167.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_168.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_169.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_170.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_171.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_172.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_173.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_174.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_175.png)

As follows， this gives you a single number evaluation metric for how well your algorithm is doing on the four different types of defects and can also help you benchmark to human level performance and also prioritize what to work on nexts so instead of accuracy on scratches dense pits and discolorations。



![](img/3ada8f4f2e02c4ae5d586902471977e4_177.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_178.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_179.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_180.png)

Using F1 score can help you to prioritize the most fruitful type of defect to try to work on。



![](img/3ada8f4f2e02c4ae5d586902471977e4_182.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_183.png)

And the reason we use F1 is because。

![](img/3ada8f4f2e02c4ae5d586902471977e4_185.png)

Maybe all four defects are very rare， and so accuracy would be very high even if the algorithm was missing a lot of these defects。



![](img/3ada8f4f2e02c4ae5d586902471977e4_187.png)

![](img/3ada8f4f2e02c4ae5d586902471977e4_188.png)

So I hope that these tools will help you both evaluate your algorithm as well as prioritize what to work on。

 both in problems with Ske dataset sets and for problems with multiple rare classes。

Now to wrap up this section on error analysis there's one final concept I hope to go over with you which is performance auditing I found for many projects this is a key step to make sure that your learning algorithm is working well enough before you push it out to a production deployment let's take a look at performance auditing。

