# 约翰霍普金斯大学《数据科学：统计和机器学习｜Data Science： Statistics and Machine Learning》中英字幕 - P101：20_随机森林.zh_en - GPT中英字幕课程资源 - BV1jsAAeNE3k

This lecture is about random forests， which you can think of as an extension to bagging for classification and regression trees。



![](img/955371e92a9bf5cd6464ae41741ecf0b_1.png)

The basic idea is very similar to bagging in the sense that we bootstrap samples。

 so we take a resample of our observed data and our training data。

And then we rebuild classification or regression trees on each of those bootstrap samples。

The one difference is that at each split when we split the data each time in the classification tree。

 we also bootstrap the variables， in other words only a subset of the variables is considered at each potential split。

This makes for a diverse set of potential trees that can be built。

 and so the idea is we grow a large number of trees。

 and then we either vote or average those trees in order to get the prediction for a new outcome。

The pros for this approach are that is quite accurate and along with boosting。

 it's one of the most widely used and highly accurate methods for prediction in competitions like Cagel。

 The cons are that it can be quite slow and it has to build a large number of trees。

 and it can be hard to interpret in the sense that you might have a large number of trees that are averaged together and those trees represent bootstrap samples with bootstrap nodes that can be a little bit complicated to understand。

It can also lead to a little bit of overfitting， which can be complicated by the fact that it's very hard to understand which trees are leading to that overfitting。

 and so it's very important to use cross validation when building granno forests。



![](img/955371e92a9bf5cd6464ae41741ecf0b_3.png)

Here's an example of how this works in practice so the idea is that you build a large number of trees where each tree is based on a bootstrap sample。

 so for example， this tree is built on a random subs sampleample of your data and this is a separate random subs sampleample of the data and this is a separate random subsetsle of the data and then at each node we allow a different subset of the variables to potentially contribute to the splits。



![](img/955371e92a9bf5cd6464ae41741ecf0b_5.png)

![](img/955371e92a9bf5cd6464ae41741ecf0b_6.png)

Then if we get a new observation， say this V observation here。

 we run that observation through tree1 and it ends up at this leaf down here at the bottom of that tree。

 and so it gets a particular prediction here。Then the next we take that same observation。

 we run it through the next tree and it goes down a slightly different leaf and it gets a slightly different set of predictions here。

 and finally we go down the third tree and we get an even different set of predictions。



![](img/955371e92a9bf5cd6464ae41741ecf0b_8.png)

Then what we do is we basically average those predictions together in order to get the predicted probabilities of each class across all the different trees。



![](img/955371e92a9bf5cd6464ae41741ecf0b_10.png)

So I'm going to show you an example of how this works， I'm going to load the IIS data in。

 and I'm going to use the GG plotot2 package for showing some plots。

I'm going to build a training set and a test set， again。

 building the data set only on the training set。

![](img/955371e92a9bf5cd6464ae41741ecf0b_12.png)

In the carrot package， I use the train function just like I've used for the other model building。

 I send it the training data set， and I tell it method equals RFf， which is the random forest method。

I'm also telling it to fit the outcome to be species and then to use any of the other predictor variables as potential predictors。

I'm setting prox equals true you'll see why I'm doing that in a minute because it produces a little bit of extra information that I can use when I'm building these model fits。

So here it tells me that I built the model and I've done bootstrap resampling and then I've tried a bunch of different tuning parameters。

 and so the tuning parameter in particular is the number of basically triess or number of repeated trees is going to build。



![](img/955371e92a9bf5cd6464ae41741ecf0b_14.png)

I can look at a specific tree in our final model fit using the get tree function。

 so I applied get tree here to our final model and I say I want the second tree out and this is what the tree looks like so each of these column or each of these rows corresponds to a particular split and so you can see what the left do of the tree is the right daughter of the tree。

 which variable we're splitting on， what's the value where that variable was split and then what the prediction is going to be out of that particular split。



![](img/955371e92a9bf5cd6464ae41741ecf0b_16.png)

You can use this centers information as well to see what the predictions would be or the center of the class predictions。

So what I've done here is I'm looking at two particular variables the pedal length and the pedal width so I've plotted pedal width on the X axis and pedal length on the y axis I then get the class centers so these are going be the centers for the predicted values so I'm going to send it the model fit and I'm going to give it this proOx variable which we asked for in the previous fitting and I'm going to tell it we're looking at the training data set and so that gives us the class centers so class centers will then we can then plot those to see where they fall on the data so now I've created the centers data set as well as the species data set。

And what I'm going to do is plot pedal width versus pal length。

 and I'm going to color it by species in the training data that's what I did with this Q plot command。

Then I'm going to add points on top of that that are the pedal width and pedal length。

Corresponding to the color being the species and now I'm using it from the IRSP which is the centers of the data set so what you can see is each dot here represents an observation and the x's show the column center or the observation centers for each of the different predictions so you can see that we predict the each species has a prediction for these two variables that's right in the center of the cloud points corresponding to that particular species。



![](img/955371e92a9bf5cd6464ae41741ecf0b_18.png)

You can then predict new values using the predict function。

 so you pass to predict our model fit and the testing data set。

And here I'm also setting a variable testing predict right。

 which is that we got the prediction right in the data set， in other words。

 our prediction is equal to the testing dataset species。

I can then make a table of our predictions versus the species to see what that variable would look like so I can see for example。

 I missed two values here with my random forest model。

 but overall get was highly accurate in the prediction I can then look and see which are the two that I missed and perhaps unsurprisingly you can see the two that I missed marked in red here are the two that in between two separate classes so remember there was one class up in this right corner and one class right here in the middle in this cloud and the two points that lie right on the border we were misclassified so you can kind of use this to explore and see where your prediction is doing well and where your prediction is doing poorly。



![](img/955371e92a9bf5cd6464ae41741ecf0b_20.png)

![](img/955371e92a9bf5cd6464ae41741ecf0b_21.png)

Renafors are usually one of the top performing algorithms。

 along with boosting in any prediction contests。 They're often difficult to interpret because of these multiple trees that were fitting。

 but they can be very accurate for a wide range of problems。

 You could check out the RFV function to make sure that cross validation is being performed。

 but the train function and carrot also handles that for you。For more information。

 you can read about random forest directly from the inventor here。

 the Wikipedia page for random For is also quite good。

 and the elements of statistical learning covers it as well。



![](img/955371e92a9bf5cd6464ae41741ecf0b_23.png)