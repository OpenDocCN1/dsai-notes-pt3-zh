# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P32：31_特征工程实验解决方案（选修部分）第3部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Alright， welcome back。 Let's get to some fancy features over here。

And so to close out our introduction to feature engineering in this notebook。

 we're going to consider a more complex type of feature that may work really nicely for certain problems Now I'm going to explain this and will become clearer as I actually walk through the code piece by piece。

 but what we're doing here is creating features that capture where a feature value lies relative to other members of the category that it belongs to。

So in particular， we're calculating deviance of a row feature value from the mean value within the category that that row belongs to。



![](img/51916725d59d753def6378c75a4f0fc6_1.png)

And this helps capture information about our feature relative to the category's distribution。

 for example， how nice a house is relative to other houses within the neighborhood。



![](img/51916725d59d753def6378c75a4f0fc6_3.png)

![](img/51916725d59d753def6378c75a4f0fc6_4.png)

So we're going to use the function that we have here and I'm going to break out this function if you look at the cell below it actually has the。

 we're actually going to run the function that we have。

 but I'm going to break out the code from within the function so we can see it' step by step。



![](img/51916725d59d753def6378c75a4f0fc6_6.png)

![](img/51916725d59d753def6378c75a4f0fc6_7.png)

So letm going to create a cell above。And we're going to start off here with X4。

 which is the data frame if you notice step by step。

 we've been creating copies of the data frame x4 is that smaller version of the data frame and the only categorical value that we have here is neighborhood So we're going to use the neighborhood variable。



![](img/51916725d59d753def6378c75a4f0fc6_9.png)

![](img/51916725d59d753def6378c75a4f0fc6_10.png)

![](img/51916725d59d753def6378c75a4f0fc6_11.png)

And the first thing that we're going to do is replicate this portion of the function that we have here。



![](img/51916725d59d753def6378c75a4f0fc6_13.png)

So we're going to use that dot group by function that we saw earlier in a prior notebook。



![](img/51916725d59d753def6378c75a4f0fc6_15.png)

And we're going to group by neighborhood。Which is our categorical variable。

And we're going to do the same thing that we have in the output two cells below where we're going to look at overall quality。

 so we're looking at the overall quality per neighborhood。



![](img/51916725d59d753def6378c75a4f0fc6_17.png)

![](img/51916725d59d753def6378c75a4f0fc6_18.png)

So right now when I run this， we just have app panda as a group by Op last time we did dot mean and we would get just to show you again what that does。



![](img/51916725d59d753def6378c75a4f0fc6_20.png)

We can see the mean for each one of our neighborhoods。 we might do dot Ag and come up with。



![](img/51916725d59d753def6378c75a4f0fc6_22.png)

Some different type of aggregation metric， if we'd like。



![](img/51916725d59d753def6378c75a4f0fc6_24.png)

But we're not going to do either of them， We're going to do something different with our group by object we're going use the dot transform。

And what the dot transform does is it's going to allow us to come up with a value for every single row。

 so it's going to be similar to the group by where it's going to come up with the same value as long as you're within the same category。

 but you're not going to be limited down to a smaller data frame。

 the data frame is going to say the same size。So to show you what I mean there。

 we're going to run the next piece of code， Lambda X x dot mean。



![](img/51916725d59d753def6378c75a4f0fc6_26.png)

So we're getting the mean value of overall quality by neighborhood。

And what you see is we have the same number of rows as we do in our original data frame。

 And you see repeat values。 And what this does is that you now have a column。



![](img/51916725d59d753def6378c75a4f0fc6_28.png)

Or a panda series that's the same size as a regular column within this data frame。

 So you see all these repeats mean that they're going to be from the same neighborhood。

 and then you see it changes。 Then you see a couple more repeats。

 These are all from a different neighborhood。 And those are the mean values by neighborhood。



![](img/51916725d59d753def6378c75a4f0fc6_30.png)

![](img/51916725d59d753def6378c75a4f0fc6_31.png)

![](img/51916725d59d753def6378c75a4f0fc6_32.png)

So we do that in order to get the mean value by neighborhood。

 then we get the standard deviation by neighborhoodigh。



![](img/51916725d59d753def6378c75a4f0fc6_34.png)

![](img/51916725d59d753def6378c75a4f0fc6_35.png)

RightAnd that's our standard deviation。

![](img/51916725d59d753def6378c75a4f0fc6_37.png)

And then to create our new feature。We take now X feature is just going to be our overall quality。



![](img/51916725d59d753def6378c75a4f0fc6_39.png)

And that overall quality that we have， we're going to subtract the mean and divide by the standard deviation。

 according to those different categories。 So what that does is it allows you to see the deviation which in within each one of those neighborhoods。



![](img/51916725d59d753def6378c75a4f0fc6_41.png)

![](img/51916725d59d753def6378c75a4f0fc6_42.png)

![](img/51916725d59d753def6378c75a4f0fc6_43.png)

So it kind of adds a little bit of complexity complexity rather than looking at the overall variation。

 you're looking at variation that is。Inclusive within that neighborhood or within whatever group by object you decide。

And then finally， you're going to take your input was a data frame， that's what this x is。

 and you're going to create a new category， a new column that's just going to be called whatever the feature was。

 so overall quality。

![](img/51916725d59d753def6378c75a4f0fc6_45.png)

Or neighborhood and the deviation， or yeah， overall quality than the deviation for the overall quality within the neighborhood。



![](img/51916725d59d753def6378c75a4f0fc6_47.png)

![](img/51916725d59d753def6378c75a4f0fc6_48.png)

