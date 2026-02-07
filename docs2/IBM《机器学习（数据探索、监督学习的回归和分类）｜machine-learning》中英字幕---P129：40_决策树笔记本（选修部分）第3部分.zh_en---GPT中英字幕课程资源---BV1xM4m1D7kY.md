# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P129：40_决策树笔记本（选修部分）第3部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Welcome back for question number five， here we're going to turn to regression rather than classification using our decision trees。



![](img/93f83eff173f0af9c4c615eee22f1dfa_1.png)

So instead of trying to predict a class such as red or white wine。

 we will be predicting a continuous value here being the residual sugar。



![](img/93f83eff173f0af9c4c615eee22f1dfa_3.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_4.png)

We're going to be using our stratified shuffle split indices from earlier in order to create our train and test sets。



![](img/93f83eff173f0af9c4c615eee22f1dfa_6.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_7.png)

We're then going to use gridd search with cross validation to find out which hyperparameters perform best on our holdout set。

We're then going to measure the errors on both our training and test set predictions。

 and here we're going to use mean squared error rather than those classification error metrics that we just use because we're doing regression and we're predicting continuous values。

 We cannot run the F1 score or recall。 Those are specific to classification。

 So here we will be using the mean squared error。 and then we're just going to plot our actual versus predicted residual sugar。



![](img/93f83eff173f0af9c4c615eee22f1dfa_9.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_10.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_11.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_12.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_13.png)

So the first thing that we want to do。Is define what our actual feature columns are。

 and we say that those are going to be all taking our data。 columns， so all of our columns。

 except for residual sugar。

![](img/93f83eff173f0af9c4c615eee22f1dfa_15.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_16.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_17.png)

So that's our new set of feature columns， so Xx and data。coms， that's all of our columns。

 except for residual sugar。

![](img/93f83eff173f0af9c4c615eee22f1dfa_19.png)

We're then going to set x train equal to our original data。



![](img/93f83eff173f0af9c4c615eee22f1dfa_21.png)

Using our train index that we defined earlier using stratified shuffle split。



![](img/93f83eff173f0af9c4c615eee22f1dfa_23.png)

And then the columns are going to be each one of those feature columns that we just defined above。

 So everything besides with Israel sugar。 and then our wide train will be that same train index。

 So the same rows。

![](img/93f83eff173f0af9c4c615eee22f1dfa_25.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_26.png)

But now it's going to be predicting residual sugar rather than the color value。



![](img/93f83eff173f0af9c4c615eee22f1dfa_28.png)

So you run that in order to get our x train Y train for X test and Y test。

 those will be the same values， except now we're using the test indices rather than the train indices。



![](img/93f83eff173f0af9c4c615eee22f1dfa_30.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_31.png)

We're then going to import our decision tree aggressor。Now。

 this decision tree regressor will be very similar to the classifier。

The main difference will be that for our y variable。

 we have to ensure that that is a continuous value。



![](img/93f83eff173f0af9c4c615eee22f1dfa_33.png)

So we're first going to create a decision tree regressor， fit it on our X train and Y train。

 so this will be a separate DR， the reason why we fit this right away。



![](img/93f83eff173f0af9c4c615eee22f1dfa_35.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_36.png)

And so that when would create our parameter grid。

![](img/93f83eff173f0af9c4c615eee22f1dfa_38.png)

We can look at。For our max depth， when we're trying to figure out which features to loop through。

 we can look at the。

![](img/93f83eff173f0af9c4c615eee22f1dfa_40.png)

Max depth that we just learned by using this decision tree wreser without any pruning or regularization。

 So that will be really the maximum that it can come out to。



![](img/93f83eff173f0af9c4c615eee22f1dfa_42.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_43.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_44.png)

So we're arranging from one up until that max value counting by two。

 and then we're doing the same for feature importances。



![](img/93f83eff173f0af9c4c615eee22f1dfa_46.png)

Then we're going to pass in these parameters into our grid search CV as we did before。



![](img/93f83eff173f0af9c4c615eee22f1dfa_48.png)

So first we're going to cr our。

![](img/93f83eff173f0af9c4c615eee22f1dfa_50.png)

What type of model do we want， we're going to use a decision tree regressor here。



![](img/93f83eff173f0af9c4c615eee22f1dfa_52.png)

The only hyperparmeter we're passing in is that the random state is equal to 42。



![](img/93f83eff173f0af9c4c615eee22f1dfa_54.png)

Then for the parameter grid， we set that equal to that parameter grid that we just defined。



![](img/93f83eff173f0af9c4c615eee22f1dfa_56.png)

For our scoring。We have to be maximizing a value。

![](img/93f83eff173f0af9c4c615eee22f1dfa_58.png)

