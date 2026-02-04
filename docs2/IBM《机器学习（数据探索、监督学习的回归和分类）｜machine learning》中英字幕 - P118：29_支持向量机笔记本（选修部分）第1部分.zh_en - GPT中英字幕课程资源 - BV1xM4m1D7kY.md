# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P118：29_支持向量机笔记本（选修部分）第1部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Welcome to our demo on how to use support vector machinesch in Python。



![](img/87518773a58ac627a5208dda23bdc623_1.png)

Here we're going to be using a wine quality data set for each one of the exercises。

 and the data contains various chemical properties of the wine， such as acidity， sugar。

 pH level and alcohol， and is also going to contain a quality metric from 3 to9。

 where higher is better， and then a color whether or not that wine is red or white。



![](img/87518773a58ac627a5208dda23bdc623_3.png)

![](img/87518773a58ac627a5208dda23bdc623_4.png)

So we're going to ensure that we are in the right directory， changing our directory to data。

 import the necessary libraries， and then for part one， we're going to want to import our data。



![](img/87518773a58ac627a5208dda23bdc623_6.png)

![](img/87518773a58ac627a5208dda23bdc623_7.png)

Create our target variable Y， and that's going to be either red or white。

 We want to choose the different colors。 that's what we're trying to predict using all of our variables and we want to set that to 1 and0 where one is red。



![](img/87518773a58ac627a5208dda23bdc623_9.png)

![](img/87518773a58ac627a5208dda23bdc623_10.png)

We're then going to create a pair plot for the data。

 that pair plot is going to be what we learned with Cborn when we did our EDA so that we say each one of the relationships between the variables and our outcome variable。

 as well as each of the variables with the other variables in our data。



![](img/87518773a58ac627a5208dda23bdc623_12.png)

![](img/87518773a58ac627a5208dda23bdc623_13.png)

![](img/87518773a58ac627a5208dda23bdc623_14.png)

We're then going to create a bar plot showing the correlations between each column and y to see which columns are most correlated。

 and then we're going to pick the two most correlated fields using the absolute value of these correlations to create a new X with only two features。

 This is just for visual purposes。 It's easier to plot when we're only working in two dimensions。

 and then we're going to want to scale our data X。 and we want to note that it's going to output an array so we want to make it back into a data frame。



![](img/87518773a58ac627a5208dda23bdc623_16.png)

![](img/87518773a58ac627a5208dda23bdc623_17.png)

![](img/87518773a58ac627a5208dda23bdc623_18.png)

So let's get started with that first we import our data as we've done before with Pandas Read CSv。



![](img/87518773a58ac627a5208dda23bdc623_20.png)

We're then going to set our y variable equal to our data color。

 and we're just going to say data color equals equals red。



![](img/87518773a58ac627a5208dda23bdc623_22.png)

![](img/87518773a58ac627a5208dda23bdc623_23.png)

And when we run that， that will pass out either true or false。



![](img/87518773a58ac627a5208dda23bdc623_25.png)

And then once we， let's actually look at that， do data。color。



![](img/87518773a58ac627a5208dda23bdc623_27.png)

Equals red。And we see that that passes out true or false。 And when we say as type ins。

 we're just going to translate each one of those truths as。



![](img/87518773a58ac627a5208dda23bdc623_29.png)

![](img/87518773a58ac627a5208dda23bdc623_30.png)

Ones， and each one of those falses as zeros。 So now y is equal to ones and zeros with one equal to red。



![](img/87518773a58ac627a5208dda23bdc623_32.png)

![](img/87518773a58ac627a5208dda23bdc623_33.png)

We're then going to say that our fields， so our feature columns are going to be all of our columns except for the last one。



![](img/87518773a58ac627a5208dda23bdc623_35.png)

![](img/87518773a58ac627a5208dda23bdc623_36.png)

So everything except for color。And then the question was to pull out all of the correlations。

 so we want to see each of the correlations with our y variable。

