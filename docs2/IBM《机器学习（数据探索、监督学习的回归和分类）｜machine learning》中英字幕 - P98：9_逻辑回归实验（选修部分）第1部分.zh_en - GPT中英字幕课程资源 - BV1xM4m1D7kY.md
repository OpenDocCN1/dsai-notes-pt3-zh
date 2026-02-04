# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P98：9_逻辑回归实验（选修部分）第1部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Welcome to our lab here on logistic regression as well as errormetric。

 Here we're going to be using the human activity recognition with Smarts database。

 which was built by just getting a bunch of study participants to walk around with smartphones with embedded inertial sensors and see given that data。

 whether or not we can tell they are walking， walking upstairs， walking downstairs， sitting。

 standing and laying。 So we have this classification problem。

 or trying to come up with a label of one of these six categories。😊。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_1.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_2.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_3.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_4.png)

And the first thing that we're going to want to do is import the necessary libraries as we've done before。

 we are also going to run OS。chdR， which is short forchan directory and we're going to set the directory that we're working as data。

 so that's going to be a sub folder within our current folder and then we are permanently changing that path so we can easily access any files within that data folder。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_6.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_7.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_8.png)

Then for question1， we want to import the data and then do the following。

 Ex the different data types。 So there are many columns。

 We want to know perhaps what the value counts are。

 as well as the different data types for each one of these many columns。

 determine if the floating point values need to be scaled。

 So we want to see if we need to scale our data。 determine the breakdown of each activity。

 So how much of each activity are we seeing in regards to our outcome variable。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_10.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_11.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_12.png)

And then we're going to want to encode that activity label as an integer because SKalL will not be able to take in a string。

 we have to encode it as an integer for our different categories。

So the first thing that we do is we run pandas。readcsv and pass in our file path。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_14.png)

We're then going to look at our different data types and recall that when we run data。d types。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_16.png)

We are getting the data type for each one of our different columns。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_18.png)

In order to see how much of each of the different data types are coming up。

 we just run value counts the same way we would with any column。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_20.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_21.png)

And we see that we have 561 floats and one object。 And that one object is going to be what we're trying to predict。

 That's going to be the different strings for walking， walking upstairs， laying and so on。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_23.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_24.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_25.png)

And we can see that here as we look at the data do D types and look at the last five values。

 and we see that activity is going to be that one object。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_27.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_28.png)

Column。We're then going to see that the data is scaled from a minimum of negative1 to a maximum of1。

 so there's some type of scaling here and the way that we're going to prove it is that for every single value。

 we're going to see that all the minimums are negative one and all of the positives and all of the maximums are positive one。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_30.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_31.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_32.png)

And so we're going to first look at thee。

![](img/44b9d00c4609e8d52e8498aeed0bcf81_34.png)

Value count so。

![](img/44b9d00c4609e8d52e8498aeed0bcf81_36.png)

If we look at just the min value， we see that we get the min for every single column。

 if you notice we took every single row， but we did not include that last column。

 that's what that negative one does for us。 And when we run dot min。

 we get the min for every single column in a panda series and then similar to what we just did for our data types we can run value counts。

 And we see that negative one is the only minimum value for every single column。

 And therefore there's 561 negative ones as our minimum value。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_38.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_39.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_40.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_41.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_42.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_43.png)

We do the same for the maximum value， and we see that all the maximum values have been scaled down to one。

 and all the minimum values have been scaled to negative one with different values in between。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_45.png)

Next thing we want to do is look at the breakdown of each one of the activities。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_47.png)

And we see here that our outcome variable has a fairly balanced set。

 So we see that they each take up an equal proportion of the overall rows。 And when we see this。

 we start to tune our minds， as we discuss in lecture。

 that different types of error metrics are going to work better for different types of data sets。

 whether their balanced or unbalance。 So here we're working with a balanced data set。

 So we want to start thinking what is the best type of error metric to use。

 given that we have a more balanced data。😊。

![](img/44b9d00c4609e8d52e8498aeed0bcf81_49.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_50.png)

