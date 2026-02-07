# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P62：13_训练集和测试集分割实验（选修部分）第1部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Welcome to our second notebook in our second course。



![](img/956a2e074cf4f6a0c302ede4f0be3678_1.png)

Here we will be learning about train test split， specifically in order to evaluate a linear regression model。



![](img/956a2e074cf4f6a0c302ede4f0be3678_3.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_4.png)

Again， we'll be working with the data set on housing prices in Aes。

 Iowa that we were introduced to in the first notebook。



![](img/956a2e074cf4f6a0c302ede4f0be3678_6.png)

The first thing that we're going to do is import OS。

 which is just a library to access our operating system。

 as well as set this variable data path equal to this list with one item data。

 which we'll see in a second is going to allow us to access the folder where our CSV file lives。



![](img/956a2e074cf4f6a0c302ede4f0be3678_8.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_9.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_10.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_11.png)

So the first question asks us to import the data using pandas and examine the shape。



![](img/956a2e074cf4f6a0c302ede4f0be3678_13.png)

So there should be 79 feature columns plus the predictor， the predictor being the sale price。



![](img/956a2e074cf4f6a0c302ede4f0be3678_15.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_16.png)

And then next part of the question is asking there are three different types， integers， floats。

 and strings。

![](img/956a2e074cf4f6a0c302ede4f0be3678_18.png)

We want to examine how many of each type there is in our data frame。



![](img/956a2e074cf4f6a0c302ede4f0be3678_20.png)

So as usual， we import panndadas SPD and nuumpy as NP。



![](img/956a2e074cf4f6a0c302ede4f0be3678_22.png)

We're going to set our file path equal to this OS dot set。



![](img/956a2e074cf4f6a0c302ede4f0be3678_24.png)

And to show you how this works。0 S dot set is just going to tell you， given your operating system。

 what is the separator that you use as you tried to find the folder within or a subfold within a folder or a CV file within the folder。

 I'm on the Mac operating system。 So we use the forward slash。 And so we have this forward slash。

 and then we want to join together using the dot join different items in a list。



![](img/956a2e074cf4f6a0c302ede4f0be3678_26.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_27.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_28.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_29.png)

So our data path is one list。 We add that to the Ames housingousing sales do CSsv。

 which is another list to have a list with two items。



![](img/956a2e074cf4f6a0c302ede4f0be3678_31.png)

And when we run dot join。

![](img/956a2e074cf4f6a0c302ede4f0be3678_33.png)

These values。Then we end up with。

![](img/956a2e074cf4f6a0c302ede4f0be3678_35.png)

This string that we want， which is just our folder and then the CSV file。



![](img/956a2e074cf4f6a0c302ede4f0be3678_37.png)

That we want to access then all we have to do is run pandas。read CSsv and pass in the file path。



![](img/956a2e074cf4f6a0c302ede4f0be3678_39.png)

And we end up with our pandas data fame， and we're setting that equal to data。



![](img/956a2e074cf4f6a0c302ede4f0be3678_41.png)

Next， we're going to print out the shape。

![](img/956a2e074cf4f6a0c302ede4f0be3678_43.png)

Remember， we asked in the beginning， what is the shape of our data frame？



![](img/956a2e074cf4f6a0c302ede4f0be3678_45.png)

The pandas data frame has this attribute， dot shape， and we see that as 1379 rows。

 and as we said earlier there's going to be 80 columns。

 79 of those features plus the predictor column。

![](img/956a2e074cf4f6a0c302ede4f0be3678_47.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_48.png)

Now in order to get。

![](img/956a2e074cf4f6a0c302ede4f0be3678_50.png)

The second portion of question 2。We were asked to find the number of integers， floats。

 and strings in each one of those 80 columns。

![](img/956a2e074cf4f6a0c302ede4f0be3678_52.png)

When I run data。 D types on its own， it'll return a panda series。 You can think of that as a。



![](img/956a2e074cf4f6a0c302ede4f0be3678_54.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_55.png)

Column within your data frame and when you have just a single column。

 you can run this method called dot value counts on your panda series。



![](img/956a2e074cf4f6a0c302ede4f0be3678_57.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_58.png)

And that will give you the count of every unique value within that column。

 So here our unique values are float， object and integer， So when we do value counts。

 it just gives the count of object flow and integer。



![](img/956a2e074cf4f6a0c302ede4f0be3678_60.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_61.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_62.png)

Now moving to question two， a significant challenge。

 particularly when dealing with data that have many columns is ensuring that each column gets encoded correctly。

 and this is particularly true with data columns that are ordered categoricals versus unordered categoricals。

 that ordinal versus nominal that we talked about in the first lecture。



![](img/956a2e074cf4f6a0c302ede4f0be3678_64.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_65.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_66.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_67.png)

Now unordered categories should be one hot and coded。



![](img/956a2e074cf4f6a0c302ede4f0be3678_69.png)

