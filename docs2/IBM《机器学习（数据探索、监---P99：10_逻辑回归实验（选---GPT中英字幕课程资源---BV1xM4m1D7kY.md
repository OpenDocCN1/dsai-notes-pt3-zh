# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P99：10_逻辑回归实验（选修部分）第2部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/916255a354808a4764b2e500da6f91ce_0.png)

Now let's pick up where we left off with question number three here we're going to split the data into train and test data sets。

 and this can be done using any method， but we're going to want to consider using the SKar stratified shuffle split here in order to ensure that we maintain the same ratio of our predictor class in both our train and test set and regardless of methods used to split the data。

 you should afterwards compare the ratio of classes in both our train and test splits。



![](img/916255a354808a4764b2e500da6f91ce_2.png)

![](img/916255a354808a4764b2e500da6f91ce_3.png)

![](img/916255a354808a4764b2e500da6f91ce_4.png)

![](img/916255a354808a4764b2e500da6f91ce_5.png)

![](img/916255a354808a4764b2e500da6f91ce_6.png)

![](img/916255a354808a4764b2e500da6f91ce_7.png)

So here we start by importing our from model selection， our stratified shuffel split。



![](img/916255a354808a4764b2e500da6f91ce_9.png)

We're then going to create our stratified shuffle split object similar to how we've done with different escalear objects。

 and we're going to pass in the different arguments in regards to this specific stratified shuffle split。



![](img/916255a354808a4764b2e500da6f91ce_11.png)

![](img/916255a354808a4764b2e500da6f91ce_12.png)

We only want to create one split we're just going to split into one train and one test set if you want to do more。

 we can increase the number of splits。 We want our test size to be 0。

3 so 30% will be our holdout set the other 70% is going to be what we train on and to ensure that you as well as what I'm showing you here will be the same results we're using a random state here being equal to 42 generally doesn't matter as long as they have the same across both users。



![](img/916255a354808a4764b2e500da6f91ce_14.png)

![](img/916255a354808a4764b2e500da6f91ce_15.png)

![](img/916255a354808a4764b2e500da6f91ce_16.png)

![](img/916255a354808a4764b2e500da6f91ce_17.png)

![](img/916255a354808a4764b2e500da6f91ce_18.png)

![](img/916255a354808a4764b2e500da6f91ce_19.png)

We then are going to take that stratified shuffel split that we just defined。



![](img/916255a354808a4764b2e500da6f91ce_21.png)

And call the split。That split method and then pass in both our x values， so our features。

 as well as our y values， the value we're trying to predict data dot activity。



![](img/916255a354808a4764b2e500da6f91ce_23.png)

And when we create this object， and I'll pull this out， as I've done before。

 we are actually creating a generator object。

![](img/916255a354808a4764b2e500da6f91ce_25.png)

![](img/916255a354808a4764b2e500da6f91ce_26.png)

So we can call next。 So if we look at just。

![](img/916255a354808a4764b2e500da6f91ce_28.png)

This object here。We'll see that when I run this， we see it outputs a generator object。

 and what I call next on this object， it's just going to output。



![](img/916255a354808a4764b2e500da6f91ce_30.png)

![](img/916255a354808a4764b2e500da6f91ce_31.png)

And we'll see this in just a second。

![](img/916255a354808a4764b2e500da6f91ce_33.png)

Both the train and test indices。 So we'll end up with。



![](img/916255a354808a4764b2e500da6f91ce_35.png)

Train indices and test indices with the train index being first and the test index being second。



![](img/916255a354808a4764b2e500da6f91ce_37.png)

And then we can just use dot Lo in order to specify that we want given our original data set。



![](img/916255a354808a4764b2e500da6f91ce_39.png)

We want each one of the rows that were specified in our split。



![](img/916255a354808a4764b2e500da6f91ce_41.png)

As well as every single one of the different columns。Of our feature columns that is。

 and then for our Y train， so we have our X train for our Y train。

 we just use that same index except now we are specifying that we want the activity column and not all of our feature columns。



![](img/916255a354808a4764b2e500da6f91ce_43.png)

![](img/916255a354808a4764b2e500da6f91ce_44.png)