Compared to our leukemia example that we talked about in lecture was very unbalanced。

 with 99% being healthy and only 1 per being unhealthy。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_52.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_53.png)

Then， as we mentioned， we cannot pass in a string into our SK learned model。

 whatever it is here going to be logistic regression。 So we have to encode that as an integer。

 So we're going to create our label encoder object。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_55.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_56.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_57.png)

First we just import it from ecalalar do prepro， then as we've done with our ecalalarn objects。

 we instantiate that object。

![](img/44b9d00c4609e8d52e8498aeed0bcf81_59.png)

We're then going to call that object that we just created El and call fit transformform on our activity column。

And we're just going to set that equal to our activity column。

 So now our activity column has been changed to， as we see here from the sample integers ranging from 0 to5 for each one of our different categories。

 right， those six different categories we had before are N maps the value 0，1，2，3，4，5。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_61.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_62.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_63.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_64.png)

Now， for question 2， we want to calculate the correlations between the independent variables。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_66.png)

We want to then create a histogram of the different correlation values。

 and then we're going to want to identify those that are most kept correlated。

 whether it's positive or negative with one another。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_68.png)

So I'm going to break this down into steps， so I'm going to create some code above。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_70.png)

We first have our feature columns， which are all of our columns up until the last column。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_72.png)

So that's going to be data。 columns and then all them up until the last。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_74.png)

And then in order to get our correlation matrix， all we have to do is specify those are the columns that we want our feature columns and call dot core。

 And that's just going to output a panda's data frame。 That's just a correlation matrix。

 So we're just going to look at that to see where we're at when we're getting started。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_76.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_77.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_78.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_79.png)

So that might take a second to run the next thing that I want to。 And there we see it。

 We see the correlation between Tea body act， whatever it is X and here of itself。

 which is why the correlation is1。 And then we can see， as well。

 the correlation between Tea body act mean X。 and Tea body act mean Y。 And that's 012。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_81.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_82.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_83.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_84.png)

And what we notice is the correlation between x and y is the same between as y and x。

 So this whole bottom portion of our matrix is not giving us any new information。

 including these ones， because we know every single value will have a perfect correlation with itself。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_86.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_87.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_88.png)

So we're going to want to eventually remove all those values。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_90.png)

So first， we're going to use this NP。trill indices from in order to get our all the indices。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_92.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_93.png)

For the bottom lower triangle。 So that's going to give us all those values on this diagonal。

 So we look at the diagonals of all the ones and below。 So this will give us all those indices。

 We'll see what that looks like。 Let's actually do that in a new cell because that took a second to run。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_95.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_96.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_97.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_98.png)

So we create this new cell here， and we can look at this trill index value that it outputs。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_100.png)

And it's going to be the。You know，0，0，1，0。 So remember， rows are first columns are second。

 and it will be each of the indices If you were to zip these two together。 So 0，0， we look here。

Then 1，0， then 1，1， and et cetera，1，1 B。 It'll be 1，1。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_102.png)

Will be across this diagonal and then all the values below。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_104.png)

So we want to replace all of those with null。A very efficient way to do it is to ensure that we are working with a numpy array。

 So we're going to change our current pandas data frame into an array。

 We're going to call that core array。

![](img/44b9d00c4609e8d52e8498aeed0bcf81_106.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_107.png)

And then we're saying for these indices that we just defined。Set them equal to NP。nam。

 so we're just setting them quickly into no values。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_109.png)

We're then going to， once we have nulled out all of that bottom triangle。

 let's actually look at what that looks like。

![](img/44b9d00c4609e8d52e8498aeed0bcf81_111.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_112.png)

We need to also call in。What it looks like now。

![](img/44b9d00c4609e8d52e8498aeed0bcf81_114.png)

We now have， let's actually set this sequel to a data frame。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_116.png)

To make it clear。

![](img/44b9d00c4609e8d52e8498aeed0bcf81_118.png)

We see that we have no doubt all the values on the diagonal and below。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_120.png)

Then we are going to set that back to a data frame with our columns equal to original columns and our index equal to our original index。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_122.png)

We're then going to stack that data frame and when we stack。

 what we're doing is we're ensuring that there's only a single value column and then we're taking each one of our different columns that we had originally。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_124.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_125.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_126.png)

