# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P63：14_训练集和测试集分割实验（选修部分）第2部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Welcome back to our notebook and this video we're just going to focus on question three。

Not because Question three is incredibly complicated。

 but rather because there's a lot of important concepts that we'll introduce。

 that'll be important to keeping in your toolkit as you move along on your machine learning journey。



![](img/3d38103bacdc97251250451abc8c3395_1.png)

So this question asks us to create a new data set where all of the above categorical features that we just discussed will be one hot and coded。

And we can fit this data and see how it' will end up affecting our results compared to not including these one hot encoded categorical variables。

So we're going to use the data frame doc copy， taking our pandas data frame。

 use that dot copy method in order to create a completely separate copy of our data frame that we will use for one hot encoding on this data frame we will one hoten each of the appropriate columns and then add it back to the data frame。



![](img/3d38103bacdc97251250451abc8c3395_3.png)

And then as we do this， we also have to make sure to drop that original column that was just an object or all the values or strings。

And then going back to the original data that are not one hot and coded。

 we also have to make sure that we drop all the string categoricals because we can't pass strings into any of our models。

And for the one hot encoding step， we're going to want to use one hot encoder。We've introduced PDd。

ge dummies earlier。This will be a different way of doing the same thing one as PDd。 get dummies。

 but it'll do it in a more efficient manner for when you are expanding your data set beyond you know just 100 or 200 variables。

 but often it'll blow up into a matrix that's 1000 columns 2000 columns， so on。

 and that can eat up a lot of memory。

![](img/3d38103bacdc97251250451abc8c3395_5.png)

And we will use here within one hot and coding。The sparse matrix。

 rather than just outputting the full data frame， and we'll see that in practice in just a little bit。

So we're going to start off by importing the one hot encoder from SK learn do preprocessing。



![](img/3d38103bacdc97251250451abc8c3395_7.png)

We're then going to make a copy of the data。 We have data do copy using that method that we discuss。

 and then we have data underscore OHC as our new pandas data frame that is a copy that won't affect data。



![](img/3d38103bacdc97251250451abc8c3395_9.png)

![](img/3d38103bacdc97251250451abc8c3395_10.png)

We're then going to initiate our one hot Enr encoding object。

And we're doing this similar to how we do it with all of our S K learn objects。

 What's important to note here is you can pass in certain arguments。

And an important argument to take note of。For those that want to do linear regression and ensure that their model is interpretable。

 we talked about prediction versus interpretability。

One of the things that you're going to want to do is drop the first value from your dummy variables。

 So I'll show you why in a second。 So this is an argument that's available。

 We're not going to do it here， but I just want to show you that it is available。



![](img/3d38103bacdc97251250451abc8c3395_12.png)

And the idea being， if you imagine you have a， let's say， with our housing， we had a column。

 that's either beachfront or not beachfront。 So one， it start off with one column。

 We expand it to two。And then the last value is going to be the red， the price。

 let's just say it's five for the first one and。For our second one。It's not going to be beachfront。

 so it'll be zero for the first new column， one for the next one。

 and let's say this one is going to evaluate two。

![](img/3d38103bacdc97251250451abc8c3395_14.png)

Four for its median dial。So we see here that the first column is indicating it is beachfront。

 the second column that it's not beachfront。And when we do linear regression。

 if we remember the model。If we don't drop one of these columns。

 we can end up with an infinite amount of difference。Coefics， in order to define。

Coicient for the first column and the second column。

 So imagine if we're trying to get to the numbers 5 and 4。

 and we can start off with the intercept equal to one， and then。

The coefficient for our first column would be four， so one plus four is equal to our five。

And then for the second column， since we're starting off with one， the second coefficient would be 3。

 and we do 1 plus3 equals 4， and that would work。 but on the same note。

 we could have started with the first coefficient equal to the intercept being equal to5。

And then our first value being equal to 0。 and we'd end up with five。And then for the second one。

 we just set the second coefficient to negative one。

And what I'm showing here is that if you don't drop one of these columns。

 you can end up with an infinite amount of what your intercept would be。

 what your first coefficient would be and what your second coefficient could be。

 because the first column and the second column are completely dependent on one another。

There's complete multicolinearity when the first column is one。

 the second column is always zero and vice versa。So if we dropped one of these columns。

 so let's say we dropped the column of not beachfront。



![](img/3d38103bacdc97251250451abc8c3395_16.png)

![](img/3d38103bacdc97251250451abc8c3395_17.png)

Then we can only have one option。

