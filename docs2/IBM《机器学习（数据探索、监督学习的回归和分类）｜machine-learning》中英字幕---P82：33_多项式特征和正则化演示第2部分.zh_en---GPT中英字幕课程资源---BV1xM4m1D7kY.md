# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P82：33_多项式特征和正则化演示第2部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Welcome back for part four of our notebook for the remaining exercises here。

 we're going to be working with the Ames Iowa Housing dataset that we've seen before。

There are going to be a number of features。And again。

 there's going to be those categorical features that we're going to have to transform using one hot ending。

So we're going to start by importing the data with pandas。

 we're going to one hot and code our categorical features。



![](img/7de10170a1cb9354da6e6b8158b2a582_1.png)

We're going to split that data into train and test sets。

We're going to do a log transformation on our skewed features。And then if necessary。

 or if you'd like， you can attempt to scale， although for us we're going to look to see how well regularization works even without scaling our features。



![](img/7de10170a1cb9354da6e6b8158b2a582_3.png)

![](img/7de10170a1cb9354da6e6b8158b2a582_4.png)

Something to note， scaling your features is going to be very important when working with regularization。

 as we discussed in course。But if you're already taking a log transformation of a lot of your variables or here of all of your variables。

 you're bringing them down to a very similar scale。

 so you don't have as much of an effect as when you're just using the raw data。

So we're going to create our file path， then use pandas。

readcsv to bring in our file we have here just to remind us the length of our columns。

 so we have 80 columns we're then going to get our dummy variables just using PDd。 get dummies。



![](img/7de10170a1cb9354da6e6b8158b2a582_6.png)

![](img/7de10170a1cb9354da6e6b8158b2a582_7.png)

That'll automatically by default， convert any columns that are of type object into dummy variables。

 we're going to also drop the first column so that we don't have strong multicollinearity。



![](img/7de10170a1cb9354da6e6b8158b2a582_9.png)

And then we see that we have now 252 columns。We look here。



![](img/7de10170a1cb9354da6e6b8158b2a582_11.png)

Next we're going to split the data to train in test sets。

 we're just going to use the train test split functionality from SK learnearn。

We're only passing in data， so since we're not passing in an X and a Y variable。

 we're going to end up with a train and test set， just those two， not for。

 as before where we have x train， X test， Y， train Y test and so on。

So we just have two outputs trained and test and that test set should be only 30% of the data and the train set should be 70% of the data。



![](img/7de10170a1cb9354da6e6b8158b2a582_13.png)

We're then going to create a list of the columns that are not one hot encoded。

 So the way that we're doing it here is we're assuming that none of our numerical features are only two values。

 And if they are， we probably don't want to do a log transformation of them anyway。

And we're using our lambda X x dot and unique to get a number of for each column。

 How many unique values there are。 And we're saying if there's only two unique values。

 we won't look at those。 We're only looking at those that have more than two unique values。

 So if you think about the one hot encoded。

![](img/7de10170a1cb9354da6e6b8158b2a582_15.png)

![](img/7de10170a1cb9354da6e6b8158b2a582_16.png)

![](img/7de10170a1cb9354da6e6b8158b2a582_17.png)

Column that's only going to have ones and zeros， and if it only has ones and zeros。

 then it only has two features and we will ignore that column and not do a long transformation on that column or even look for its S。



![](img/7de10170a1cb9354da6e6b8158b2a582_19.png)

So those are going to be our nu calls。

![](img/7de10170a1cb9354da6e6b8158b2a582_21.png)

Defined by this mask。We're then going to set our S limit above which we will transform our variables。

We're then going to get a Pada series and we've seen this before。

Where we filter down to only the numb callss that we just defined。

And then we check this skew of each one of those。 So then we will end up with a panda series where we have as the index。

 each one of the different column names， and then as the value， the actual skew of that column。



![](img/7de10170a1cb9354da6e6b8158b2a582_23.png)

We're then going to take that。Filter down。Here to only those that are above 0。75。



![](img/7de10170a1cb9354da6e6b8158b2a582_25.png)

We're then going to sort those values from largest to smallest。

We're then going to put it into a data frame， so from Pada series we have the method to translate it into a pandas data frame。