So all we have to do is take our data fields。Which is just going to be each one of our columns that's going to be a pandas data frame。

And then we call dot core width， and we'll check the correlation with whatever panaces we pass in there。

 We pass in our Y。 We have to ensure that that y is going to be the same length。

 So the same number of rows as our fields， which it will be。

And then we're going to sort those values from smallest to largest。



![](img/87518773a58ac627a5208dda23bdc623_38.png)

So I run this， and we see that we have for each one of our different columns。

 how correlated that column is with our y variable。 So total sulfur dioxides。

 the highest negative correlation and volatile acidity is the highest positive correlation。



![](img/87518773a58ac627a5208dda23bdc623_40.png)

![](img/87518773a58ac627a5208dda23bdc623_41.png)

![](img/87518773a58ac627a5208dda23bdc623_42.png)

![](img/87518773a58ac627a5208dda23bdc623_43.png)

We're then going to run our pair plot by just passing in all of our data here。

 And when we say h equals color that allows to split up our data into both our red and white rhhine here。



![](img/87518773a58ac627a5208dda23bdc623_45.png)

![](img/87518773a58ac627a5208dda23bdc623_46.png)

I'm going to run this and this is it take a second， so it'll pause and when you see hear it again。

 it'll have RAand already， but it may take a second for you。



![](img/87518773a58ac627a5208dda23bdc623_48.png)

So we see here now our repair plot and we have the scatter plot for each one of the relationships between our different x variables for each one of our features。



![](img/87518773a58ac627a5208dda23bdc623_50.png)

![](img/87518773a58ac627a5208dda23bdc623_51.png)

As well as seeing the histogram or the distribution for each one of these individual features。



![](img/87518773a58ac627a5208dda23bdc623_53.png)

And we also see because we use hue equals color that we are differentiating between our red and white wine。

 and then you can see the little legends down by the right side where red is going to be blue and white is going to be green in regards to the coloring in our plots。



![](img/87518773a58ac627a5208dda23bdc623_55.png)

![](img/87518773a58ac627a5208dda23bdc623_56.png)

And we see from the scatter plots， as well as the histograms。

 that there seems to be some type of separation in the data in regards to our red wine and our white wine that we can see within each one of these graphs。



![](img/87518773a58ac627a5208dda23bdc623_58.png)

![](img/87518773a58ac627a5208dda23bdc623_59.png)

So hopefully that means that we'll be able to come up with a classifier that clearly identifies which rhs are red and which wines are white。



![](img/87518773a58ac627a5208dda23bdc623_61.png)

![](img/87518773a58ac627a5208dda23bdc623_62.png)

We're then going to plot our correlations that we came up with earlier。

 so it'll be the same data that we saw before， where we see that on the negative correlation side。

 so the highest negative correlation was total sulphfur dioxide and the largest positive correlation was the volatile acidity。



![](img/87518773a58ac627a5208dda23bdc623_64.png)

![](img/87518773a58ac627a5208dda23bdc623_65.png)

![](img/87518773a58ac627a5208dda23bdc623_66.png)

We're then going to look at the top two values for these correlations。



![](img/87518773a58ac627a5208dda23bdc623_68.png)

So I pulled out here。The fields that we'd be pulling out in order to get these two top two absolute。



![](img/87518773a58ac627a5208dda23bdc623_70.png)

![](img/87518773a58ac627a5208dda23bdc623_71.png)

Correlations。So if we look at this step by step， the first thing that we want to do is get the absolute values for each。



![](img/87518773a58ac627a5208dda23bdc623_73.png)

We can then sort those values。

![](img/87518773a58ac627a5208dda23bdc623_75.png)

By calling sort values。And we probably just want these last two， I mean。

 we do want just these last two， because those were the highest absolute value of the correlations。



![](img/87518773a58ac627a5208dda23bdc623_77.png)

