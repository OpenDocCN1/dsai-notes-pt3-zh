# IBM数据科学专业证书课程9：《Python机器学习课程（IBM）》machine-learning-with-python（中英字幕） - P15：14_决策树构建.zh_en - GPT中英字幕课程资源 - BV1Vp4y1V7n2

![](img/1f67179b146c9d478458d293cbaf4071_0.png)

Hello and welcome In this video we'll be covering the process of building decision trees。

 so let's get started。

![](img/1f67179b146c9d478458d293cbaf4071_2.png)

Consider the drug data set again。The question is， how do we build a decision tree based on that data set？

Decision trees are built using recursive partitioning to classify the data。



![](img/1f67179b146c9d478458d293cbaf4071_4.png)

Let's say we have 14 patients in our data set。

![](img/1f67179b146c9d478458d293cbaf4071_6.png)

The algorithm chooses the most predictive feature to split the data on。



![](img/1f67179b146c9d478458d293cbaf4071_8.png)

What is important in making a decision tree is to determine which attribute is the best or more predictive to split data based on the feature。



![](img/1f67179b146c9d478458d293cbaf4071_10.png)

![](img/1f67179b146c9d478458d293cbaf4071_11.png)

Let's say we pick cholesterol as the first attribute to split data。



![](img/1f67179b146c9d478458d293cbaf4071_13.png)

It will split our data into two branches。As you can see， if the patient has high cholesterol。

 we cannot say with high confidence that drug B might be suitable for him。



![](img/1f67179b146c9d478458d293cbaf4071_15.png)

![](img/1f67179b146c9d478458d293cbaf4071_16.png)

Also， if the patient's cholesterol is normal， we still don't have sufficient evidence or information to determine if either drug A or drug B is in fact suitable。



![](img/1f67179b146c9d478458d293cbaf4071_18.png)

![](img/1f67179b146c9d478458d293cbaf4071_19.png)

![](img/1f67179b146c9d478458d293cbaf4071_20.png)

It is a sample of bad attribute selection for splitting data。 So let's try another attribute。



![](img/1f67179b146c9d478458d293cbaf4071_22.png)

Again， we have our 14 cases。

![](img/1f67179b146c9d478458d293cbaf4071_24.png)

This time， we picked the sex attribute of patients。



![](img/1f67179b146c9d478458d293cbaf4071_26.png)

It will split our data into two branches， male and female。



![](img/1f67179b146c9d478458d293cbaf4071_28.png)

As you can see， if the patient is female， we can say drug B might be suitable for her with high certainty。

 but if the patient is male， we don't have sufficient evidence or information to determine if drug A or drug B is suitable。



![](img/1f67179b146c9d478458d293cbaf4071_30.png)

![](img/1f67179b146c9d478458d293cbaf4071_31.png)

![](img/1f67179b146c9d478458d293cbaf4071_32.png)

However， it is still a better choice in comparison with the cholesterol attribute because the result in the nodes are more pure。

 it means nodes that are either mostly drug A or drug B。



![](img/1f67179b146c9d478458d293cbaf4071_34.png)

![](img/1f67179b146c9d478458d293cbaf4071_35.png)

![](img/1f67179b146c9d478458d293cbaf4071_36.png)

So we can say the sex attribute is more significant than cholesterol， or in other words。

 it's more predictive than the other attributes。

![](img/1f67179b146c9d478458d293cbaf4071_38.png)

![](img/1f67179b146c9d478458d293cbaf4071_39.png)

![](img/1f67179b146c9d478458d293cbaf4071_40.png)

Indeed， predictiveness is based on decrease in impurity of nodes。



![](img/1f67179b146c9d478458d293cbaf4071_42.png)

We're looking for the best feature to decrease the impurity of patients in the leaves after splitting them up based on that feature。

 So the sex feature is a good candidate in the following case。

 because it almost found the pure patients。😊。

![](img/1f67179b146c9d478458d293cbaf4071_44.png)

![](img/1f67179b146c9d478458d293cbaf4071_45.png)

![](img/1f67179b146c9d478458d293cbaf4071_46.png)

Let's go one step further。

![](img/1f67179b146c9d478458d293cbaf4071_48.png)

For the male patient branch， we again test other attributes to split the sub tree。



![](img/1f67179b146c9d478458d293cbaf4071_50.png)

We test cholesterol again here。 As you can see， it results in even more pure leaves。



![](img/1f67179b146c9d478458d293cbaf4071_52.png)

![](img/1f67179b146c9d478458d293cbaf4071_53.png)

So we can easily make a decision here。For example， if a patient is male and his cholesterol is high。

 we can certainly prescribe drug A， but if it is normal。

 we can prescribe drug B with high confidence。

![](img/1f67179b146c9d478458d293cbaf4071_55.png)

![](img/1f67179b146c9d478458d293cbaf4071_56.png)

![](img/1f67179b146c9d478458d293cbaf4071_57.png)

As you might notice， the choice of attribute to split data is very important。

 and it is all about purity of the leaves after the split。



![](img/1f67179b146c9d478458d293cbaf4071_59.png)

![](img/1f67179b146c9d478458d293cbaf4071_60.png)