And we're going to set that equal to that deviation feature that we have defined over here。



![](img/51916725d59d753def6378c75a4f0fc6_50.png)

So to see the final results， we're going to。

![](img/51916725d59d753def6378c75a4f0fc6_52.png)

First， we had to bring in house style because we're going to use Ha styleyle as one of our categories。

 And as we mentioned up here， we only have neighborhood currently within our X4 data frame。



![](img/51916725d59d753def6378c75a4f0fc6_54.png)

![](img/51916725d59d753def6378c75a4f0fc6_55.png)

So bringing x5 from our DF object that we defined earlier。

 the columns are the same length so it can bring them right in。



![](img/51916725d59d753def6378c75a4f0fc6_57.png)

And we run this add deviation feature function that we just defined as going to find the deviation within each category。



![](img/51916725d59d753def6378c75a4f0fc6_59.png)

And we're going to do that with year built as the one of the。



![](img/51916725d59d753def6378c75a4f0fc6_61.png)

Nummerical values and house style as the categorical value。

 and then we're going to do the same thing with neighborhood as our categorical value and overall quality as our numerical value。



![](img/51916725d59d753def6378c75a4f0fc6_63.png)

I'm going to run this。And let's look at x5 now。

![](img/51916725d59d753def6378c75a4f0fc6_65.png)

And we see all the way at the end that we've created these new columns where we see that。Negative 0。

59 means that for this year for this house style， this was earlier than the average year for this house style。

 and then this is above the average for that specific house style。

So that's going to tell us you're by， if you're looking by house style。

 whether that year built is higher or lower compared to the average within that certain house style。



![](img/51916725d59d753def6378c75a4f0fc6_67.png)

![](img/51916725d59d753def6378c75a4f0fc6_68.png)

And the same for overall quality by neighborhood， we see that this is a higher overall quality within its neighborhood compared to this one。

 within its neighborhood。

![](img/51916725d59d753def6378c75a4f0fc6_70.png)

![](img/51916725d59d753def6378c75a4f0fc6_71.png)

![](img/51916725d59d753def6378c75a4f0fc6_72.png)

Okay， so we introduced polynomial features earlier now we're going to show you how to do polynomial features in psyitL we went over this in the lesson I want to show you the output lied as we run through the code as well。

 and this will give you an introduction to how SK learned preprocessing actually works and will be a big part of your machine learning workflow。

So we're going to from SKLarn。 preprocess， import the polynomial features。

We have to instantiate the polynomial features object here we're specifying the degree to we can pass in whichever degree we would like to pass in。



![](img/51916725d59d753def6378c75a4f0fc6_74.png)

![](img/51916725d59d753def6378c75a4f0fc6_75.png)

![](img/51916725d59d753def6378c75a4f0fc6_76.png)

We're going to specify here just which features we want to actually run this polynomial function on。



![](img/51916725d59d753def6378c75a4f0fc6_78.png)

So we're going to fit it on these two features， lot area and overall quality。



![](img/51916725d59d753def6378c75a4f0fc6_80.png)

![](img/51916725d59d753def6378c75a4f0fc6_81.png)

What we cant what we can do here is see what are going to be the outputs。

 so if we wanted the actual names， we'd have to figure out a way to input them in。

 but what we have is。

![](img/51916725d59d753def6378c75a4f0fc6_83.png)

The first value is going to be x not， which is going to be lot area。

 The second value x1 is going to refer to overall quality and when we run this polynomial features。

 we don't just get x1 and x2。 We don't just get that squared。

 so we don't just have lot area squared in overall quality squared。

One is going to represent the intercept value。X0 is going to represent law area， x1 overall quality。

 then we have law area squared， then we also have the interaction term between our two variables that we passed in and we have x1 squared。



![](img/51916725d59d753def6378c75a4f0fc6_85.png)

![](img/51916725d59d753def6378c75a4f0fc6_86.png)

So by default， the polynomial features is going to provide all of these extra columns from just these two columns that we started off with。



![](img/51916725d59d753def6378c75a4f0fc6_88.png)

We then run P， which is our object we did fit before we run transform。



![](img/51916725d59d753def6378c75a4f0fc6_90.png)

![](img/51916725d59d753def6378c75a4f0fc6_91.png)

So we're transforming our variables from just those two columns to all of these features that we have here。



![](img/51916725d59d753def6378c75a4f0fc6_93.png)

And then we're going to take that output of an array to see what each one of those columns are。



![](img/51916725d59d753def6378c75a4f0fc6_95.png)

You see we run the get feature names and the input features equals to our features。

 which we defined here， just so that we know that we are replacing x not with law area and x1 with overall quality。



![](img/51916725d59d753def6378c75a4f0fc6_97.png)

And we see we get one lot area， overall quality， again， one being the inters。

 lot area squared lot area times overall quality and overall quality squared。

 And these from your original two parameter your two features， you now have。



![](img/51916725d59d753def6378c75a4f0fc6_99.png)

![](img/51916725d59d753def6378c75a4f0fc6_100.png)

![](img/51916725d59d753def6378c75a4f0fc6_101.png)

What is it？5 new features，1，2，3，6 new features if you count the interet。



![](img/51916725d59d753def6378c75a4f0fc6_103.png)

And instead of having just two parameters that you're trying to learn， you can learn six parameters。

That closes out this section on feature engineering Look forward to seeing you back in lecture Thank you。



![](img/51916725d59d753def6378c75a4f0fc6_105.png)

![](img/51916725d59d753def6378c75a4f0fc6_106.png)

![](img/51916725d59d753def6378c75a4f0fc6_107.png)