Normally， we want to minimize our mean squared error。

 So in order to allow us to be maximizing value while using our grid search。

 we say that we are maximizing the negative of mean squared error。



![](img/93f83eff173f0af9c4c615eee22f1dfa_60.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_61.png)

So in reality， we minimizing mean squared error， and then n jobs equals negative 1。

 we discussed this before that this will just allow us to paralyze across all of the power。

 all the functionality that's available on our computer。



![](img/93f83eff173f0af9c4c615eee22f1dfa_63.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_64.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_65.png)

Once we have that， we are then going to take that GR sugar and fit it to our X train and Y train。



![](img/93f83eff173f0af9c4c615eee22f1dfa_67.png)

And then as before， once that's fit， we have our best estimator。 that best estimator， as before。

 will have its tree with its note count， as well as its max depth。



![](img/93f83eff173f0af9c4c615eee22f1dfa_69.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_70.png)

And I can run this and I see that has a ton of nodes， 2743 nodes， and a max depth of 13。



![](img/93f83eff173f0af9c4c615eee22f1dfa_72.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_73.png)

Now we wanted to see what our mean squared error was， again。

 we can't use the same classification metrics that we just used before。



![](img/93f83eff173f0af9c4c615eee22f1dfa_75.png)

So first things first， we use our G R sugar to predict our actual X train。

 What would we predict on the set that we just trained on as well as the prediction on our X test。

 and we set that to Y train preed and Y test preed respectively。



![](img/93f83eff173f0af9c4c615eee22f1dfa_77.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_78.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_79.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_80.png)

We're then going to create a panda series。Where the indices are going to be train and test and the values are going to be the mean squared to error for our training set。

 as well as the mean squared error for our test set。



![](img/93f83eff173f0af9c4c615eee22f1dfa_82.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_83.png)

We set the column name equal to MSE。

![](img/93f83eff173f0af9c4c615eee22f1dfa_85.png)

We dump that into a data frame rather than using just a panda series。

 and then we call transpose the dot T will transpose it so that means square errors is now our row and train and test our column headers。



![](img/93f83eff173f0af9c4c615eee22f1dfa_87.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_88.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_89.png)

And we can see here that we did much better on our training set than we did on our test set than we did on our holdout set。

 and this will often be the case when you're working with continuous prediction using the decision tree regressor because we're getting that mean value once we split on that actual train set。



![](img/93f83eff173f0af9c4c615eee22f1dfa_91.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_92.png)

So。We also want to keep in mind here that we did make sure to evaluate and to tune our model according to our holdoutset。

 that was the key in regards to using grid search and using grid search in general。

 but we did see this discrepancy just in the way this model is built。



![](img/93f83eff173f0af9c4c615eee22f1dfa_94.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_95.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_96.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_97.png)

We're going to predict we're then going to plot the predicted values versus our actual values。



![](img/93f83eff173f0af9c4c615eee22f1dfa_99.png)

So we're going to as usual just initiate our figure as well as our bounding box。

 so here x is equal to PLT do axes， we have the bounding box in which our graph will actually lie。



![](img/93f83eff173f0af9c4c615eee22f1dfa_101.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_102.png)

We're then going to call PDd。 datata frame on。Test and predict。

 so this is initially a dictionary that we dump into a data frame。



![](img/93f83eff173f0af9c4c615eee22f1dfa_104.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_105.png)

Where the first value is going to be our actual values and our second column is going to be our predicted values。



![](img/93f83eff173f0af9c4c615eee22f1dfa_107.png)

And then just because it's easiest in regards to calling the ploting functionality with pandas。

 we set our index equal to test。

![](img/93f83eff173f0af9c4c615eee22f1dfa_109.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_110.png)

Once we do that， we have this object， which is a panda data frame we can just call dot plot。



![](img/93f83eff173f0af9c4c615eee22f1dfa_112.png)

Set the marker equal to O and the line style equal to blank。

 so that is just going to be a scatter plot， and we plotted on that bounding box that we initiated earlier。



![](img/93f83eff173f0af9c4c615eee22f1dfa_114.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_115.png)

And then we can just set our X label， our y label， and our x limits and y limits。

 according to the X limits and y limits of our actual predictions。



![](img/93f83eff173f0af9c4c615eee22f1dfa_117.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_118.png)

And our actual values as well。And then we see here on the X axis we have our test values。

 our actual values， and on the y axis， we have our predicted values。



![](img/93f83eff173f0af9c4c615eee22f1dfa_120.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_121.png)

And if they were perfectly aligned， if we got every single value exactly correct。

 they would be exactly on the diagonal because if the actual value is 15。

 our predicted value would be 15。 And same for 20 and 20。 And they would all be in a straight line。

 And we see here we were fairly close to being along that straight line。😊。



