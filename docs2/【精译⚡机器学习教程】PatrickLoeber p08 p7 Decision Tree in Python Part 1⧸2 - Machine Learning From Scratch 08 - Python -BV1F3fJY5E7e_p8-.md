# 【精译⚡机器学习教程】PatrickLoeber p08 p7 Decision Tree in Python Part 1⧸2 - Machine Learning From Scratch 08 - Python -BV1F3fJY5E7e_p8-

Hi everybody， Welcome to a new machine learning from Sc tutorial Today。

 we are going to implement a decision tree using only built in Python modules and nuy。

 A decision tree is a very simple but powerful concept。

 The idea is to build a tree that splits our data such that we have the best separation of our classes。

 A decision tree is also the basis for the very popular random forest model。

 which we will implement in the next tutorial， So I hope you will stick with me。😊，And as always。

 we will start with the theory first， so let's look at an example to understand the concept and the math behind the decision tree。

 let's say we want to predict if a person is walking or taking the bus to go to work and we have 10 observations or 1 samples with two different features so we have the feature if it is raining and then we have the feature how much time do they have。

And then we have the prediction or the class label， yes or no。

And now we want to build our tree that splits our data。

 so we put all the samples in the root node and then we apply a question。

 so we ask if it is raining and if the answer is yes。

 then we go to the right and we put all the samples where the answer is yes， so these three。



![](img/6111b16c758dda866060283b6ef2ffc2_1.png)

![](img/6111b16c758dda866060283b6ef2ffc2_2.png)

![](img/6111b16c758dda866060283b6ef2ffc2_3.png)

Into the right node。 And if the answer is no， then we go to the left and put all the other samples in the left node。



![](img/6111b16c758dda866060283b6ef2ffc2_5.png)

![](img/6111b16c758dda866060283b6ef2ffc2_6.png)

And here on the right， we can immediately say that the answer is no。 They don't walk。 So we put the。



![](img/6111b16c758dda866060283b6ef2ffc2_8.png)

Or return the class label 0。 And here on the left， we can further split the data and grow our tree。

 So we ask the next question。 So do they have more than 10 minutes and again。

 if the answer is yes and we go to the right and put all of the。



![](img/6111b16c758dda866060283b6ef2ffc2_10.png)

![](img/6111b16c758dda866060283b6ef2ffc2_11.png)

Samples where where they have more than 10 minutes in the right note and all the other ones in the left note and then again here we can say that the answer is yes or the class label is1 and here the class label is0。



![](img/6111b16c758dda866060283b6ef2ffc2_13.png)

And we could also stop with the growing here and return the most common class label。

 So here we can say that it's more likely that they will walk。Um。

 but we could also further split our data and but we don't want to grow our data too much because we don't want to overfit our data。

 but we also want to have a good prediction。

![](img/6111b16c758dda866060283b6ef2ffc2_15.png)

So this is the concept of how the decision tree works and now the only thing that we have to find out is at what at which node we want to apply which question so why do we ask for rain at first and not for the time and why do we ask for the time is greater than 10 and why don't we ask for if it's greater than5 or greater than 20。

 so this is the best the so-called best。

![](img/6111b16c758dda866060283b6ef2ffc2_17.png)

![](img/6111b16c758dda866060283b6ef2ffc2_18.png)

![](img/6111b16c758dda866060283b6ef2ffc2_19.png)

![](img/6111b16c758dda866060283b6ef2ffc2_20.png)

![](img/6111b16c758dda866060283b6ef2ffc2_21.png)

![](img/6111b16c758dda866060283b6ef2ffc2_22.png)

Split feature and best split value or split threshold that we want to find out。



![](img/6111b16c758dda866060283b6ef2ffc2_24.png)

So， the concept is to。At each note， we want to find the best split value and the best split threshold and store them。

And this is our training phase and later when we want to predict a new test sample and we start at the top and then we traverse our tree and apply the questions or the features that we stored and go to the left or to the right until we reach a leaf node。

 so a leaf node is the node at the bottom and then we apply the most common label that we store based on our test samples。



![](img/6111b16c758dda866060283b6ef2ffc2_26.png)

![](img/6111b16c758dda866060283b6ef2ffc2_27.png)

So this is the concept。 And now how do we find out the best split。 So for this， we need some math。

 So we calculate the entropy or and the entropy is also is the a measure for uncertainty。

 So the formula is minus， and then we have the sum of p of x times lock of p of x。

 and p of x is the number of occurrences over the total number of samples。

 So in our example we have 110 samples and five times the answer is or the label is 0 and five times the answer is。



![](img/6111b16c758dda866060283b6ef2ffc2_29.png)

![](img/6111b16c758dda866060283b6ef2ffc2_30.png)