Since it is now a new pandas data frame， we're then going to have a default of a column called zero。

 we're just going to rename that SkuU。And if you want to see all these steps broken down one by one。

 they are in a past notebook， but we run this here， and we get our new Skew data frame。

 and it's going to be sorted from largest to smallest all above 0。75。



![](img/7de10170a1cb9354da6e6b8158b2a582_27.png)

![](img/7de10170a1cb9354da6e6b8158b2a582_28.png)

![](img/7de10170a1cb9354da6e6b8158b2a582_29.png)

So just to get a recap of what this looks like， we've done this before as well。

 we're going to use Plt。splots。

![](img/7de10170a1cb9354da6e6b8158b2a582_31.png)

And we're going to have two axes， the as before and a after whenever we call PLT do subplots。

 it's then going to be the overall figure， and then after that it will be the number of axes that we define the number of bounding boxes here we have two it's going to be one row and two columns。



![](img/7de10170a1cb9354da6e6b8158b2a582_33.png)

We're then going to take our train set that we defined。And say for this field， which we have here。

 basement Fin SF1， which is one of our skewed variables that we saw here。



![](img/7de10170a1cb9354da6e6b8158b2a582_35.png)

![](img/7de10170a1cb9354da6e6b8158b2a582_36.png)

We're going to look at the histogram and we're going to plot that histogram on the bounding box X before。

 So here we're using the pandas built in version of plotting。



![](img/7de10170a1cb9354da6e6b8158b2a582_38.png)

![](img/7de10170a1cb9354da6e6b8158b2a582_39.png)

We're then going to apply the NP。 log 1p。To get the log transform of that。

 we do log 1 P rather than just log because if the value is 0， it would error out。

 So this takes any value of 0， adds one， and then does the log transformation。



![](img/7de10170a1cb9354da6e6b8158b2a582_41.png)

And we're going to plot that on the ax after。We're then just going to set our title。

 our Y label and our X label for both our Acts before and our Act after。



![](img/7de10170a1cb9354da6e6b8158b2a582_43.png)

And then we'll have the full title for the overall figure that we're working with。



![](img/7de10170a1cb9354da6e6b8158b2a582_45.png)

And we see here how the log transformation created a more normally distributed graph。



![](img/7de10170a1cb9354da6e6b8158b2a582_47.png)

From left to right。With that in mind， we're then going to go through each one of our columns。

 except for sales price。 And we're going to convert them to the。



![](img/7de10170a1cb9354da6e6b8158b2a582_49.png)

Log transform of the of their respective columns。

![](img/7de10170a1cb9354da6e6b8158b2a582_51.png)

So for call in each one of our Sw columns。

![](img/7de10170a1cb9354da6e6b8158b2a582_53.png)

Now， if it's equal to sales price will pass。

![](img/7de10170a1cb9354da6e6b8158b2a582_55.png)

Otherwise， we will。Change the train column to the log transform of it。



![](img/7de10170a1cb9354da6e6b8158b2a582_57.png)

And we will do the same for the test column。

![](img/7de10170a1cb9354da6e6b8158b2a582_59.png)

These two are just different ways of doing the same thing。

 just showing you two different ways of doing the same thing。



![](img/7de10170a1cb9354da6e6b8158b2a582_61.png)

Also， we don't have to do something like fit transform and then just transform on the test set because the log isn't fitting to anything。

 the log is going to be the same mathematical operator no matter what。



![](img/7de10170a1cb9354da6e6b8158b2a582_63.png)

![](img/7de10170a1cb9354da6e6b8158b2a582_64.png)

![](img/7de10170a1cb9354da6e6b8158b2a582_65.png)

We're then going to separate out our feature columns。

 what we're trying to use to predict as well as our prediction， so that we'll have X train， Y train。

 X test and Y tests， so our feature calls are just every single column besides sales price。

 and then we can just select the appropriate columns。



![](img/7de10170a1cb9354da6e6b8158b2a582_67.png)

![](img/7de10170a1cb9354da6e6b8158b2a582_68.png)

![](img/7de10170a1cb9354da6e6b8158b2a582_69.png)

From our training and test sets。

![](img/7de10170a1cb9354da6e6b8158b2a582_71.png)