A node in the tree is considered pure if in 100% of the cases。

 the nodes fall into a specific category of the target field。



![](img/1f67179b146c9d478458d293cbaf4071_62.png)

![](img/1f67179b146c9d478458d293cbaf4071_63.png)

In fact， the method uses recursive partitioning to split the training records into segments by minimizing the impurity at each step。



![](img/1f67179b146c9d478458d293cbaf4071_65.png)

![](img/1f67179b146c9d478458d293cbaf4071_66.png)

Impurity of nodes is calculated by entropy of data in the node。 So what is entropy。



![](img/1f67179b146c9d478458d293cbaf4071_68.png)

![](img/1f67179b146c9d478458d293cbaf4071_69.png)

Entropy is the amount of information disorder or the amount of randomness in the data。

The entropy in the node depends on how much random data is in that node and is calculated for each node。



![](img/1f67179b146c9d478458d293cbaf4071_71.png)

In decision trees， we're looking for trees that have the smallest entropy in their nodes。

The entropy is used to calculate the homogeneity of the samples in that node。

If the samples are completely homogeneous， the entropy is0， and if the samples are equally divided。

 it has an entropy of one。This means if all the data in a node are either drug A or drug B。

 then the entropy is0， but if half of the data or drug A and other half are B， then the entropy is1。

You can easily calculate the entropy of a node using the frequency table of the attribute through the entropy formula where P is for the proportion or ratio of a category。

 such as drug A or B。Please remember though， that you don't have to calculate these as it's easily calculated by the libraries or packages that you use。

As an example， let's calculate the entropy of the data set before splitting it。

We have nine occurrences of drug B and five of drug A。

You can embed these numbers into the entropy formula to calculate the impurity of the target attribute before splitting it。

In this case， it is 0。94， so what is entropy after splitting？

Now we can test different attributes to find the one with the most predictiveness。

 which results in two more pure branches。Let's first select the cholesterol of the patient and see how the data gets split based on its values。

For example， when it is normal， we have six for drug B and two for drug A。

We can calculate the entropy of this node based on the distribution of drug A and B， which is 0。

8 in this case。But when cholesterol is high， the data is split into three for drug B and three for drug A。

Calculating its entropy， we can see it would be 1。0。

We should go through all the attributes and calculate the entropy after the split and then choose the best attribute。

Okay， let's try another field。Let's choose the sex attribute for the next check。As you can see。

 when we use the sex attribute to split the data， when its value is female。

 we have three patients that responded to drug B and four patients that responded to drug A。

The entropy for this node is 0。98， which is not very promising。However。

 on the other side of the branch， when the value of the sex attribute is male。

 the result is more pure with six for drug B and only one for drug A。The entropy for this group is 0。

59。Now， the question is， between the cholesterol and sex attributes， which one is a better choice？

Which one is better at the first attribute to divide the data set into two branches？

Or in other words， which attribute results in more pure nodes for our drugs？Or in which tree。

 do we have less entropy after splitting rather than before splitting。

The sex attribute with entropy of 0。98 and 0。59， or the cholesterol attribute， with entropy of 0。

81 and 1。0 in its branches。The answer is the tree with the higher information gain after splitting。

So what is information gain？Information gain is the information that can increase the level of certainty after splitting。



![](img/1f67179b146c9d478458d293cbaf4071_73.png)

It is the entropy of a tree before the split minus the weighted entropy after the split by an attribute。

We can think of information gain and entropy as opposites。

As entropy or the amount of randomness decreases， the information gain or amount of certainty increases and vice versa。

So， constructing a decision tree is all about finding attributes that return the highest information gain。

Let's see how information gain is calculated for the sex attribute。As mentioned。

 the information gain is the entropy of the tree before the split minus the weighted entropy after the split。

The entropy of the tree before the split is 0。94。The portion of female patients is 7 out of 14。

 and its entropy is 0。985。 Also the portion of men is 7 out of 14 and the entropy of the male node is 0。

592。The result of a square bracket here is the weighted entropy after the split。

So the information gain of the tree， if we use the sex attribute to split the data set， is 0。151。

As you can see， we will consider the entropy over the distribution of samples falling under each leaf node and will take a weighted average of that entropy weighted by the proportion of samples falling under that leaf。

We can calculate the information gain of the tree if we use cholesterol as well。 It is 0。48。 Now。

 the question is， which attribute is more suitable。Well， as mentioned。

 the tree with the higher information gain after splitting。This means the sex attribute。

So we select the sex attribute as the first splitter。



![](img/1f67179b146c9d478458d293cbaf4071_75.png)

Now， what is the next attribute after branching by the sex attribute， Well， as you can guess。

 we should repeat the process for each branch and test each of the other attributes to continue to reach the most pure leaves。

 This is the way you build a decision tree。

![](img/1f67179b146c9d478458d293cbaf4071_77.png)

![](img/1f67179b146c9d478458d293cbaf4071_78.png)

![](img/1f67179b146c9d478458d293cbaf4071_79.png)

![](img/1f67179b146c9d478458d293cbaf4071_80.png)

Thanks for watching。