And then we do the same thing for each one of our test indices。



![](img/916255a354808a4764b2e500da6f91ce_46.png)

So with that， we've defined our X train， our Y train， our X test， and our Y test。



![](img/916255a354808a4764b2e500da6f91ce_48.png)

We can then check。

![](img/916255a354808a4764b2e500da6f91ce_50.png)

What our value counts are for Y train， When we call normalizedize equals true within our value counts is they give us our proportion rather than the actual counts。

 and that will allow us to compare both our Y train and our Y test。

 And we see that they're fairly similar for each one of the difference。



![](img/916255a354808a4764b2e500da6f91ce_52.png)

![](img/916255a354808a4764b2e500da6f91ce_53.png)

![](img/916255a354808a4764b2e500da6f91ce_54.png)

Activities which are labeled by integers that we want to predict。



![](img/916255a354808a4764b2e500da6f91ce_56.png)

![](img/916255a354808a4764b2e500da6f91ce_57.png)

Now moving on to question4， we're going to fit a logistic regression model without any regularization to start using all of our features。

 remember we have 561 features so it's quite a large feature set and we mention here that we want to ensure that we read the documentation about fitting a multiclass model because the way that the coefficients are going to spinit out are going to be a little bit different and I'll talk to that as we look at the coefficients themselves as well。



![](img/916255a354808a4764b2e500da6f91ce_59.png)

![](img/916255a354808a4764b2e500da6f91ce_60.png)

![](img/916255a354808a4764b2e500da6f91ce_61.png)

![](img/916255a354808a4764b2e500da6f91ce_62.png)

![](img/916255a354808a4764b2e500da6f91ce_63.png)

![](img/916255a354808a4764b2e500da6f91ce_64.png)

And then we're going to use cross validation to determine the hyperparameters that will fit models using L1 and L2 regularization。

 so just as we've done in the past， and as we'll continue to do in the future。

 we'll find the right hyperparameters in order to ensure that our out of sample prediction is optimized in terms of its error。



![](img/916255a354808a4764b2e500da6f91ce_66.png)

![](img/916255a354808a4764b2e500da6f91ce_67.png)

![](img/916255a354808a4764b2e500da6f91ce_68.png)

![](img/916255a354808a4764b2e500da6f91ce_69.png)

And then we're going to store each one of these models and again we want to ensure that we understand the multiclass models。

 the solvers and the regulars that all come into play。

 and we'll discuss this as we go through each one of the models。



![](img/916255a354808a4764b2e500da6f91ce_71.png)

![](img/916255a354808a4764b2e500da6f91ce_72.png)

![](img/916255a354808a4764b2e500da6f91ce_73.png)

So the first thing that we do is fit our regular logistic regression model。

 which is just going to have no extra hyperparameter， no regularization。

 and we see here that we pass the solver Lib linear。



![](img/916255a354808a4764b2e500da6f91ce_75.png)

![](img/916255a354808a4764b2e500da6f91ce_76.png)

![](img/916255a354808a4764b2e500da6f91ce_77.png)

And the only thing you need to know there's different solvers that optimize for different versions and you can look at the documentation What we need to know here is that we're using here the one versus the rest that we talked about during lecture。

 which is just trying to predict a certain class versus all the rest and then another class versus all the rest。

 so we're going to do that six different times for each one of the six different classes。

 and Lib linearar is just one of the ways to optimize when we're using one versus rest。



![](img/916255a354808a4764b2e500da6f91ce_79.png)

![](img/916255a354808a4764b2e500da6f91ce_80.png)

![](img/916255a354808a4764b2e500da6f91ce_81.png)

![](img/916255a354808a4764b2e500da6f91ce_82.png)

![](img/916255a354808a4764b2e500da6f91ce_83.png)

![](img/916255a354808a4764b2e500da6f91ce_84.png)

So we're specifying that for our logistic regression。

 and then we're fitting that model that we're going to be initiating and fitting in one step。



![](img/916255a354808a4764b2e500da6f91ce_86.png)

![](img/916255a354808a4764b2e500da6f91ce_87.png)

Using our X train and our Y train。