Part 5 here， we're going to write a function， RMSE， which is the root mean squared error。

 that's going to take the truth。The actual outcome， the actual sales price。

 and the prediction values， and return the root mean squared error。



![](img/7de10170a1cb9354da6e6b8158b2a582_73.png)

We're going to use SsK learns mean squared error here， and all we got to do is take the square root。



![](img/7de10170a1cb9354da6e6b8158b2a582_75.png)

So we import mean squared error， and then root mean squared error takes in y true and y predicted。

And we just pass in that y Q and y predicted into our mean squared error function and then take the square root of that function。



![](img/7de10170a1cb9354da6e6b8158b2a582_77.png)

So rather than looking at mean squared error， we'll have something that's at least on a similar scale to our actual sales price。

Now we're going to fit a basic linear regression model。

We will print the root mean squared error for this particular model。

 and then we'll plot the predicted versus the actual sales price for the linear regression model。



![](img/7de10170a1cb9354da6e6b8158b2a582_79.png)

![](img/7de10170a1cb9354da6e6b8158b2a582_80.png)

So we're combining a lot of steps that we saw broken out into separate steps in prior notebooks。

 Best practice is going to be to separate this out into separate lines。

 Here we have the initiation of the objects linear regression。

 and then we're quickly calling dot fit。On that object rather than initiating that object and then calling a dot fit on that initiated objects。

 according to a variable defined earlier。

![](img/7de10170a1cb9354da6e6b8158b2a582_82.png)

The reason why we generally will not want to do this。

 and we have been using the practice that we have before and the syntax that we have before is because as we do more machine learning。

 we're going to pass in a lot of arguments here and we'll end up with a large line of code。



![](img/7de10170a1cb9354da6e6b8158b2a582_84.png)

And it'll be confusing to find that dot fit at the end of it。

 So it's better to break this out in separate steps。

 It's much easier to read Here we call linear regression and dot fit just to show you that you can do it all in one step。



![](img/7de10170a1cb9354da6e6b8158b2a582_86.png)

So then we have linear regression fit to our x train and Y train。

 and then we're going to get a root mean squared error。

 which is the function we define on our y test， our actual Y variables。

And then using the linear regression we just defineds， we are going to predict the X test。

 right this linear regression was defined and then fit to training data。

 we're then going to predict on our test data。

![](img/7de10170a1cb9354da6e6b8158b2a582_88.png)

![](img/7de10170a1cb9354da6e6b8158b2a582_89.png)

And then we can print out our linear regression root mean squared error， which we defined above。

 and we get the root mean squared error for plain linear regression。



![](img/7de10170a1cb9354da6e6b8158b2a582_91.png)

![](img/7de10170a1cb9354da6e6b8158b2a582_92.png)

We're then going to plot out our linear regression here we're plotting out not the linear regression。

 but the predicted values versus the actual outcome values。 again。

 we'd want them to be exactly on the same exactly on the diagonal if we got it completely correct。

 the further it is from the diagonal， the worse we did in terms of our prediction。



![](img/7de10170a1cb9354da6e6b8158b2a582_94.png)

We're initiating our X， we're also initiating our figure just to set our figure size to six by six。



![](img/7de10170a1cb9354da6e6b8158b2a582_96.png)

And then we're going X dot plot， and we're just plotting our actual values versus our predicted values。

We're setting the marker to O。Our line style is going to blank。

 We don't want lines connecting each one of these dots。



![](img/7de10170a1cb9354da6e6b8158b2a582_98.png)

And we can run this here。

![](img/7de10170a1cb9354da6e6b8158b2a582_100.png)

And we see that it's fairly aligned， but maybe a bit off a little bit difficult to tell when you're looking at an image。

 But we'll see more results as we look at the。Lassso regression and ridge regression in the next video。

 as well as actually just looking at that root mean squared error for here， linear regression。

 And then later on， ridge and Lasso， as well as elastic net。



![](img/7de10170a1cb9354da6e6b8158b2a582_102.png)

I look forward to seeing you in next video， Thank you。



![](img/7de10170a1cb9354da6e6b8158b2a582_104.png)

![](img/7de10170a1cb9354da6e6b8158b2a582_105.png)