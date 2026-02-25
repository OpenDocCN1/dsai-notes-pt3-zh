# 康奈尔大学《应用机器学习 CS 5787_ Applied Machine Learning 2020》中英字幕（deepseek p48 -48-Lecture 12. Part 4_ Random Forests.zh_en -BV12udzYvEFM_p48-

This is part 4 of Le 12 of Applied machinech learning。In this video。

 I am going to define a new tree based algorithm that is going to be different from the decision tree that we saw earlier。

 but it's also going to use the decision tree as a building block and the name of this algorithm is going to be the random forest。



![](img/59498f05dce46373602ba3e8036e89b9_1.png)

The random forest is going to be motivated by a problem that decision trees have。

 which is overfitting。And we saw previously one problem， one way to address overfitting。

 which is the bagging approach in which given a data x label data set of X and y。

 we repeatedly sample random subsets of this data， and then we fit different we fit the instances of the same。

 we run the same machine learning algorithm on each of these random subsets of the data to obtain a different predictive model。

 and then we add these models to an ensemble and then at prediction time。

 we return their average prediction。And even though each of these models may individually be overfitting the data。

 when they overfit the data， they will make errors outside the training set in random ways。

 and so if we average enough models， all these random overfitting errors should cancel out and give us a more stable prediction。



![](img/59498f05dce46373602ba3e8036e89b9_3.png)

We also saw earlier the decision tree algorithm and one way to define the decision tree algorithm is that we have a set of rules which partition the feature space into a set of regions each region is noted by R and then when we have a new training instance when we have a new input we predict we first see which region does x fall into。

 and then we predict the we output the prediction for this particular region。And in practice。

 these regions are obtained by applying。

![](img/59498f05dce46373602ba3e8036e89b9_5.png)

Decision rules which can be organized in a treelike structure。

 so here is an example of a tree over two variables here。

 depending on whether x1 is greater or less than T1。

 we're going to the left or to the right If we go to the right then we have another rule。

 then we go to the right again we have another rule and then we have these final two regions in total we have five regions in this decision tree。

 and this gives us a partition of the feature space which looks like this grid。



![](img/59498f05dce46373602ba3e8036e89b9_7.png)

Now let's investigate some properties of decision trees on a data set that we have seen earlier。

 which is the flower data set。

![](img/59498f05dce46373602ba3e8036e89b9_9.png)

Recall that in the flower data set we have data for about 150 flowers for each flower。

 we have various measurements that have been taken here in centimeters。



![](img/59498f05dce46373602ba3e8036e89b9_11.png)

![](img/59498f05dce46373602ba3e8036e89b9_12.png)

And。We can visualize this data set or well we can first look at the raw inputs which is a data frame with four feature columns and a target。

 the target takes one of three possible values depending on what the class is and we can visualize this data set in two dimensions by taking two of these dimensions and displaying each point as based on where it land according to these two measurements and you immediately see that you have clusters in the data here we have one type of flower and blue which is different from all the other flowers and then you also have two other classes which are more similar to each other but still different。

And these are three types of ir flower。 Each color here corresponds to a different type of ir flower。



![](img/59498f05dce46373602ba3e8036e89b9_14.png)

Let's see what happens if we train decision trees on this flower data set。



![](img/59498f05dce46373602ba3e8036e89b9_16.png)

I'm going to be reusing this code a lot and this is just boiler plate code for visualizing decision boundaries and decision regions over this iris data set。

 so this is not really important to follow but if you're interested in how we use Matpllib you can later go and revisit these。



![](img/59498f05dce46373602ba3e8036e89b9_18.png)

![](img/59498f05dce46373602ba3e8036e89b9_19.png)

![](img/59498f05dce46373602ba3e8036e89b9_20.png)

![](img/59498f05dce46373602ba3e8036e89b9_21.png)

![](img/59498f05dce46373602ba3e8036e89b9_22.png)

These visualizations， but this is just boiler plate code to generate figures。



![](img/59498f05dce46373602ba3e8036e89b9_24.png)

Let's now train a decision tree on this data set and visualize it。

Here I'm using the first two features from the data set， I create a decision treeclassifier。

 which I've imported earlier from PsyLn， I fit the data， I generate predictions。

 and then when I visualize them， I have this highly irregular region。

So this is a visualization of the predictions from the training set and you can see here that we do have these kinds of regions that we have defined earlier。

 so here this yellow rectangangle is a region， this also is a rectangle which is a region。

 it has this， you can immediately see this partition of the feature space of which I gave a toy example earlier。

And each。Partition is colored， each region in this partition is colored with the class of the prediction that is going to be making。



![](img/59498f05dce46373602ba3e8036e89b9_26.png)

![](img/59498f05dce46373602ba3e8036e89b9_27.png)

So there are two immediate problems that you can see with that decision boundary。

First is that it's highly non smooth and blocky。 It's fairly unlikely that， you know。

 like the the deportition between these two points is a straight line or here that it has this jagged structure and here is a straight line。

 it is probably some kind of。

![](img/59498f05dce46373602ba3e8036e89b9_29.png)

Line or curve here that is diagonal and this tree can only represent these very blocky regions that is one problem。

 but the bigger problem is that it clearly overfits the data。



![](img/59498f05dce46373602ba3e8036e89b9_31.png)