![](img/6111b16c758dda866060283b6ef2ffc2_31.png)

1。

![](img/6111b16c758dda866060283b6ef2ffc2_33.png)

And then we have its， our entropy is minus5 over 10 times lock of 5 over 10 minus。

 And then we look at the next。Label， so one， again， we have five labels。

 so minus5 over 10 times lock of5 over 10。 And if you calculate this， then this is one。

 So this is the first possible case here in our in the first note we cannot make a prediction which are if it is one or0 because we have an equal amount of both。



![](img/6111b16c758dda866060283b6ef2ffc2_35.png)

Samples or both classes here。So one is the worst possible case and like here the entropy here would be0。

 so this is the best case here we are very certain that we have the class0。



![](img/6111b16c758dda866060283b6ef2ffc2_37.png)

And now so we calculate the entropy and then we split our data and calculate the entropy for our childs。

 and then we calculate how much information we gain through this split and this measure is actually really called information gain and this is calculated by the entropy of the parent minus weighted average of all the child entroies。

 so like in our example， we have the root note with our 10 observations。



![](img/6111b16c758dda866060283b6ef2ffc2_39.png)

![](img/6111b16c758dda866060283b6ef2ffc2_40.png)

And then on the left side， we have seven observations with here， two zeros。



![](img/6111b16c758dda866060283b6ef2ffc2_42.png)

And5 one。 And on the right side， we have three zeros。

 So our entropy is the entropy of the parent 7 over 10 times the entropy on the left side plus3 over 10 times the entropy of the right side。

 So this is the information gain。

![](img/6111b16c758dda866060283b6ef2ffc2_44.png)

![](img/6111b16c758dda866060283b6ef2ffc2_45.png)

![](img/6111b16c758dda866060283b6ef2ffc2_46.png)

And now we do a greedy search so we go over all the possible features and over all the possible feature values or thresholds。

 so for rain， we check if it's yes or no， or it means one or zero and if the answer and for the time feature。

 we check for 5， 10， 15， 20， 25 and 30 so we do a greedy search。



![](img/6111b16c758dda866060283b6ef2ffc2_48.png)

![](img/6111b16c758dda866060283b6ef2ffc2_49.png)

![](img/6111b16c758dda866060283b6ef2ffc2_50.png)

![](img/6111b16c758dda866060283b6ef2ffc2_51.png)

And then we store。Or select and store the best feature and the best threshold。 So this is the。



![](img/6111b16c758dda866060283b6ef2ffc2_53.png)

![](img/6111b16c758dda866060283b6ef2ffc2_54.png)

Concept， so let's look at the approach a little bit more in detail。 So first。

 we have the training phase where we want to build our tree。 So we start at a top note。

 And at each node， we select the best split based on the best information game。



![](img/6111b16c758dda866060283b6ef2ffc2_56.png)

And we do a greedy search， so we loop over all features and over all thresholds。

Then we saved the best split feature and split threshold at each node and we built the tree recursively。



![](img/6111b16c758dda866060283b6ef2ffc2_58.png)

And we also have to apply some stopping criteria to stop growing。 And in our example。

 we will use a maximum depth。

![](img/6111b16c758dda866060283b6ef2ffc2_60.png)

So for example， we say if the depth three is5， then we would stop。



![](img/6111b16c758dda866060283b6ef2ffc2_62.png)

And we use a minimum samples at a node。 So for example。

 we could say if we have less than five samples in a node then we don't split any further。

And if we have no more class distribution in a node like here。

 then we can no longer split because we only have class 0 labels here。

 So these are our stopping criteria that we need。 And then when we have a leaf node。

 then we store the most common class label of this node。 So here we store 0，1 and 0。



![](img/6111b16c758dda866060283b6ef2ffc2_64.png)

![](img/6111b16c758dda866060283b6ef2ffc2_65.png)

![](img/6111b16c758dda866060283b6ef2ffc2_66.png)

![](img/6111b16c758dda866060283b6ef2ffc2_67.png)

So this is our training phase and then later when we do the testing with new samples。

 then we traverse the tree and we also do this recursively。

 so we implement a function that calls itself。And at each note。

 we look at the best split feature of the test feature vector and go left or right， depending on if。

The value of this feature。Is smaller or equal than our threshold that we stored？

And then when we reach the leaf node or the bottom， we return the stored most common class label。

 So this is the concept of the。

![](img/6111b16c758dda866060283b6ef2ffc2_69.png)

Deci 3。 And now I think I will stop this video here。

 and we will continue in the next part or in the second part with the implementation。

 So see you then。

![](img/6111b16c758dda866060283b6ef2ffc2_71.png)

![](img/6111b16c758dda866060283b6ef2ffc2_72.png)