![](img/93f83eff173f0af9c4c615eee22f1dfa_123.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_124.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_125.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_126.png)

So the next part that we're going to do here is very cool。

Is that we're going to introduce how to actually plot out our decision tree。



![](img/93f83eff173f0af9c4c615eee22f1dfa_128.png)

A big part of what makes decision trees so powerful is the fact that they work along the lines of human logic。

 So you can imagine yourself trying to make a decision and going down the route if this part is true。

 then I can make my next decision。 And then if that's true， make my next decision。



![](img/93f83eff173f0af9c4c615eee22f1dfa_130.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_131.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_132.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_133.png)

And with that human logic in mind， you may want to dive under the hood and see how the computer was able to generate that。



![](img/93f83eff173f0af9c4c615eee22f1dfa_135.png)

Proxy of human logic in regards to coming to a certain conclusion。



![](img/93f83eff173f0af9c4c615eee22f1dfa_137.png)

So in order to do so， you will need certain libraries。

 you'll have to download the graph Vz that we see here， the pi dot plus。



![](img/93f83eff173f0af9c4c615eee22f1dfa_139.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_140.png)

And in order to do so， you can use PIP or Conda install。

 I would also make sure that you would look at the documentation before installing to ensure that you have all the prerequisites already installed on your computer。



![](img/93f83eff173f0af9c4c615eee22f1dfa_142.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_143.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_144.png)

So first we're going to need to。Import many of the libraries that are necessary。

 so we're going to import string IO here that's just so we can dump out the file as a string and we'll see this in a little bit。



![](img/93f83eff173f0af9c4c615eee22f1dfa_146.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_147.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_148.png)

We're going to。Import our image from iython dot display just to allow us to actually show the image within our Jupyter notebook。



![](img/93f83eff173f0af9c4c615eee22f1dfa_150.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_151.png)

Then from SK learned dotre， we're going to use the export graphs。

 which will allow us to take our learned model and export that into a file here we're going to just export that into this string IO。

 but that's the purpose of export graphs to export our decision tree into a file and then pi dot plus will take that file and allows us to render an actual image。



![](img/93f83eff173f0af9c4c615eee22f1dfa_153.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_154.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_155.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_156.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_157.png)

So the first thing that we want to do。Is set dot data equal to this string input output。



![](img/93f83eff173f0af9c4c615eee22f1dfa_159.png)

Variable is going to be just a blank string input output to start。

 I'm going to run this above so that we can break this down step by step。



![](img/93f83eff173f0af9c4c615eee22f1dfa_161.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_162.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_163.png)

And we can see that dot data is just going to be this string input output object。



![](img/93f83eff173f0af9c4c615eee22f1dfa_165.png)

We're then going to export our first decision tree from question number three。



![](img/93f83eff173f0af9c4c615eee22f1dfa_167.png)

Where we did no pruning。And we're setting our out file here， where do we want to export this to。

 we want to export it to this string variable that we just created to that dot data。



![](img/93f83eff173f0af9c4c615eee22f1dfa_169.png)

And then when we say filled equals true， that's going to be one of many different arguments that are available in regards to defining how this graph is actually going to look。



![](img/93f83eff173f0af9c4c615eee22f1dfa_171.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_172.png)

And you can dig into the documentation for what each of these do in regards toe providing the class names。

 the feature names where those splits are happening， which can all be useful Here。

 you see they're all set by default to none Se filled equals to true is just going to fill each one of the boxes。

 And the coloring of those boxes will be in accordance to the majority class。

 and we'll see this once we actually look at the graph。



![](img/93f83eff173f0af9c4c615eee22f1dfa_174.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_175.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_176.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_177.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_178.png)

So I'm going to run this。And once I run this， I've outputted into our dot data。



![](img/93f83eff173f0af9c4c615eee22f1dfa_180.png)

Our actual decision tree classifier。 so now it exists as a string。



![](img/93f83eff173f0af9c4c615eee22f1dfa_182.png)

And pi dot plus can get that。

![](img/93f83eff173f0af9c4c615eee22f1dfa_184.png)

Once we run this dot get value， I want to show you。

 this is be worn going to be a bit of a messy string coming out。



![](img/93f83eff173f0af9c4c615eee22f1dfa_186.png)

This string。Is going to define everything we need to know in order to render。



![](img/93f83eff173f0af9c4c615eee22f1dfa_188.png)

That decision tree， as an image。

![](img/93f83eff173f0af9c4c615eee22f1dfa_190.png)

So pi dot plus will take that。

![](img/93f83eff173f0af9c4c615eee22f1dfa_192.png)