![](img/3d38103bacdc97251250451abc8c3395_19.png)

Because our intercept will have to be four， because we only have one coefficient， is it beach front？

So the first one our intercept is four， so4 plus0 equals 4。

 and then our intercept is equal to one here。Because and that'll tell us that the beachfront will add an extra dollar of value to our median value。

And that's interpretable。 The coefficients will actually make sense。

 And we don't have to worry about that multicolineity。

 messing with the interpretability of our coefficients。 So that's the danger of multicolineity。

 It probably will not affect your predictions。 but it will affect the predictability。

 The interpretability， excuse me。

![](img/3d38103bacdc97251250451abc8c3395_21.png)

So if you want high interpretability when you're looking back at your coefficients that you've learned。

 make sure that you use this drop first， and that's also available on PDd。ge dummies。



![](img/3d38103bacdc97251250451abc8c3395_23.png)

Now I'm going to remove this here we're just focusing on predictability。

 so it won't have too much of an effect， and I wanted to match up with the number that we came up earlier this 215 and that doesn't take into account that we're dropping one of the columns。

 but best practice will generally be to drop one of these columns。



![](img/3d38103bacdc97251250451abc8c3395_25.png)

![](img/3d38103bacdc97251250451abc8c3395_26.png)

![](img/3d38103bacdc97251250451abc8c3395_27.png)

Now， for each column in our。Values here。 So this， if you recall。



![](img/3d38103bacdc97251250451abc8c3395_29.png)

Let's start with just the。

![](img/3d38103bacdc97251250451abc8c3395_31.png)

Variable nu underscore OHC underscore columns was just our panda series with all of our unique columns that are categorical。

 when we say indexed then we're just going to be looping through each one of these individual columns。



![](img/3d38103bacdc97251250451abc8c3395_33.png)

![](img/3d38103bacdc97251250451abc8c3395_34.png)

![](img/3d38103bacdc97251250451abc8c3395_35.png)

So in order to make this example clear of what's happening within the for loop， let's set。



![](img/3d38103bacdc97251250451abc8c3395_37.png)

Everything above as we go through it， so we're going to set call equals to neighborhood just to see a single example。



![](img/3d38103bacdc97251250451abc8c3395_39.png)

The first thing that we're going to do。

![](img/3d38103bacdc97251250451abc8c3395_41.png)

Is use our fit transform of our one hot encoder that we are defining。



![](img/3d38103bacdc97251250451abc8c3395_43.png)

Now， I'm going to have to pull that in。 I'm have to pull both of these in in order for this to work。

 because I have to initiate those values of the。

![](img/3d38103bacdc97251250451abc8c3395_45.png)

![](img/3d38103bacdc97251250451abc8c3395_46.png)

Copy of the data as well as the oneheim encoder objects。

Then I use the one hot encoder to fit and transform just this individual column。

Now another key concept that we're learning， so we learned about the importance of dropping one of the columns。

 another key concept is if you see I have two brackets here。

What that's doing for me is is ensuring that rather than just pulling out that column。

 which would only have one dimension in terms of its length。

When I put double brackets it's going to output as a data frame。

 and that's going to have two dimensions， one of those dimensions just equal to one。

 but the other one the length of the data frame。

![](img/3d38103bacdc97251250451abc8c3395_48.png)

And just to make that clear before I tell you why that's so important， we have， let's say。

 data neighborhood， which is with just one bracket。



![](img/3d38103bacdc97251250451abc8c3395_50.png)

![](img/3d38103bacdc97251250451abc8c3395_51.png)

I misspelled it。And if I doductt shape here。

![](img/3d38103bacdc97251250451abc8c3395_53.png)

You see that it only has one value。1379， it is a one dimensional array。 If I do two brackets。First。

 let's see what that looks like。

![](img/3d38103bacdc97251250451abc8c3395_55.png)

That'll be a data frame now。 And if I look at the shape。



![](img/3d38103bacdc97251250451abc8c3395_57.png)

Itll be 1379 by one。 So 1379 rows by one column。 And the reason why this is important is because when you pass in to your different S K learn transformers or predictors with linear regression in just a bit。

You will often get this error that it will not work because you don't have the appropriate number of dimensions。



![](img/3d38103bacdc97251250451abc8c3395_59.png)

And you need to ensure that you have two dimensions whenever you pass into many of these SKLar objects。



![](img/3d38103bacdc97251250451abc8c3395_61.png)

So that's the idea behind these two brackets that' will be important to use throughout as you continue to use SK learns objects。