![](img/59498f05dce46373602ba3e8036e89b9_32.png)

You can see here， for example， it has found this one brown point and has decided to draw this really big brown block in the middle of the two other classes just to make sure that this is classified correctly this is an example of overfiing and here also it's learning a decision boundary that is way too precise for the kind of data that we have and its shape is very blocky and it's just not a sensible region。



![](img/59498f05dce46373602ba3e8036e89b9_34.png)

So this is an example of the kind of overfitting that a decision tree algorithm might exhibit。



![](img/59498f05dce46373602ba3e8036e89b9_36.png)

And we can look at this further by looking at how trees can overfit the data。



![](img/59498f05dce46373602ba3e8036e89b9_38.png)

And we can look at it from a high variance perspective。

So recall that in the previous video I what is high variance。

 I defined what it means for an algorithm to be high variance， and we say that of an algorithm。

 if it overfits the data and small perturbations of the training set result in big changes of the predictive model that it outputs。



![](img/59498f05dce46373602ba3e8036e89b9_40.png)

So overfitting in hi variances are synonyms， but hi varianceance in addition highlights the fact that small perturbations to the training set will cause big fluctuations in the predictive model。



![](img/59498f05dce46373602ba3e8036e89b9_42.png)

And one way in which we can visualize this is by taking random subsets of the data and training a different decision tree model on them。



![](img/59498f05dce46373602ba3e8036e89b9_44.png)

So here I am taking samples of 40 data points， so I'm taking 40 data points uniformly at random。

And I am training a different decision tree on each of them。

And you can see that each of these decision trees returns。A part that is。

Completely different and this is a dramatic example of the high varianceance problem if we change the data a little bit it or if we make changes to the data that still have here we still have the right structure。

 we still have enough， we should still be able to separate the blue and the other two classes but still these changes in the data。

 they create completely different predictions。

![](img/59498f05dce46373602ba3e8036e89b9_46.png)

So random forests are a way of addressing this overfitting and high variance problem using the technique of bagging which we have seen earlier。

And a random forest is nothing but a bagged decision tree。Or it's an ensemble of back decision trees。

 so it is bagging applied to a decision tree model。



![](img/59498f05dce46373602ba3e8036e89b9_48.png)

![](img/59498f05dce46373602ba3e8036e89b9_49.png)

If we were to instantiate our example with bagging， this is what we have。

 and I have just replaced the earlier definition of bagging by using decision tree as the model here。



![](img/59498f05dce46373602ba3e8036e89b9_51.png)

And。Random forests are really easy to implement just as bagging implement is easy to implement。

This is essentially a Python code that closely mirrors the episode pseudo code that I had in my earlier slide。



![](img/59498f05dce46373602ba3e8036e89b9_53.png)

Let's see what happens if we now run these random forests on the flower data set。



![](img/59498f05dce46373602ba3e8036e89b9_55.png)

So I have trained earlier in one of the earlier。Slides， there was a cell in which I implemented。

Random Fors training that creates a set of models， and now it can visualize their predictions on the flower data set。

In visualizing their predictions， I can go back here and I can look at- so here we have  300 models and each of them is sampling only 10 data points。



![](img/59498f05dce46373602ba3e8036e89b9_57.png)

So here I have the average of 300 models and each of them is trained on 10 random data points in the data。



![](img/59498f05dce46373602ba3e8036e89b9_59.png)

And now if I visualize this， I have one， I have a decision boundary that is much smoother than what I had before。

 and it looks much more natural here。 this kind of smooth curve is something that we would expect and here also have a smooth curve between the two classes。

 It's not as jaggy anymore， which is good。 and also it clearly overfits the data much less。

 This decision boundary is much more intuitive and it's no longer trying to put this one data point in its own class。

 This set of predictions is just much better behaved。

 It generalizes better and is just a more intuitive looking boundary。



![](img/59498f05dce46373602ba3e8036e89b9_61.png)

So to summarize， we defined random forests as a new kind of algorithm and because it's built on decision trees。

 it still can solve the regression classification problems。

And it uses this because it is simply bagging， obtain train on top of decision trees。

 our model family is still based on decision trees。

 and our objective and optimizer is the same that we used for the decision trees。



![](img/59498f05dce46373602ba3e8036e89b9_63.png)

So what are the pros and cons of random forests relative to other algorithms？

Since they're based on decision trees， they still retain a lot of。

Important benefits that decision trees have they don't require any scaling of the input。

 they continue they handle continuous and discrete features equally well。

 and they work equally well for classification and regression without modifying without really making a lot of changes to the algorithm。

And unlike decision trees， they are in practice quite often accurate。

 and so random forests are a very competitive class of algorithms and on many benchmarks that compare classical machine learning algorithms。

 random forests are they perform quite well on kggal competition。Competitions。

 random forests are a competitive model。Now， their disadvantages is that because they are bagging a large set of decision trees。

 they lose a lot of the advantages that these decision trees have in terms of interpretability。

So if we bootstrap together 300 decision trees， even though each decision tree might be interpretable。

 the average of 300 decision trees is no longer interpretable。And finally， decision sheet work。

 even though they're accurate models， they typically work better with features that have been preprocessed and if we're working with some kind of raw unstructured modalities such as images and audio。

 random horse would not work as well。

![](img/59498f05dce46373602ba3e8036e89b9_65.png)