![](img/916255a354808a4764b2e500da6f91ce_89.png)

So we run that that may take just a second， but not quite as long as what we're about to do here。

 I'm going to start talking about this next step， you see that the step before just finished running。



![](img/916255a354808a4764b2e500da6f91ce_91.png)

![](img/916255a354808a4764b2e500da6f91ce_92.png)

Now we're going to import the logistic regression CV， which is that cross validation method。

 we talked about it a bit in lecture and similar to grid search CV。

 which we've learned about earlier that allow us to loop through many different hyperparameters。



![](img/916255a354808a4764b2e500da6f91ce_94.png)

![](img/916255a354808a4764b2e500da6f91ce_95.png)

![](img/916255a354808a4764b2e500da6f91ce_96.png)

And what we're going to do is use that logistic regression CV。



![](img/916255a354808a4764b2e500da6f91ce_98.png)

The hyperparmeters that we generally want to look through are the different type of penalties we're just going to specify L1 here and the different C values and C is similar to lambda except that it's the inverse here。



![](img/916255a354808a4764b2e500da6f91ce_100.png)

![](img/916255a354808a4764b2e500da6f91ce_101.png)

嗯。So we're going to say C's equal 10， which is just going to be the default and we can look at the documentation here。



![](img/916255a354808a4764b2e500da6f91ce_103.png)

![](img/916255a354808a4764b2e500da6f91ce_104.png)

Let me just run。Oh we didn't import it yet， but once we import it， this is going to take a second。

 but what we allow here when we do the default of C's， which is 10。

 is that's going to check it across 10 different default values of that C value and then we can optimize from there。



![](img/916255a354808a4764b2e500da6f91ce_106.png)

![](img/916255a354808a4764b2e500da6f91ce_107.png)

So I'm going to run this and again we're using the solver equals Lib linear Our penalty here is equal to the L1 penalty。

 I do want you to notice that this will take a long time I'm going to run pause and then we'll come back to it it may take about7 to8 minutes depending on the strength of your computer and the CPU power that you have available but this is just to highlight how long certain models can end up taking and how you want to ensure that you optimize those values。

 so I'm going to run this now and we'll check back in as soon as it's done running。



![](img/916255a354808a4764b2e500da6f91ce_109.png)

![](img/916255a354808a4764b2e500da6f91ce_110.png)

![](img/916255a354808a4764b2e500da6f91ce_111.png)

![](img/916255a354808a4764b2e500da6f91ce_112.png)

![](img/916255a354808a4764b2e500da6f91ce_113.png)

![](img/916255a354808a4764b2e500da6f91ce_114.png)

![](img/916255a354808a4764b2e500da6f91ce_115.png)

![](img/916255a354808a4764b2e500da6f91ce_116.png)

So now we're back and hopefully for you that's just a cut to where we are now and I have gone ahead and fit both the logistic regression with an L1 penalty as well as going ahead and running it for the L2 penalty that one should be a little bit faster as we've discussed before。

 generally speaking the L2 penalty tends to run a bit faster just because of how it works under the hood and we have also optimized using this crossval method to ensure that we are also choosing the appropriate Cs with our four different holdout sets right we have CV equal to4 so we're having four different holdout sets to see which values of C will optimize best on some holdout set。



![](img/916255a354808a4764b2e500da6f91ce_118.png)

![](img/916255a354808a4764b2e500da6f91ce_119.png)

![](img/916255a354808a4764b2e500da6f91ce_120.png)

![](img/916255a354808a4764b2e500da6f91ce_121.png)

![](img/916255a354808a4764b2e500da6f91ce_122.png)

![](img/916255a354808a4764b2e500da6f91ce_123.png)

![](img/916255a354808a4764b2e500da6f91ce_124.png)

So now we want to compare the magnitude of each of the coefficients for each of the models that we came up with。

 and we're using the one versus rest fitting in terms of how we are using multilabel classification and what that's going to mean is that when we come up with our coefficients。

 if we think about the models that we're trying to create we are trying to create models that will predict a certain class versus the rest of the classes。

 So standing versus not standing， sitting versus not sitting so on and so forth。



