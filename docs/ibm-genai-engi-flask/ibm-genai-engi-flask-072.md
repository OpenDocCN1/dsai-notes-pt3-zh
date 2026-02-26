# 072：IBM《生成式人工智能工程｜Falsk、生成式AI应用、数据分析、机器学习、Keras、架构和数据、NLP基础、transformer、微调、高级微调、RAG》 p72 14_构建决策树.zh_en -BV1NAq6Y9E7z_p72-

Hello and welcome in this video we'll be covering the process of building decision trees。

 so let's get started。

![](img/e8bfb11f2ed810644038f76ceba9a7b0_1.png)

Consider the drug data set again。The question is， how do we build a decision tree based on that data？



![](img/e8bfb11f2ed810644038f76ceba9a7b0_3.png)

Decision trees are built using recursive partitioning to classify the data。

Let's say we have 14 patients in our data。The algorithm chooses the most predictive feature to split the data on。

What is important in making a decision tree is to determine which attribute is the best or more predictive to split data based on the feature。

Let's say we pick cholesterol as the first attribute to split data。

It will split our data into two branches。As you can see， if the patient has high cholesterol。

 we cannot say with high confidence that drug B might be suitable for him。Also。

 if the patient's cholesterol is normal， we still don't have sufficient evidence or information to determine if either drug A or drug B is in fact suitable。

It is a sample of bad attribute selection for splitting data， so let's try another attribute。



![](img/e8bfb11f2ed810644038f76ceba9a7b0_5.png)

Again， we have our 14 cases。This time， we picked the sex attribute of patients。

It will split our data into two branches， male and female。As you can see， if the patient is female。

 we can say drug B might be suitable for her with high certainty。But if the patient is male。

 we don't have sufficient evidence or information to determine if drug A or drug B is suitable。

However， it is still a better choice in comparison with the cholesterol attribute because the result in the nodes are more pure。

 It means nodes that are either mostly drug A or drug B。

So we can say the sex attribute is more significant than cholesterol， or in other words。

 it's more predictive than the other attributes。Indeed。

 predictiveness is based on decrease in impurity of nodes。

We're looking for the best feature to decrease the impurity of patients in the leaves after splitting them up based on that feature。

 So the sex feature is a good candidate in the following case。

 because it almost found the pure patients。😊，Let's go one step further。For the male patient branch。

 we again test other attributes to split the subte。We test cholesterol again here。 As you can see。

 it results in even more pure leaves。So we can easily make a decision here。For example。

 if a patient is male and his cholesterol is high， we can certainly prescribe drug A。

 but if it is normal， we can prescribe drug B with high confidence。As you might notice。

 the choice of attribute to split data is very important。

 and it is all about purity of the leaves after the split。

A node in the tree is considered pure if in 100% of the cases。

 the nodes fall into a specific category of the target field。In fact。

 the method uses recursive partitioning to split the training records into segments by minimizing the impurity at each step。

Impurity of nodes is calculated by entropy of data in the node， so what is entropy？



![](img/e8bfb11f2ed810644038f76ceba9a7b0_7.png)

Entropy is the amount of information disorder or the amount of randomness in the data。

The entropy in the node depends on how much random data is in that node and is calculated for each node。

In decision trees， we're looking for trees that have the smallest entropy in their nodes。

The entropy is used to calculate the homogeneity of the samples in that node。

If the samples are completely homogeneous， the entropy is0， and if the samples are equally divided。

 it has an entropy of one。This means if all the data in a node are either drug A or drug B。

 then the entropy is0， but if half of the data or drug A and other half are B， then the entropy is1。

You can easily calculate the entropy of a node using the frequency table of the attribute through the entropy formula where P is for the proportion or ratio of a category。

 such as drug A or B。Please remember though， that you don't have to calculate these as it's easily calculated by the libraries or packages that you use。



![](img/e8bfb11f2ed810644038f76ceba9a7b0_9.png)

As an example， let's calculate the entropy of the data set before splitting it。

We have nine occurrences of drug B and five of drug A。

You can embed these numbers into the entropy formula to calculate the impurity of the target attribute before splitting it。

In this case， it is 0。94。So what is entropy after splitting？



![](img/e8bfb11f2ed810644038f76ceba9a7b0_11.png)

Now we can test different attributes to find the one with the most predictiveness。

 which results in two more pure branches。Let's first select the cholesterol of the patient and see how the data gets split based on its values。

For example， when it is normal， we have six for drug B and two for drug A。

We can calculate the entropy of this node based on the distribution of drug A and B， which is 0。

8 in this case。But when cholesterol is high， the data is split into three for drug B and three for drug A。

Calculating as entropy， we can see it would be 1。0。

We should go through all the attributes and calculate the entropy after the split。

 and then choose the best attribute。

![](img/e8bfb11f2ed810644038f76ceba9a7b0_13.png)

Okay， let's try another field。Let's choose the sex attribute for the next check。As you can see。

 when we use the sex attribute to split the data， when its value is female。

 we have three patients that responded to drug B and four patients that responded to drug A。

The entropy for this node is 0。98， which is not very promising。However。

 on the other side of the branch， when the value of the sex attribute is male。

 the result is more pure with six for drug B and only one for drug A。The entropy for this group is 0。

59。

![](img/e8bfb11f2ed810644038f76ceba9a7b0_15.png)

Now， the question is between the cholesterol and sex attributes， which one is a better choice。

Which one is better at the first attribute to divide the data set into two branches？Or。

 in other words， which attribute results in more pure nodes for our drugs？Or in which tree。

 do we have less entropy after splitting rather than before splitting。

The sex attribute with entropy of 0。98 and 0。59， or the cholesterol attribute， with entropy of 0。

81 and 1。0 in its branches。The answer is the tree with the higher information gain after splitting。



![](img/e8bfb11f2ed810644038f76ceba9a7b0_17.png)

So what is information gain？Information gain is the information that can increase the level of certainty after splitting。

It is the entropy of a tree before the split minus the weighted entropy after the split by an attribute。

We can think of information gain and entropy as opposites。

As entropy or the amount of randomness decreases， the information gain or amount of certainty increases and vice versa。

So， constructing a decision tree is all about finding attributes that return the highest information gain。



![](img/e8bfb11f2ed810644038f76ceba9a7b0_19.png)

Let's see how information gain is calculated for the sex attribute。As mentioned。

 the information gain is the entropy of the tree before the split minus the weighted entropy after the split。

The entropy of the tree before the split is 0。94。The portion of female patients is 7 out of 14。

 and his entropy is 0。985。 Also the portion of men is 7 out of 14。

 and the entropy of the male node is 0。592。The result of a square bracket here is the weighted entropy after the split。

So the information gain of the tree， if we use the sex attribute to split the data set， is 0。151。

As you can see， we will consider the entropy over the distribution of samples falling under each leaf node and will take a weighted average of that entropy weighted by the proportion of samples falling under that leaf。

We can calculate the information gain of the tree if we use cholesterol as well， it is 0。48。Now。

 the question is， which attribute is more suitable？Well， as mentioned。

 the tree with the higher information gain after splitting。This means the sex attribute。



![](img/e8bfb11f2ed810644038f76ceba9a7b0_21.png)

So we select the sex attribute as the first splitter。Now。

 what is the next attribute after branching by the sex attribute， Well， as you can guess。

 we should repeat the process for each branch and test each of the other attributes to continue to reach the most pure leaves。

 This is the way you build a decision tree。

![](img/e8bfb11f2ed810644038f76ceba9a7b0_23.png)

Thanks for watching。