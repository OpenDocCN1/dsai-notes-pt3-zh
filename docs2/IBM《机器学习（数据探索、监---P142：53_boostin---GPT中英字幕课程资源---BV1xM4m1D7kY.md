# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P142：53_boosting笔记本（选修部分）第1部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Welcome to our lab here on boosting and stacking using Python here we're going to be using the human activity recognition with smartphones database we've used this before in the first lab for logistic regression。

And we're going to just quickly recap some of the things that we discussed there to ensure that we are familiar with the data set that we're working with and then do our train test split in order to prepare for actually doing some modeling。



![](img/cccfcad3f6a6d2852b5e37be1c2feccd_1.png)

So the first thing that we do is import the necessary libraries。



![](img/cccfcad3f6a6d2852b5e37be1c2feccd_3.png)

We're then going to import our。

![](img/cccfcad3f6a6d2852b5e37be1c2feccd_5.png)

File just using pandas。read csv。We look at the shape， and we see that we have 10299 rows。

 as well as 562 different columns。

![](img/cccfcad3f6a6d2852b5e37be1c2feccd_7.png)

![](img/cccfcad3f6a6d2852b5e37be1c2feccd_8.png)

And when we look at the value counts for the data types， so this is first doing data。 D types。

 getting what are the data types for each one of the different columns and then seeing the value counts for each one of those values。



![](img/cccfcad3f6a6d2852b5e37be1c2feccd_10.png)

We see that 561 of them are already floats， and one of them is an object。

 and if we recall from working with logistic regression。

 that is going to be our outcome variable that will have to eventually change into integer values in order to pass it through our SKLn models。



![](img/cccfcad3f6a6d2852b5e37be1c2feccd_12.png)

![](img/cccfcad3f6a6d2852b5e37be1c2feccd_13.png)

We're then going to confirm that the maximum value is1 and the minimum value is negative one for each one of our values so that we can confirm that these values are already scaled。



![](img/cccfcad3f6a6d2852b5e37be1c2feccd_15.png)

![](img/cccfcad3f6a6d2852b5e37be1c2feccd_16.png)

![](img/cccfcad3f6a6d2852b5e37be1c2feccd_17.png)

And something to note here is that， on the other hand。

 scaling is never really required for tree based methods。

 And the majority of what we're going to work with are tree based methods。

 But for the small amount of the end when we do stacking。

 it is worth double checking that all of these are already pre processed。



![](img/cccfcad3f6a6d2852b5e37be1c2feccd_19.png)

![](img/cccfcad3f6a6d2852b5e37be1c2feccd_20.png)

![](img/cccfcad3f6a6d2852b5e37be1c2feccd_21.png)

![](img/cccfcad3f6a6d2852b5e37be1c2feccd_22.png)

So first we're going to create appendda series that will just tell us for each column whether or not they are afloat。



![](img/cccfcad3f6a6d2852b5e37be1c2feccd_24.png)

We're then going to locate every single row， that's going to be our colon here。

And then only the float columns， only the columns that were already afloat。

 and then check the max value， and this will by default。

 check the max value for each one of those different columns。



![](img/cccfcad3f6a6d2852b5e37be1c2feccd_26.png)

So once we get that max value， we then check that it's equal to one。

So now we have true or false for every single one of our different columns that are floats that is。



![](img/cccfcad3f6a6d2852b5e37be1c2feccd_28.png)

![](img/cccfcad3f6a6d2852b5e37be1c2feccd_29.png)

And then we called the all， and that will just say is every single value true？

So if you have one false in there， this will return false。 If they are all true。

 then it will return true。

![](img/cccfcad3f6a6d2852b5e37be1c2feccd_31.png)

And then we do the same thing for a negative one here。



![](img/cccfcad3f6a6d2852b5e37be1c2feccd_33.png)

We run this and we see that this returns two values for true。Now I want to note， I will not be doing。

 as I've done in earlier notebooks， jumping out and creating a cell above in order to show you step by step the Python code and how it works。

 unless it's a new function for all the new functions I will break down those steps。

 as well as from some of the more complex graphs。

![](img/cccfcad3f6a6d2852b5e37be1c2feccd_35.png)

But I do want you to note and on your own， if you get confused， always feel free to pause a video。



![](img/cccfcad3f6a6d2852b5e37be1c2feccd_37.png)

And go ahead and do something along the lines of pulling out a piece of code。



![](img/cccfcad3f6a6d2852b5e37be1c2feccd_39.png)

And confirming what it actually looks like， because we're just setting these equal to variables so that we understand piece by piece。

 what the code actually looks like。 And we can think the same here pulling。



![](img/cccfcad3f6a6d2852b5e37be1c2feccd_41.png)

This out。Running this as well and you can see this step by step， and as I mentioned。

 this will just return either true or false values for each one of our different columns。



![](img/cccfcad3f6a6d2852b5e37be1c2feccd_43.png)

![](img/cccfcad3f6a6d2852b5e37be1c2feccd_44.png)