And do we call from pi dot plus this function graph from dot data。

 we then pass in this crazy string that we just output using dot data。gevalue。



![](img/93f83eff173f0af9c4c615eee22f1dfa_194.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_195.png)

And now we have our graph， so our graph will be equal to the pi do plus rendered version of that string that we see above。



![](img/93f83eff173f0af9c4c615eee22f1dfa_197.png)

And then we can use graph。Which is our output from P up plus。

 has this functionality of right PNG to create a PG file， and will' pass in this file name here。



![](img/93f83eff173f0af9c4c615eee22f1dfa_199.png)

And then once we do that， we can pull that out， we have now saved that file name。

 we can now pull that out and see what that image actually looks like using image。

So I'm going to run this and it'll take just a second。

 and here we see our huge decision tree from question number3 with each one of the different splits。

 Again， whether or not it's orange or blue will tell you along that step what the majority classes。



![](img/93f83eff173f0af9c4c615eee22f1dfa_201.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_202.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_203.png)

And you see some of these stuff pretty high up， whereas towards the middle。

 it goes pretty far down in regards to the number of splits we actually have。



![](img/93f83eff173f0af9c4c615eee22f1dfa_205.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_206.png)

Now I'm going to do the same things for our pruned version of the tree。



![](img/93f83eff173f0af9c4c615eee22f1dfa_208.png)

And this might make it a little bit clearer， still a little bit difficult to see。

 but we do see here that we have a much prune tree。 We cut it off at max depth equal to。

 I don't remember what it was， but I believe seven。

 so that we have a much smaller tree a bit wider here。



![](img/93f83eff173f0af9c4c615eee22f1dfa_210.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_211.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_212.png)

Now I do want you to see exactly what this tree looks like， so I'm going to create a new classifier。



![](img/93f83eff173f0af9c4c615eee22f1dfa_214.png)

Decision。

![](img/93f83eff173f0af9c4c615eee22f1dfa_216.png)

Clasifier， and we're gonna pass in。We actually have to pull this in from above。



![](img/93f83eff173f0af9c4c615eee22f1dfa_218.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_219.png)

So we go back to where we first defined each one of our features。



![](img/93f83eff173f0af9c4c615eee22f1dfa_221.png)

And this is just for a quick example， this won't be in your actual notebook。



![](img/93f83eff173f0af9c4c615eee22f1dfa_223.png)

So we have our new decision tree reinstate that we're working with color。

 and then I also want this decision tree actually， let's put it down here。



![](img/93f83eff173f0af9c4c615eee22f1dfa_225.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_226.png)

To have a max depth。Equal to。3。

![](img/93f83eff173f0af9c4c615eee22f1dfa_228.png)

And then we'll call DT dot。Fit， and we will fit this on our X train。



![](img/93f83eff173f0af9c4c615eee22f1dfa_230.png)

Why train？

![](img/93f83eff173f0af9c4c615eee22f1dfa_232.png)

So now we have a new decision tree with a very small max depth。



![](img/93f83eff173f0af9c4c615eee22f1dfa_234.png)

And then I will use now that I've replaced what DT actually means， I'll run this again。

And now we can get a clear look at what this picture actually looks like。



![](img/93f83eff173f0af9c4c615eee22f1dfa_236.png)

And we see that we haven't defined what each one of the features are。

 We could have passed in the feature names as well， but we say for x 11， if it's less than 0。5。

 then we will have 1353 samples on one end and 4144 on the other end。 So almost the。



![](img/93f83eff173f0af9c4c615eee22f1dfa_238.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_239.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_240.png)

Well actually a perfect split here in regards to splitting these up and that's because I forgot to change what the feature columns are so color was in there it's probably splitting on the color between0 and1。

 but here you see how the actual split is occurring using our pictorial version of this decision tree。



![](img/93f83eff173f0af9c4c615eee22f1dfa_242.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_243.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_244.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_245.png)

So that closes out our discussion here on decision trees and the lab on decision trees。

 I'd very much welcome you guys to play around with what I just did in regards to changing the max depth。

 also ensure that your feature columns are changed because here the feature column is including the actual color。

 which is why it was performing so well and then you can actually look at how each one of these steps are actually creating splits along the way and again。

 you can pass in different arguments here in order to ensure that you'll be able to appropriately see where each one of these splits are happening。



![](img/93f83eff173f0af9c4c615eee22f1dfa_247.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_248.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_249.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_250.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_251.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_252.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_253.png)

All right， thank you and I look forward to seeing you back in lecture。



![](img/93f83eff173f0af9c4c615eee22f1dfa_255.png)

![](img/93f83eff173f0af9c4c615eee22f1dfa_256.png)