Let's actually again pass this in step by step so that we can take a closer look。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_128.png)

So now we have。This new data frame。Which has the same name as the one that we had before。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_130.png)

And we're going to call dot stack。And we'll see what that looks like。

And we see that it's going to be our original index， and then each one of the columns。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_132.png)

And then it's finally going to have the value for each one of the different correlations。

 So this actually becomes clear as we go through the other steps。 we go two frame。

 This will change it to a pandas data frame。

![](img/44b9d00c4609e8d52e8498aeed0bcf81_134.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_135.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_136.png)

And we see here that we have the correlation between Teabody acine x and each one of these different values。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_138.png)

Just in a single data frame。The next thing that we do is reset the index。

 So we're going to call dot reset index。

![](img/44b9d00c4609e8d52e8498aeed0bcf81_140.png)

And now we see that we clearly have the different correlations and then their values。

 And then we're renaming each one of these values from level 0 to feature 1， level 1 to feature 2。

 And then our 0 column that we had here。

![](img/44b9d00c4609e8d52e8498aeed0bcf81_142.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_143.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_144.png)

Is going to be set equal to correlation。

![](img/44b9d00c4609e8d52e8498aeed0bcf81_146.png)

So we're going to end up with this new matrix core values。

 and then we are also going to create one new column called Abs correlation。

 which is just going to be the absolute value of that correlation because all we care about is the magnitude。

 not whether it's positive or negative。

![](img/44b9d00c4609e8d52e8498aeed0bcf81_148.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_149.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_150.png)

So I'm going to run this full thing， this full cell it's going to take about five seconds to get it done and then we can start to plot out so you see that that's done。

 we are going to start to plot out each one of the different correlations to see the distribution of higher versus lower correlations between each one of these different columns。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_152.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_153.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_154.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_155.png)

So we're setting our axis and that's going to be equal to our abs correlation， right。

 this is our data frame， this is going to be the column。

 and then we're calling a histogram with 50 bins。

![](img/44b9d00c4609e8d52e8498aeed0bcf81_157.png)

And then we can just set our X label and our Y label。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_159.png)

So we run this and we see that most of the time there only there's essentially zero correlation。

 and then we see much less at the top end that there's close to one in terms of correlation。

 but otherwise maybe a couple of different modes here， but really fairly uniform across。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_161.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_162.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_163.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_164.png)

At once it dips down from those lower values。

![](img/44b9d00c4609e8d52e8498aeed0bcf81_166.png)

So then we're going to say， let's look at the most highly correlated values。

 we're going to sort the values by correlation。

![](img/44b9d00c4609e8d52e8498aeed0bcf81_168.png)

With ascending equals false， so we're going to be going from top to bottom。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_170.png)

And then we just do duckuck query， that's a way to filter down our database similar to what we've done in brackets before。

 we call D query。

![](img/44b9d00c4609e8d52e8498aeed0bcf81_172.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_173.png)

And then we can just pass in the column name。 We only want the absolute correlation greater than 0。8。

 and we can look at those values， and we see them all the way through the first 22000 rows that we have for this。

 And if we look at the actual。

![](img/44b9d00c4609e8d52e8498aeed0bcf81_175.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_176.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_177.png)

Size， actually， let's go right here， the actual size of the original core values data frame。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_179.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_180.png)

This is going to be out of 1 hundred 57000 different values because it's each one of the different cross correlations。

 which is why we have so many possible values。 So here we see。

 and we can explore this further how highly correlated many of these two values are。

 And when we see something that's so highly correlated。

 we may want to do some type of feature engineering or feature selection。

 which we'll talk about further along as we go through this course。



![](img/44b9d00c4609e8d52e8498aeed0bcf81_182.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_183.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_184.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_185.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_186.png)

That closes out this section here in the next video we'll continue in the notebook and discuss the test train split。

 thank you。

![](img/44b9d00c4609e8d52e8498aeed0bcf81_188.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_189.png)

![](img/44b9d00c4609e8d52e8498aeed0bcf81_190.png)