![](img/916255a354808a4764b2e500da6f91ce_126.png)

![](img/916255a354808a4764b2e500da6f91ce_127.png)

![](img/916255a354808a4764b2e500da6f91ce_128.png)

![](img/916255a354808a4764b2e500da6f91ce_129.png)

![](img/916255a354808a4764b2e500da6f91ce_130.png)

![](img/916255a354808a4764b2e500da6f91ce_131.png)

![](img/916255a354808a4764b2e500da6f91ce_132.png)

So each one of these coefficients will have to show up for each one of these one versus rest models。

 and they will define for those log odds， for each coefficient。

 how much are we increasing the odds of standing versus not standing。

 sitting versus not sitting and so on so that each one of these coefficients will be specific to each one of our different labels。



![](img/916255a354808a4764b2e500da6f91ce_134.png)

![](img/916255a354808a4764b2e500da6f91ce_135.png)

![](img/916255a354808a4764b2e500da6f91ce_136.png)

![](img/916255a354808a4764b2e500da6f91ce_137.png)

![](img/916255a354808a4764b2e500da6f91ce_138.png)

So the first thing that we're going to do is initiate an empty list。



![](img/916255a354808a4764b2e500da6f91ce_140.png)

We're then going to create these coF labels and COF models。

 we're going to use that to loop through as we see right here。

 and we're going to zip those two together。

![](img/916255a354808a4764b2e500da6f91ce_142.png)

![](img/916255a354808a4764b2e500da6f91ce_143.png)

And when we zip those two together， we can access both the label and the model at each step。

 so it'll be LR as a string and then the actual LR model that we created earlier。

 or going to be the first thing that we reach within our for loop。



![](img/916255a354808a4764b2e500da6f91ce_145.png)

![](img/916255a354808a4764b2e500da6f91ce_146.png)

We're then going to pull out our coefficients， so just from our mod， our mod being again。

 just signifying what we have here in the for loop， we're going to pull out those coefficients。



![](img/916255a354808a4764b2e500da6f91ce_148.png)

![](img/916255a354808a4764b2e500da6f91ce_149.png)

We're then going to create a multilevel index， so that multilevel index will be on top of our data frame and we'll see what that looks like once I print this out。

 but that's going to have our different levels。 So again this is a multilevel index where the first level is going to be the name of the actual model。



![](img/916255a354808a4764b2e500da6f91ce_151.png)

![](img/916255a354808a4764b2e500da6f91ce_152.png)

![](img/916255a354808a4764b2e500da6f91ce_153.png)

![](img/916255a354808a4764b2e500da6f91ce_154.png)

And then we're going to also highlight these numbers 0，1，2，3，4，5。

 which is just going to say the coefficients for each one of these versus the rest。 right again。

 we have replaced each one of our labels with integers。

 And now those integers will be used to say0 versus the rest so that could be sitting versus the rest。

 standing versus the rest and so on。

![](img/916255a354808a4764b2e500da6f91ce_156.png)

![](img/916255a354808a4764b2e500da6f91ce_157.png)

![](img/916255a354808a4764b2e500da6f91ce_158.png)

![](img/916255a354808a4764b2e500da6f91ce_159.png)

![](img/916255a354808a4764b2e500da6f91ce_160.png)

And then in regards to codes， all that means is how do we want these ordered， so it's going to be0。

0 together，0 one together， that first one being all zeros because we only have one label and then that's tied to each one of these different numbers and we'll see this with the labeling as well。



![](img/916255a354808a4764b2e500da6f91ce_162.png)

![](img/916255a354808a4764b2e500da6f91ce_163.png)

![](img/916255a354808a4764b2e500da6f91ce_164.png)

We're then going to take our coefficient list and append onto that list a data frame。



![](img/916255a354808a4764b2e500da6f91ce_166.png)

Of our coefficients that we have here， we're going to transpose them so that they're a column and then the columns names are going to be that coF label。

 which is our multi index label that we just created。



![](img/916255a354808a4764b2e500da6f91ce_168.png)

![](img/916255a354808a4764b2e500da6f91ce_169.png)

![](img/916255a354808a4764b2e500da6f91ce_170.png)

