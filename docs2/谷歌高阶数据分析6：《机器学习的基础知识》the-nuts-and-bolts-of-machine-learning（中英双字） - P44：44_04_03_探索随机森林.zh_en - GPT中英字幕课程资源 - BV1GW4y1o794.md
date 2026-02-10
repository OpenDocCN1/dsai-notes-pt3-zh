# 谷歌高阶数据分析6：《机器学习的基础知识》the-nuts-and-bolts-of-machine-learning（中英双字） - P44：44_04_03_探索随机森林.zh_en - GPT中英字幕课程资源 - BV1GW4y1o794

![](img/2d24b0bd1731f667db3b40ff736329b1_0.png)

Now that you've been introduced to random forests， let's examine a little more closely what they are and how they function。

 It's important to understand this methodology because it's commonly used in data work。

 and many of its component steps are used by other more advanced modeling strategies。As a refresher。

 a random forest is an ensemble of learning trees whose predictions are all aggregated to determine a final prediction。

 Each tree in a random forest model uses bootstrapping to randomly sample the observation in the training data with replacement。

 Remember， this means that any tree in the model can use the same observation。

 and the same observation can be sampled more than once by the same tree。😊。

Bootstrapping is a critical component of random forest models。

 It ensures that every base learner in the ensemble is trained on different data while allowing each learner to train on a data set that's the same size as the original training data。

Because there are duplicated observations in the trees training data。

 each one will be missing some of the observations from the original training data set。

One more important principle of random forest models is that all trees in the ensemble are trained on a random subset of the available features in the data set。

No single tree sees all the features。Again， this is to introduce another element of randomness and ensure that each tree is as different from the others as possible。

You learned that one of the main weaknesses of decision trees is that they are very sensitive to new data。

 so they're prone to overfitting。Therefore， randomizing both the data and the features used by each base learner means that no single tree can overfi all the data。

 This is because no single tree sees all the data。 In fact， the trees underfi the data。

 They are high bias， but together， they can be very powerful predictors that are more stable than a regular single decision tree。

In addition， random forests are very scalable。 All the base learners they rely on can be trained in parallel using different processing units。

 even across many different servers。

![](img/2d24b0bd1731f667db3b40ff736329b1_2.png)

Finally， just like decision trees， random forest models need to be tuned to find the combination of hyperparameter settings that results in the best predictions。

After all， random forests are made up of many decision trees。

 and data professionals want them all to be as effective as possible。