![](img/3d38103bacdc97251250451abc8c3395_63.png)

![](img/3d38103bacdc97251250451abc8c3395_64.png)

So I'm going to run this。

![](img/3d38103bacdc97251250451abc8c3395_66.png)

I didn't import one hot encoder。We're going to have to import that as well。



![](img/3d38103bacdc97251250451abc8c3395_68.png)

And。

![](img/3d38103bacdc97251250451abc8c3395_70.png)

Now， we have our new。Data。

![](img/3d38103bacdc97251250451abc8c3395_72.png)

Which is just going to be a sparse matrix。Now this is going to be another important concept。

 the idea again， which I mentioned earlier， is that you will actually be able to save a lot of memory when that matrix blows up。

Now， to show you what that actually looks like， I'm going to run PD。 data frame。

And this won't get it to its normal data frame， but rather output these funky values that you see here。



![](img/3d38103bacdc97251250451abc8c3395_74.png)

And what these values mean is that it's just now we've blown up probably one column was initially one column we would have blown it up into。

 I believe， around 25 columns， depending on how many we have for neighborhood。

 we see neighborhood list 25 so we would have blown this up into 25 columns。

 rather than creating 25 new columns， we just say。

![](img/3d38103bacdc97251250451abc8c3395_76.png)

![](img/3d38103bacdc97251250451abc8c3395_77.png)

We are going to ignore zeros。That's what this zero is here for。

And we're going to say where the one is within our sparse matrix。

 So here it's within the fifth column。 Here it's the 24th column。

 And here it's the fifth column again。 So the zeroth index and the second index should have similar。



![](img/3d38103bacdc97251250451abc8c3395_79.png)

Or the same exact values， so if we look back at data neighborhood， you'll see that zero and two。

 both our college CR。

![](img/3d38103bacdc97251250451abc8c3395_81.png)

![](img/3d38103bacdc97251250451abc8c3395_82.png)

So that's why we have five and five。 So that sparse matrix is going to allow you to save a lot of memory。



![](img/3d38103bacdc97251250451abc8c3395_84.png)

Now we just wanted to show you how that worked and we can pass in these sparse matrices into our SK learn models。

 so you won't have to put these back into data frames。

 but they're a little bit more difficult to look at so later on we're actually going to change us back to an array and just to see how that looks it would just be like this and this is going to be our 25 columns where we have one for five men zeros otherwise。



![](img/3d38103bacdc97251250451abc8c3395_86.png)

![](img/3d38103bacdc97251250451abc8c3395_87.png)

![](img/3d38103bacdc97251250451abc8c3395_88.png)

![](img/3d38103bacdc97251250451abc8c3395_89.png)

And this， again， would take up a lot more memory。 But for our current process。

 it won't be too much memory。 You can think if you are doing any type of natural language processing。

😊，How intense this can get when you're trying to one hot and code every single word。

 how big that matrix can get。

![](img/3d38103bacdc97251250451abc8c3395_91.png)

![](img/3d38103bacdc97251250451abc8c3395_92.png)

So we have new dot， which is just a sparse matrix。

![](img/3d38103bacdc97251250451abc8c3395_94.png)

We're then going to drop the original column。

![](img/3d38103bacdc97251250451abc8c3395_96.png)

From our copy of the data set， because we do not want that anymore。

 we now have the one hot encoded version of that column。



![](img/3d38103bacdc97251250451abc8c3395_98.png)

We're then going to pull out the names of each one of the values。

 and this will just be for interpretability。

![](img/3d38103bacdc97251250451abc8c3395_100.png)

To show you what that looks like。

![](img/3d38103bacdc97251250451abc8c3395_102.png)

These are just going to be all the unique values that are available within the neighborhood。

 and they will align with this 0，1，2，3，4， etc cetera。

 column by column so that you'll be able to know the name of each one of those columns。



![](img/3d38103bacdc97251250451abc8c3395_104.png)

![](img/3d38103bacdc97251250451abc8c3395_105.png)

We're also going to want to join that with the original column that we pulled out。



![](img/3d38103bacdc97251250451abc8c3395_107.png)

So we're going to join neighborhood that's the name of the column with the category。

 which is either Bloomington， Blue West， and so on。



![](img/3d38103bacdc97251250451abc8c3395_109.png)

![](img/3d38103bacdc97251250451abc8c3395_110.png)

For every single category in cats zero， the reason why we say Cats zero is because this is an array and within that array is our list。