And then once we run through that for loop。We are then going to concatenate each one of these different coefficient lists。

 we're going to concatenate the entire list together across each one of the columns。



![](img/916255a354808a4764b2e500da6f91ce_172.png)

![](img/916255a354808a4764b2e500da6f91ce_173.png)

![](img/916255a354808a4764b2e500da6f91ce_174.png)

So I'm going to run this。And again， walk through what we just discussed。 This is just a sample。

 We should have a value These， each one of these numbers is going to be a different coefficient。



![](img/916255a354808a4764b2e500da6f91ce_176.png)

And each one of these should add。 there should be about 561。 I believe was the number。

 We can look at the coefficients。

![](img/916255a354808a4764b2e500da6f91ce_178.png)

![](img/916255a354808a4764b2e500da6f91ce_179.png)

The shape。And we see that 561 rows for each one of the different coefficients。

 And then each one of those coefficients are going to come with a number。

 some numerical value to define for that coefficient for0， which could be sitting。

 is going to decrease that odds versus the rest of the different values。

 and then increase for one increase for two and so on。

 So we see the effect of each one of these coefficients for each one of these one versus rest models。



![](img/916255a354808a4764b2e500da6f91ce_181.png)

![](img/916255a354808a4764b2e500da6f91ce_182.png)

![](img/916255a354808a4764b2e500da6f91ce_183.png)

![](img/916255a354808a4764b2e500da6f91ce_184.png)

![](img/916255a354808a4764b2e500da6f91ce_185.png)

![](img/916255a354808a4764b2e500da6f91ce_186.png)

![](img/916255a354808a4764b2e500da6f91ce_187.png)

Now we're going to plot all of these models and again， the code is a bit complex。

 so we're going to walk through step by step so that we understand what we're actually doing here。



![](img/916255a354808a4764b2e500da6f91ce_189.png)

![](img/916255a354808a4764b2e500da6f91ce_190.png)

We're going to create our subplots。Using P L T dot subplots， we're going to initiate the figure。

 And then also this ax list。 and that ax list should be。



![](img/916255a354808a4764b2e500da6f91ce_192.png)

![](img/916255a354808a4764b2e500da6f91ce_193.png)

Three rows by two columns， so there should be six different bounding boxes within which we can plot。



![](img/916255a354808a4764b2e500da6f91ce_195.png)

We're then going to flatten that out just so it's easier to run a for loop through that a list。

 So we're going to end up with the first one， the second one， the third one。

 each one of those being a bounding box。 So we'll have six bounding boxes。



![](img/916255a354808a4764b2e500da6f91ce_197.png)

![](img/916255a354808a4764b2e500da6f91ce_198.png)

![](img/916255a354808a4764b2e500da6f91ce_199.png)

And then we just set the size here using that figure object to make sure that we have the size that we want for each one of these。

 for the entire figure。

![](img/916255a354808a4764b2e500da6f91ce_201.png)

![](img/916255a354808a4764b2e500da6f91ce_202.png)

We're then going to enumerate the ax list。 Now， the ax list currently is an object that is going to be the six bounding boxes in which all of our different plots are going to be contained。



![](img/916255a354808a4764b2e500da6f91ce_204.png)

![](img/916255a354808a4764b2e500da6f91ce_205.png)

And our Lo， because we're a en nuerating ax list。

![](img/916255a354808a4764b2e500da6f91ce_207.png)

That a list is going to come with numerical value that's going to be the lo， so it'll be 0，1，2，3，4，5。

6 with the related x with that related bounding box。



![](img/916255a354808a4764b2e500da6f91ce_209.png)

![](img/916255a354808a4764b2e500da6f91ce_210.png)

![](img/916255a354808a4764b2e500da6f91ce_211.png)

We're then going to take the coefficients。Which is。



![](img/916255a354808a4764b2e500da6f91ce_213.png)

What we had up here， this is just a sample of it， but it's going to be that 561 row by 18 column data frame。



![](img/916255a354808a4764b2e500da6f91ce_215.png)

