# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P86：37_正则化详细信息（选修部分）第1部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_0.png)

Welcome to the notebook。 Here we will go over all the solutions for our regularization lab。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_2.png)

The learning objectives that we had here were to implement data standardization。

 as well as a refresher on seeing what goes on under the hood of standardization。

 we're going to implement variants of regularized regression such as Lasso and Rige。

 and then we're going to combine standardization with our train test foot procedure as we have done before。

 and implement regularization to prevent overfitting within our regression problems。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_4.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_5.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_6.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_7.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_8.png)

So we're going to import Ny pandas， we're also going to use that helper file that we discussed in earlier labs that will allow us to bring in this Boston data。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_10.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_11.png)

Were then able to set Boston equal to our Boston data frame。

 which is pulled out from the helper file， we then will get both the Boston data and the Boston description so that if we want to look later at each one of our fields。

 we can pull that out with Boston description。

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_13.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_14.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_15.png)

Otherwise， we're just going to be working with Boston data， which is now a pandas data frame。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_17.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_18.png)

So in regards to standardization， we know that standardizing data refers to transforming each variable。

 so that is more closely following a standard normal distribution。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_20.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_21.png)

That standard normal distribution will also have a mean of 0 and a standard deviation of one。

 So we'll be subtracting the mean and dividing by the standard deviation。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_23.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_24.png)

So first we're going to generate our X and y， our features and our outcome variable。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_26.png)

We set y call equal to the string M V， which is just the median value for each one of our households。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_28.png)

And then the Boston data， we're going to drop this y column from our columns。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_30.png)

And set that equal to X， X being our feature variables。

 and then y is going to be our outcome variable。

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_32.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_33.png)

We're then going to import our standard Scalar and then quickly do our fit transform on our X data here。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_35.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_36.png)

So now we start our off with our object， as we always do， s is equal to our standard scalar。

 and then we can call fit transform on our X。

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_38.png)

Now I want you to be thinking， obviously， if we are going to have a train and test split。

 we would do this a bit differently。

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_40.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_41.png)

And we'll discuss that in a couple more cells。

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_43.png)

So first， we want to confirm that the standard scaling is working appropriately。

 The way that we want to do this is to have you work using nuy in order to recreate the standardization on your own。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_45.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_46.png)

So the hints that we add here is that if you had your array。

 which is now going to be two rows and three columns。

 we can call a dot mean and if we specify in axis， we can get the mean value across either all of the columns or all of the rows。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_48.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_49.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_50.png)

And because we are trying to standardize each column。

 we obviously want to be working with the mean across all the columns。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_52.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_53.png)

We also want to be getting the standard deviation across each one of the columns。

 and then we can subtract the meanme using this。

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_55.png)

Dot meme method that's available for our Numpy arrays， as well as the dot SD method。

 which is available with Numpy arrays as well。

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_57.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_58.png)

We set x2 equal to just the array version of our x。

 which is our pandas data frame with all of our features。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_60.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_61.png)

We're going to do a manual transformation， we'll call that man transform。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_63.png)

And with that we're going to do x2， which is just going to be our new nuly array。

 which is all of our features， subtract the mean with the axis equal to0。 So looking back to here。

 we'd be essentially subtracting each one of our different mean values for that column and then dividing by the standard deviation for that column。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_65.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_66.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_67.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_68.png)

And that should be all that your standard Scalr should be doing under the hood。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_70.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_71.png)

We're then going to check that the solution of this will end up being equal to one another XSS being this。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_73.png)

Standard scaled version of our original data frame that we have up here。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_75.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_76.png)

Using the standard Scalar。And man transform is our new array where we。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_78.png)

Created that manual transformation of the standard scalealar on our own。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_80.png)

The NP the all close is just telling us that every single value and two arrays are very similar to one another by very similar。

 we mean that there may be。

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_82.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_83.png)

Under the hood， some type of。Small difference due to just rounding error。

 So it'd be something like the 10th decimal point can be difference。

 And that's what the nupi do all close。 And that'll be useful as we use different means of coming up with the same solution and trying to ensure that they are all the same values。

 All the outcomes of the same values。 So we call N do all close。 and we see that that is true。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_85.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_86.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_87.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_88.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_89.png)

Now let's look at now that we've scaled our data and we have the scaled and non scaled version。

 I am going to go in and create a linear regression object and fit our model to both our standardized and our nonstandized version of our X data。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_91.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_92.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_93.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_94.png)

So first， we initiate our linear Russian objects。

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_96.png)

We have our X and our Y variables again initiated to their original form。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_98.png)

Then we could just call LR。 fit LR being our linear regression object。

 we're fitting it on our X and on our Y， and then once we do that we can see the coefficients that it has learned。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_100.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_101.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_102.png)

And we see that the coefficients on our widely different scales。And we have the question underneath。

 is this a bad thing， It's not necessarily a bad thing。

 So in regards to interpretability in regards to how much will one unit change in each one of these columns。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_104.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_105.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_106.png)

Change the outcome variable。 This is much more interpretable。

 So one unit change in whatever this coefficient is。 The first one will subtract 010。

108 from our median value household。 So in that regards， it's much more interpretable。

 But in regards to figuring out which one of these different coefficients has the largest effect on the outcome of our median value。

 Which ones the most important feature。

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_108.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_109.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_110.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_111.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_112.png)

We're not able to see that because that is now dependent。

 because each one of these coefficients are dependent on the scale of those original features。

 as we've discussed in prior lectures。

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_114.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_115.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_116.png)

So now let's scale our data as we did before， we do our standard Scalar。

 XSs is just our transformed version of our features。 We create a new linear Russian object。

 We'll call it L R2。 And then when we print these out。

 we are able to see each one of these different coefficients。 Now they are all on the same scale。

 So now a larger value means that it has a larger positive or negative， whatever it is。

 But a larger impact on our actual outcome variable。😊。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_118.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_119.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_120.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_121.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_122.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_123.png)

So as one of these features varies by a single standard deviation。

 we see how largely that will affect our median value households。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_125.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_126.png)

So now using what we have here， we want to find the most impactful feature。

 all we're going to do is zip together。

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_128.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_129.png)

Our columns and our coefficients， as we've noticed so far。

 our coefficients are not coming with the names of each one of those coefficients。

 So what we're going to want to do is zip together。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_131.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_132.png)

The X dot columns and the coefficients themselves so that they're aligned。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_134.png)

One with the other， which we'll see in a second， and then we're going to put this into a data frame。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_136.png)

So we see here that Lt， which is just the lower status of the area。

 is associated with the very lowest number and R M， which stands for the number of rooms。

 is associated with the highest coefficient， which makes sense。 The more rooms we have。

 the higher our median value for our household would be， and the lower the status of the。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_138.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_139.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_140.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_141.png)

Surrounding area， the lower our median value of our household would be。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_143.png)

And that's the idea of getting the magnitude of each one of these coefficients。



![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_145.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_146.png)

So that closes out the section， working just with linear regression。

 as well as standardizing the coefficients and reviewing how that can be used in order to find feature importance。

 Next， we will move into working with Lasso regression and see the scaling and without scaling for lasso regression as well。

 Thank you。

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_148.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_149.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_150.png)

![](img/2bfd6be60b4fc6c9f1dcc4b575b617d0_151.png)