Now let's move on to question number two， here we're going to integer and code each one of our different activities。



![](img/cccfcad3f6a6d2852b5e37be1c2feccd_46.png)

![](img/cccfcad3f6a6d2852b5e37be1c2feccd_47.png)

And then we're going to split our data into train and test sets。

 and we also want to decide if that data will be stratified or not during that trainer test split。

So recall how we would look at that， whether or not we should be stratified。

 that's usually if we have some type of imbalance， we want to ensure that we stratify our sample。

 so we'll take a quick look at that before doing our train test split。



![](img/cccfcad3f6a6d2852b5e37be1c2feccd_49.png)

![](img/cccfcad3f6a6d2852b5e37be1c2feccd_50.png)

![](img/cccfcad3f6a6d2852b5e37be1c2feccd_51.png)

So first things first。We first import our label encoder because we have to encode our activity column。

 our outcome variable as integers rather than how they currently are as strings。



![](img/cccfcad3f6a6d2852b5e37be1c2feccd_53.png)

So we initiate our label encoder objects。

![](img/cccfcad3f6a6d2852b5e37be1c2feccd_55.png)

And then all we have to do is call fit transform on our original data。

And then we'll use that to replace our current version of the data。



![](img/cccfcad3f6a6d2852b5e37be1c2feccd_57.png)

So what we've done is we've taken these original classes。

And we've converted them to different integer values。



![](img/cccfcad3f6a6d2852b5e37be1c2feccd_59.png)

Now， as you walk through the code and you look at stuff like your confusion matrix or the precision or recall for a specific class and you're curious which class which you can always come back to these L dot classes and these are in order。

 so this will be0， this will be1， this will be two， and so on and so forth。



![](img/cccfcad3f6a6d2852b5e37be1c2feccd_61.png)

![](img/cccfcad3f6a6d2852b5e37be1c2feccd_62.png)

![](img/cccfcad3f6a6d2852b5e37be1c2feccd_63.png)

Now， here we want to note what's noted here is that when we're doing boosting。



![](img/cccfcad3f6a6d2852b5e37be1c2feccd_65.png)

Because it has the sequential process that we discuss in lecture and it can't be parallellyzed。

 often this will take a very long time to run， especially if you have a larger data set。



![](img/cccfcad3f6a6d2852b5e37be1c2feccd_67.png)

So if you want to make sure that things run a little bit quicker。

And you may want to scale down the size of your training and test sets。



![](img/cccfcad3f6a6d2852b5e37be1c2feccd_69.png)

Or especially your train sets in order to ensure that it trains a bit quicker。



![](img/cccfcad3f6a6d2852b5e37be1c2feccd_71.png)

So first thing to see whether or not we need to actually stratify our split。

 we check the value counts for each one of our outcome variables， we see that it' fairly balanced。

 so we're going to just use a regular train test split。



![](img/cccfcad3f6a6d2852b5e37be1c2feccd_73.png)

![](img/cccfcad3f6a6d2852b5e37be1c2feccd_74.png)

![](img/cccfcad3f6a6d2852b5e37be1c2feccd_75.png)

If down the line you're seeing some type of errors with your confusion matrices or some of your errors for specific values。

 perhaps you want to move back and try a stratifiedite splitzz well and see if that improves how your model actually comes up with its difference values with its different metrics。



![](img/cccfcad3f6a6d2852b5e37be1c2feccd_77.png)

![](img/cccfcad3f6a6d2852b5e37be1c2feccd_78.png)

We're then going to create our feature columns as well as our actual outcome variable。

 so we have our feature columns。

![](img/cccfcad3f6a6d2852b5e37be1c2feccd_80.png)

Using。This list comprehension that we've had before。

 so we're just taking x for every single x in the columns that are not equal to activity。



![](img/cccfcad3f6a6d2852b5e37be1c2feccd_82.png)

We set as our x variable data feature columns， those feature columns we just defined。

 and as our y variable data activity， we set our test size equal to 0。3， random say equal to 42。

 and we will get our x train， x test， Y train and Y test output from our train test split。



![](img/cccfcad3f6a6d2852b5e37be1c2feccd_84.png)

And then we can just look at the shape of each， and we see that we have 70% in one and 30% in the other。



![](img/cccfcad3f6a6d2852b5e37be1c2feccd_86.png)

![](img/cccfcad3f6a6d2852b5e37be1c2feccd_87.png)

Now that closes out this video， just preparing for actually going into our modeling。

 and then the next video we'll pick up and start off with actually fitting and predicting using our gradient boosting classifier。



![](img/cccfcad3f6a6d2852b5e37be1c2feccd_89.png)

![](img/cccfcad3f6a6d2852b5e37be1c2feccd_90.png)

![](img/cccfcad3f6a6d2852b5e37be1c2feccd_91.png)

All right， I'll see you there。

![](img/cccfcad3f6a6d2852b5e37be1c2feccd_93.png)