And we're going to access certain values， you see here we have that multiple index where we have linear regression as that top index or logistic regression。

 excuse me， and then the L1 penalty and the L2 penalty。

 and then below that we have each one of the different models one versus the rest。



![](img/916255a354808a4764b2e500da6f91ce_217.png)

![](img/916255a354808a4764b2e500da6f91ce_218.png)

![](img/916255a354808a4764b2e500da6f91ce_219.png)

![](img/916255a354808a4764b2e500da6f91ce_220.png)

We're going to say that we want to locate。

![](img/916255a354808a4764b2e500da6f91ce_222.png)

Here we're using the lo value that we used for enumerate。

 so at the first value that's going to be zero。

![](img/916255a354808a4764b2e500da6f91ce_224.png)

So we're going to be locating each one of these different zeros。

 so we have a zero here and a zero here for L1 and a zero here for L2。



![](img/916255a354808a4764b2e500da6f91ce_226.png)

![](img/916255a354808a4764b2e500da6f91ce_227.png)

We're accessing that in level 1， so L， L1 and L2 are level 0， we're accessing with in level 1。

 and we're saying that the access is equal to one， so we can add multiple indices for our rows。

 but we have multiple indices for our columns， so access equals ones means that we're using X to access our multiplelevel column index。



![](img/916255a354808a4764b2e500da6f91ce_229.png)

![](img/916255a354808a4764b2e500da6f91ce_230.png)

![](img/916255a354808a4764b2e500da6f91ce_231.png)

![](img/916255a354808a4764b2e500da6f91ce_232.png)

![](img/916255a354808a4764b2e500da6f91ce_233.png)

We're then going to take that data， which is now specific to at first just these0， so LR0。

 L10 and L20。

![](img/916255a354808a4764b2e500da6f91ce_235.png)

![](img/916255a354808a4764b2e500da6f91ce_236.png)

And we're going to plot those。Just using a scatter plot， so we're going to have a marker equal to oh。

 no lines between we're setting our markers， so each one of those dots will be a size of two。



![](img/916255a354808a4764b2e500da6f91ce_238.png)

![](img/916255a354808a4764b2e500da6f91ce_239.png)

Where do we want to plot that in this axis that we've defined here in the bounding box as we loop through them。

 and we don't want a legend？

![](img/916255a354808a4764b2e500da6f91ce_241.png)

![](img/916255a354808a4764b2e500da6f91ce_242.png)

And then we're saying here if the x is x is zero， so's the same as if it is our first value。

 then we will actually add on this legend at the location equal to4。



![](img/916255a354808a4764b2e500da6f91ce_244.png)

![](img/916255a354808a4764b2e500da6f91ce_245.png)

![](img/916255a354808a4764b2e500da6f91ce_246.png)

And then we just set our title plus that string and we'll run this。



![](img/916255a354808a4764b2e500da6f91ce_248.png)

And what we see here is for the coefficient set zero。



![](img/916255a354808a4764b2e500da6f91ce_250.png)

So this is zero versus the rest。We have each one of our different coefficients and there should be 561 of them。

 and we see that we have some high values here on the low end and maybe some will not some here on the low end for coefficient set zero for coefficient set three。

 we see it scattered throughout， so here's just getting the strength of each one of those coefficients。



![](img/916255a354808a4764b2e500da6f91ce_252.png)

![](img/916255a354808a4764b2e500da6f91ce_253.png)

![](img/916255a354808a4764b2e500da6f91ce_254.png)

![](img/916255a354808a4764b2e500da6f91ce_255.png)

![](img/916255a354808a4764b2e500da6f91ce_256.png)

We're going to stop this video here and in the next video now that we've seen the coefficients across 561 coefficients and saw how that worked for multiple label indices。

 we're going to get started with actually setting out predicting as well as coming up with the probabilities for each one of the predicted classes All right。

 I'll see you there。

![](img/916255a354808a4764b2e500da6f91ce_258.png)

![](img/916255a354808a4764b2e500da6f91ce_259.png)

![](img/916255a354808a4764b2e500da6f91ce_260.png)

![](img/916255a354808a4764b2e500da6f91ce_261.png)

![](img/916255a354808a4764b2e500da6f91ce_262.png)