However， this can significantly increase the number of features when we one hot and code and create features that are also highly correlated with one another。



![](img/956a2e074cf4f6a0c302ede4f0be3678_71.png)

So we want to determine with our starting point of 80 columns。

 how many total features would be present relative to what currently exists if all object features are one hot encoded。



![](img/956a2e074cf4f6a0c302ede4f0be3678_73.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_74.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_75.png)

And recall that the number of one hot encoded columns is going to be n minus1。

 where n is the number of categories， and the reason being that if you have one category。



![](img/956a2e074cf4f6a0c302ede4f0be3678_77.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_78.png)

Or in your original data frame。

![](img/956a2e074cf4f6a0c302ede4f0be3678_80.png)

And then you one hot and code it and say that creates three new columns because there's three unique。



![](img/956a2e074cf4f6a0c302ede4f0be3678_82.png)

Values。We are also going to drop that original one， so we only end up with two new values overall。

 so that's why it's n minus1。

![](img/956a2e074cf4f6a0c302ede4f0be3678_84.png)

So the first thing that we do is using that data。D types。

 we want to see which one of those are equal to NP dot object， so which ones are of type object。



![](img/956a2e074cf4f6a0c302ede4f0be3678_86.png)

And。

![](img/956a2e074cf4f6a0c302ede4f0be3678_88.png)

Once we do that， we can use that mask， which is just going to be true or false panda series that is the same length as your columns in order to filter down to the columns that are just equal to NP dot objects。



![](img/956a2e074cf4f6a0c302ede4f0be3678_90.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_91.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_92.png)

So。Quickly showing you what the mask looks like。

![](img/956a2e074cf4f6a0c302ede4f0be3678_94.png)

It's going to be this data frame where alley is actually an object whereas bedroom above grade is not that will actually be a numerical value。



![](img/956a2e074cf4f6a0c302ede4f0be3678_96.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_97.png)

So now that we have our categorical columns and that's just going to be our columns。

 we'll look at that as well really quickly， these are all the columns that we're now looking at。



![](img/956a2e074cf4f6a0c302ede4f0be3678_99.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_100.png)

We are going to。

![](img/956a2e074cf4f6a0c302ede4f0be3678_102.png)

Filter down our data to just those columns。

![](img/956a2e074cf4f6a0c302ede4f0be3678_104.png)

And we're going to use the dot apply method and that's going to apply a function to each individual column。

 we're going to run the X dotN unique which will give you for that column the number of unique values。

 which is what we're looking for right when we one hot and code we're creating a new column for every single unique value in that column。



![](img/956a2e074cf4f6a0c302ede4f0be3678_106.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_107.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_108.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_109.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_110.png)

So I'm going to say lambda x。Exa and unique。

![](img/956a2e074cf4f6a0c302ede4f0be3678_112.png)

And we see that we have for every column the number of unique values in that column。

 and that's going to be our nu OHC。

![](img/956a2e074cf4f6a0c302ede4f0be3678_114.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_115.png)

Underscore calls， and we can sort our values。 That won't matter later on。

 but it may make it a little cleaner to look at。

![](img/956a2e074cf4f6a0c302ede4f0be3678_117.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_118.png)

Now we don't need to encode if there's only going to be one value in that column。

 that's not the case for any of these， but just in case you can locate any of those that are equal to one and filter those out using this dot Lo。



![](img/956a2e074cf4f6a0c302ede4f0be3678_120.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_121.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_122.png)

The next thing that we want to do is we want to take each one of these values and subtract one because as we mentioned。

 we want to get to n minus1 because we're going to be losing that column after we create these new columns for each unique feature。



![](img/956a2e074cf4f6a0c302ede4f0be3678_124.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_125.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_126.png)

Pret unique value。So every one of these is going to be one subtracted from it using minus equals1。



![](img/956a2e074cf4f6a0c302ede4f0be3678_128.png)

And then finally， we're going to get the sum of how many unique values we are now left with。



![](img/956a2e074cf4f6a0c302ede4f0be3678_130.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_131.png)

So after we subtracted one， we have that end that we're looking for and we run。

 sum and we should have 215 new columns being created。



![](img/956a2e074cf4f6a0c302ede4f0be3678_133.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_134.png)

So if we started off with 79 or 80， we should end up with。



![](img/956a2e074cf4f6a0c302ede4f0be3678_136.png)

294 or 295， depending if you're counting that outcome variable。



![](img/956a2e074cf4f6a0c302ede4f0be3678_138.png)

Now， in the next section， when we come back， we will get started on actually doing that onehot encoding。

 not using the PDd。 dummies that we used earlier， but this time using SK learns One hott Enr。

 look forward to seeing you there。

![](img/956a2e074cf4f6a0c302ede4f0be3678_140.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_141.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_142.png)

![](img/956a2e074cf4f6a0c302ede4f0be3678_143.png)