![](img/87518773a58ac627a5208dda23bdc623_78.png)

We look at those last two by calling the Ilu negative2 through and then。



![](img/87518773a58ac627a5208dda23bdc623_80.png)

Just taking the index values so that we know that those are the two columns that we're going to use moving forward so that we can easily visualize our classifier right once we move beyond two dimensions。

 it gets a little bit more difficult to visualize our classification。



![](img/87518773a58ac627a5208dda23bdc623_82.png)

![](img/87518773a58ac627a5208dda23bdc623_83.png)

![](img/87518773a58ac627a5208dda23bdc623_84.png)

![](img/87518773a58ac627a5208dda23bdc623_85.png)

So we're saying that X rather than being all of the fields that we have available is just going to be equal to these two fields。

That we have highlighted here using the code that we just walked through。



![](img/87518773a58ac627a5208dda23bdc623_87.png)

And then an an important point that we didn't highlight in lecture。

 but we want to keep in mind similar to Can nearest neighbors。

 The distance is going to matter when we're trying to figure out what is the best margin。

 What is the largest margin we can find between our two classes。

And we don't want any one of our features to have more weight than the others because it's just a larger value or a lower value。



![](img/87518773a58ac627a5208dda23bdc623_89.png)

So if the features range from 0 to 5 versus 10，000 to a million。

 we don't want that to have an effect， but rather the variation within those values to have that effect。

 so we want to scale them so that they're on the same scale。



![](img/87518773a58ac627a5208dda23bdc623_91.png)

![](img/87518773a58ac627a5208dda23bdc623_92.png)

So that's going to be very important for any of your support vector machines as we move forward。



![](img/87518773a58ac627a5208dda23bdc623_94.png)

So we initiate our Min Macac Scalar， we call that scalar。



![](img/87518773a58ac627a5208dda23bdc623_96.png)

We're then going to use our fit transform on X。

![](img/87518773a58ac627a5208dda23bdc623_98.png)

Generally speaking， we would want a holdout set so that we do our fit transform on our X train and then test on our holdout set。

 but within this demo we just want to visualize how each of these boundaries are being built and what they actually look like。



![](img/87518773a58ac627a5208dda23bdc623_100.png)

So we're going to train on the entire data set。

![](img/87518773a58ac627a5208dda23bdc623_102.png)

Or then once we have x equal to the fit transform of x， we're working with a nuumpy array。

 so all we want to do is make sure that goes back into appenddas data frame rather than a numpy array。

 so we pass in X， which is now our scaled version of our data and our columns are just going to be the original columns。



![](img/87518773a58ac627a5208dda23bdc623_104.png)

![](img/87518773a58ac627a5208dda23bdc623_105.png)

![](img/87518773a58ac627a5208dda23bdc623_106.png)

![](img/87518773a58ac627a5208dda23bdc623_107.png)

Which are those two that we identified earlier in fields， where it's just going to be that。

 but we are going to rename the columns that value scales。



![](img/87518773a58ac627a5208dda23bdc623_109.png)

![](img/87518773a58ac627a5208dda23bdc623_110.png)

And then when we print X dot columns， we'll see that we have volatile acidity and total sulfur dioxide originally。



![](img/87518773a58ac627a5208dda23bdc623_112.png)

![](img/87518773a58ac627a5208dda23bdc623_113.png)

And then we print out the new columns and we have those values scaled。



![](img/87518773a58ac627a5208dda23bdc623_115.png)

We're going to take a pause here。

![](img/87518773a58ac627a5208dda23bdc623_117.png)

And in the next video， we will start to plot out our decision boundaries。

 show you the code in order to do that， and with that we'll be able to walk through different hyperparameters and see the effects of more or less regularization。



![](img/87518773a58ac627a5208dda23bdc623_119.png)

![](img/87518773a58ac627a5208dda23bdc623_120.png)

![](img/87518773a58ac627a5208dda23bdc623_121.png)