![](img/3d38103bacdc97251250451abc8c3395_112.png)

So。Now Os our array， so here you just see were still working with an array。

 and then we can index the first value second value from there。



![](img/3d38103bacdc97251250451abc8c3395_114.png)

![](img/3d38103bacdc97251250451abc8c3395_115.png)

And then we create our new data frame， and that's going to be equal to PDd dot data frame。

 which is just going to transform an array into a data frame。



![](img/3d38103bacdc97251250451abc8c3395_117.png)

We're going to use that two array that we saw up here。



![](img/3d38103bacdc97251250451abc8c3395_119.png)

Will'll translate this into actual。

![](img/3d38103bacdc97251250451abc8c3395_121.png)

Into an actual data frame。And then we're going to set columns equal to our new columns that we have defined up here。

 I'm going to run this just so that we can see what that looks like。



![](img/3d38103bacdc97251250451abc8c3395_123.png)

![](img/3d38103bacdc97251250451abc8c3395_124.png)

![](img/3d38103bacdc97251250451abc8c3395_125.png)

And then we can see that our new Df。

![](img/3d38103bacdc97251250451abc8c3395_127.png)

Will， output。

![](img/3d38103bacdc97251250451abc8c3395_129.png)

This new data frame which has neighborhood Bloomington， neighborhood Blue West。

 and so on and so forth so that we can correctly identify which one of these different unique values we are looking at within the column that we started with。



![](img/3d38103bacdc97251250451abc8c3395_131.png)

![](img/3d38103bacdc97251250451abc8c3395_132.png)

And then finally， you are going to take our copy of the data。



![](img/3d38103bacdc97251250451abc8c3395_134.png)

And simply concatenate that with this new D that we have created up here。



![](img/3d38103bacdc97251250451abc8c3395_136.png)

And that's going to create all of our new columns When we do the Conca on access one。

 we're just putting it to the right of it。 So we're continually adding this to the right of our data frame。



![](img/3d38103bacdc97251250451abc8c3395_138.png)

You look above， this will have the same number of rows every single time so we can keep adding on to the right。



![](img/3d38103bacdc97251250451abc8c3395_140.png)

So we're running a for loop， so data underscore OHC just keeps equaling itself plus all of these new columns。



![](img/3d38103bacdc97251250451abc8c3395_142.png)

So I'm going to run all of that。Then we can say， what is the difference in terms of our columns？

From the original data frame to our new data frame。 So this is our new data frame。

 When we run dot shape， we get rows and columns。 We only want the number of columns。

 So we take index1， and we subtract the data dot shape that we originally had。

 And you see we have 215 new columns， which matches up with what we predicted early on with 215 columns。



![](img/3d38103bacdc97251250451abc8c3395_144.png)

![](img/3d38103bacdc97251250451abc8c3395_145.png)

![](img/3d38103bacdc97251250451abc8c3395_146.png)

And then finally， because we want to test with our original data frame。

 we have to drop of all those original columns that were strings。

 otherwise we'll not be able to pass through our original data。



![](img/3d38103bacdc97251250451abc8c3395_148.png)

So we just do data。 droprop。We're dropping the numb underscore OatC underscore calls。

 those are just our object values。Dot indexd will just give us a list of just those names and axis equals 1 is just that we're dropping columns and not rows。



![](img/3d38103bacdc97251250451abc8c3395_150.png)

![](img/3d38103bacdc97251250451abc8c3395_151.png)

And we can see that we take it from 80 columns down to 37， because we are subtracting。



![](img/3d38103bacdc97251250451abc8c3395_153.png)

43 values。

![](img/3d38103bacdc97251250451abc8c3395_155.png)

If we look here， right？We had 43 values， we dropped all those object values。



![](img/3d38103bacdc97251250451abc8c3395_157.png)

All right。So that's question3， really in depth， hopefully you now understand why we may want to drop certain columns understanding what a sparse matrix is。

 as well as how to use the one hot encoder in order to add on new columns to our data frame in a similar fashion that we did with PD。

 get dumies。

![](img/3d38103bacdc97251250451abc8c3395_159.png)

![](img/3d38103bacdc97251250451abc8c3395_160.png)

![](img/3d38103bacdc97251250451abc8c3395_161.png)

![](img/3d38103bacdc97251250451abc8c3395_162.png)

In the next lesson， we will get into our train test split and I look forward to seeing you there。



![](img/3d38103bacdc97251250451abc8c3395_164.png)

![](img/3d38103bacdc97251250451abc8c3395_165.png)