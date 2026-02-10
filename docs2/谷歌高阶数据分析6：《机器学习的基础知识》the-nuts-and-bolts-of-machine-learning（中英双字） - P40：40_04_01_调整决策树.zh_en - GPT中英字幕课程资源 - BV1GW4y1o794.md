# 谷歌高阶数据分析6：《机器学习的基础知识》the-nuts-and-bolts-of-machine-learning（中英双字） - P40：40_04_01_调整决策树.zh_en - GPT中英字幕课程资源 - BV1GW4y1o794

![](img/138fe5b53998a5f4fefc2cfffee833ab_0.png)

Recently， you've been exploring how to build a decision tree classifier model for many of the models you've worked with throughout this course。

 you used evaluation metrics such as F1 score to gauge their performance。

But throughout this section of the course， you'll be taking an extra step to gain some additional performance increases from your models。

A very popular and widely used technique to improve performance after creation is known as hyperparameter tuning。

Hyperparameters are parameters that can be set before the model is trained。

 they can be tuned to improve model performance directly affecting how the model is fit to the data。

Hyperparameter tuning is the process of adjusting the parameters to find the best values that will result in the most optimal model。

 Just like a musician tuning the strings on their guitar。

 the idea is to achieve balance and a beautiful result。For tree based modeling。

 there are many hyperparameters that can be tuned， and they can have a big impact on the model itself。

 You've actually already used one previously in this course when you worked with Ks。As you'll recall。

 when building a K means model， you set the value of k to produce different cluster results。

But when you change its value， you perform hyperparameter tuning。

One of the more basic hyperparameters for a decision tree is called max depth。

Setting this hyperparameter defines a limit of how long a decision tree can get。

The depth of a decision tree is the number of levels between the root node and the farthest node from the root node。

 with the root node itself being level 0。Consider our previous example。 This tree has three levels。

 The root node is level 0。 The nodes in the middle are level 1。

 and the leaf nodes all the way at the bottom are level 2。 So this tree has a depth of 2。 However。

 this decision tree has a depth of 4。Even though this decision tree isn't as filled out as the previous example。

 what matters is the distance of the farthest node from the root and whether it's a leaf node or a decision node。

This leads us back to max depth。When working with very large data sets。

 you could potentially create massive trees that are very deep。

But this isn't necessarily what you want for your model。

So setting a value for max depth can help reduce overfitting problems by limiting how deep the tree will go。

 Additionally， it can reduce the computational complexity of training and using the model in the first place。

For example， if you're finding that a decision tree has the same performance with a depth of 10 versus a depth of 100。

 you can set max depth to 10 and achieve the desired performance more quickly。

 Another very commonly used hyperparameter is called min samples leaf。

 This hyperparameter defines the minimum number of samples that must be contained in a leaf node。

 It means that split will only happen if there are enough samples in each of the result nodes to satisfy the required value。



![](img/138fe5b53998a5f4fefc2cfffee833ab_2.png)

For example， maybe part of the way down your tree， there's a decision node that currently has 10 samples。

 However， the min samples leaf hyperparameter is set to 6。

 There would be no way to split the data so that each leaf node has six samples and therefore no further split can take place。

There are other hyperparameters for decision trees that you'll learn， but first。

 let's explore finding the optimal values for the parameters。

 and here's where something called grid search is useful。

Grid search is a tool to confirm that a model achieves its intended purpose by systematically checking every combination of hyperparameters to identify which set produces the best results based on the selected metric。

So at the end， you'll have values that produce optimal results for your model when performing a grid search。

 the first step is to specify which parameters you want to tune and the set of values that you want to search over For example。

 Maybe we want to tune max step and min samples leaf。

 We would define potential values for each of these for max step。 We could check depths of 4，8，12。

20 and 30。For min's samples leaf， we could try 10，50 and 100。

 The algorithm will check every combination of values to see which pair has the best evaluation metrics。

 It would first check max depth of 4 with mins samples leaf of 10， then 50， then 100。

The algorithm would then check max step of 8 with min samples leaf of 10， then 50， then 100。

 This continues until every combination has been analyzed。Remember。

 you can try any values and any number of values during grid search if you believe the benefits are worth the cost of your computing time Com up。

 we'll put into practice many of the tree based modeling concepts you've learned so far。

All the way from constructing the tree to optimizing it and using it to make some classification predictions。

 looking forward to it。