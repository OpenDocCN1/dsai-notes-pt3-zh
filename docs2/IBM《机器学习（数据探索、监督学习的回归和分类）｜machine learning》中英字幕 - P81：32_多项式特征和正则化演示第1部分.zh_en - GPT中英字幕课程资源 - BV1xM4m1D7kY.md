# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P81：32_多项式特征和正则化演示第1部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/b2ac712cb25f0490f3a7935794d0e97c_0.png)

Welcome to our demo notebook here on regularization here。

 we will show you something very similar to what we saw in lecture and that we will have a true underlying function。

 We will have some data points， which are just the actual underlying function plus random noise that we don't want to fit to。

 and then we'll see how we can use regularization as well as polynomial features and linear regression。

 in order to come up with the underlying model。 So that's going to be the goal for the first part of this demo。

 We're going to import the needed libraries such as OSs， pandas， numpy， mappllib and seaborn。



![](img/b2ac712cb25f0490f3a7935794d0e97c_2.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_3.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_4.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_5.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_6.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_7.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_8.png)

We're going to set our data path equal to data that is just the folder where our data actually exists。



![](img/b2ac712cb25f0490f3a7935794d0e97c_10.png)

And then in part one， we're going to import our data。

 which is just going to be in this X underscore y underscore sinoid data。

 which is just going to be our data points， those data points with the random noise on top of the actual model that we're working with。



![](img/b2ac712cb25f0490f3a7935794d0e97c_12.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_13.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_14.png)

We're also going to ourselves generate the actual model。

 the ground truth model that it is we are trying to approximate。

 The way that we're going to do that is use0100 equally spaced x data points over the range of 0 to 1。

 And then for each one of those x data points show what the relating y should be。

 and that y will be defined by the function of s。

![](img/b2ac712cb25f0490f3a7935794d0e97c_16.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_17.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_18.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_19.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_20.png)

And then within the sign of two pi times each one of those x values。



![](img/b2ac712cb25f0490f3a7935794d0e97c_22.png)

And then we're going to plot both the data points。

![](img/b2ac712cb25f0490f3a7935794d0e97c_24.png)

With the extra noise， as well as the true underlying function。 And from there。

 we'll be able to start using regularization， as well as polynomial functions to see how well we can fit to this data。



![](img/b2ac712cb25f0490f3a7935794d0e97c_26.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_27.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_28.png)

So we're setting our file path the same way as we have in past Nobooks， using OS。

C to say how to separate between the folder and the path to the file。

 and we're going to join our data path， which is data to X underscore Y underscore sininooid data。

 just pulling out that CSV file。

![](img/b2ac712cb25f0490f3a7935794d0e97c_30.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_31.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_32.png)

So that's just going to be equal to a string。 We pass in that string into our read CSV function。

 and we set that equal to data。 So now we have our data。



![](img/b2ac712cb25f0490f3a7935794d0e97c_34.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_35.png)

And then we want to also create our real x values， as well as the relating real Y values。

 So we start off with x real is equal to this NP dot L space。

 And what that's going to do is you put in your first value。



![](img/b2ac712cb25f0490f3a7935794d0e97c_37.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_38.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_39.png)

You put in your second value。

![](img/b2ac712cb25f0490f3a7935794d0e97c_41.png)

And then you put in how many values you want in between that initial and end value。

 So here we'll have 100 values between 0 and 1。

![](img/b2ac712cb25f0490f3a7935794d0e97c_43.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_44.png)

Then y realel is just going to be a function of each one of those x values。



![](img/b2ac712cb25f0490f3a7935794d0e97c_46.png)

Which， again， we said is going to be the s。 And here we're using NP dot sign， the nuy sign。



![](img/b2ac712cb25f0490f3a7935794d0e97c_48.png)

Of two times pi。

![](img/b2ac712cb25f0490f3a7935794d0e97c_50.png)

Times each one of these different points， x real， and because it's a nuly array。

 it'll do it across each one of those individual data points。



![](img/b2ac712cb25f0490f3a7935794d0e97c_52.png)

So first let's look quickly at what we produce from data。head。

 that's going to be our random data points。

![](img/b2ac712cb25f0490f3a7935794d0e97c_54.png)

That's going to be the actual function。

![](img/b2ac712cb25f0490f3a7935794d0e97c_56.png)

Plus， a little bit of noise。 And we'll see that graph in just a second。 and then as discussed X real。



![](img/b2ac712cb25f0490f3a7935794d0e97c_58.png)

Will just be an array between zero and1。

![](img/b2ac712cb25f0490f3a7935794d0e97c_60.png)

With 100 different values。 and why real will be the relating。



![](img/b2ac712cb25f0490f3a7935794d0e97c_62.png)

hy。😡，Using the function sine of two times pi times that x real。



![](img/b2ac712cb25f0490f3a7935794d0e97c_64.png)

Also，100 values。

![](img/b2ac712cb25f0490f3a7935794d0e97c_66.png)

So first we set all the styles， contacts and palette that we want for Seaborn。



![](img/b2ac712cb25f0490f3a7935794d0e97c_68.png)

We're then going to create our a object that bounding box by using pandas built in plotting functionality。

 so we're calling data， which is our pandas data frame， we're calling dot plot。



![](img/b2ac712cb25f0490f3a7935794d0e97c_70.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_71.png)

And then we just say if we would go back to data。head， you recall that we had two columns。



![](img/b2ac712cb25f0490f3a7935794d0e97c_73.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_74.png)

One of them was x， one of them was y， so we're just setting the x within our plot to the actual column X and our y values within that plot to the actual column y。



![](img/b2ac712cb25f0490f3a7935794d0e97c_76.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_77.png)

We don't want to connect to each one of those dots， so the line style will be blank。



![](img/b2ac712cb25f0490f3a7935794d0e97c_79.png)

We'll set the marker equal to O， so we'll have a circle for each one。

 and we're just going to have it labeled data so that when we see the legend。

 we'll see that this is the actual data that we're trying to fit to。



![](img/b2ac712cb25f0490f3a7935794d0e97c_81.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_82.png)

And then to look at the actual real function。

![](img/b2ac712cb25f0490f3a7935794d0e97c_84.png)

We're going to call x dot plot。 So we're still on that same x。 We're still on that same bounding box。

 And we're going to plot x realel and y real。 Again， that being the values between 0 and 1。

 and they're relating， according to the actual function wise。



![](img/b2ac712cb25f0490f3a7935794d0e97c_86.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_87.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_88.png)

We're going to set the line sail to a dashed line。 No marker for each point。

 And then we'll label that real function。

![](img/b2ac712cb25f0490f3a7935794d0e97c_90.png)

We'll call accent legend so we can see which one is which。

 and then we will set our X label to x data and our Y label to Y data。



![](img/b2ac712cb25f0490f3a7935794d0e97c_92.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_93.png)

So here we see， as we discussed something very similar to what we saw in the course。

 where we have the actual underlying curve， which has this dotted red line。

 And that's the real function。 And then the blue dots。

 the true underlying function should be that red line。 There's just random noise added on to it。

 which is why it's not exactly on that line。 So we want to make sure we find a model that fits closely to that red line。

 And。

![](img/b2ac712cb25f0490f3a7935794d0e97c_95.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_96.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_97.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_98.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_99.png)

Does not fit exactly to the extra random error that's built into there， But at the same time。

 doesn't ignore the underlying model altogether。 again。

 trying to find that balance between bias and variance。



![](img/b2ac712cb25f0490f3a7935794d0e97c_101.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_102.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_103.png)

So part two， we want to use the polynomial features。

 which we've learned from SKLarn in order to create a 20th order polynomial。



![](img/b2ac712cb25f0490f3a7935794d0e97c_105.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_106.png)

We're then going to fit this data using linear regression and then plot the resulting predicted value。



![](img/b2ac712cb25f0490f3a7935794d0e97c_108.png)

And then we want to compare the calculated data。

![](img/b2ac712cb25f0490f3a7935794d0e97c_110.png)

We want to note that polynomial features requires either data frame with one column。



![](img/b2ac712cb25f0490f3a7935794d0e97c_112.png)

Or a2 D array of dimension X comma 1。 So we want to ensure。

 and I'm going to highlight here where this comes into play。

 We'll discuss it again when we get to it。 We want to ensure that we have a two dimensional array。

 We saw this before。 We can't just pass in a one dimension， just one column or a series。

 We have to make it in the form of。

![](img/b2ac712cb25f0490f3a7935794d0e97c_114.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_115.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_116.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_117.png)

Perhaps a data frame， as we see here or a two dimensional array。

So we import polynomial features our linear regression。

We're just setting degree equal to 20 and then we pass that in as a hyperparmeter for our polynomial features。

 which is going to allow us to fit and transform our X datata。



![](img/b2ac712cb25f0490f3a7935794d0e97c_119.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_120.png)

We're then going to use linear regression on that expanded version of X。



![](img/b2ac712cb25f0490f3a7935794d0e97c_122.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_123.png)

Our X data will be data and here we're putting in the two brackets and again that's because as we pass into our polynomial features。



![](img/b2ac712cb25f0490f3a7935794d0e97c_125.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_126.png)

We can't pass in just a single column， we have to pass in a data frame and when we pick double brackets。

 it's as if we're saying we want a data frame version of that column。



![](img/b2ac712cb25f0490f3a7935794d0e97c_128.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_129.png)

So if we did a single bracket， we would actually error out here。

We're setting y data just to equal to data y， and again these are the different points on our graph。

 it's not going to be the true underlying model that we're fitting our linear regression to。



![](img/b2ac712cb25f0490f3a7935794d0e97c_131.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_132.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_133.png)

We're then going to use our polynomial features to fit and transform our X data。

 so it's taking our original X data and expanding it out to a 20 degree polynomial。



![](img/b2ac712cb25f0490f3a7935794d0e97c_135.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_136.png)

We set that output equal to x poly。We're then going to use our linear Russian objects。

In order call LR dot fit on our X poly， our expanded version of X。



![](img/b2ac712cb25f0490f3a7935794d0e97c_138.png)

And our original Y data。And then we can actually come up with predictions once we come up with this fit。



![](img/b2ac712cb25f0490f3a7935794d0e97c_140.png)

On the actual data。 So we're not going to have a training and test set。

 this is just to articulate how will actually fit to the data set so we can see how overfitting will actually look。

 So I'm hinting ahead a little bit here。 degree 20 polynomial with no regularization will have too much variance will be too complex and will overfit to the data。



![](img/b2ac712cb25f0490f3a7935794d0e97c_142.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_143.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_144.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_145.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_146.png)

So we call LR dot predictd on our X polyly on the same values that we trained on。



![](img/b2ac712cb25f0490f3a7935794d0e97c_148.png)

And then we plot out both our new predictions。Given our new model that， again。

 hinted to should be too complex。

![](img/b2ac712cb25f0490f3a7935794d0e97c_150.png)

As well as looking at the true underlying function， as well as each one of the data points。



![](img/b2ac712cb25f0490f3a7935794d0e97c_152.png)

So first， we are going to。

![](img/b2ac712cb25f0490f3a7935794d0e97c_154.png)

Ploots are X data and y data in their original form without any X poly， right。

 so we just should get the same blue dots that we saw here above。



![](img/b2ac712cb25f0490f3a7935794d0e97c_156.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_157.png)

We set the marker to O line style to blank and label this just to data。



![](img/b2ac712cb25f0490f3a7935794d0e97c_159.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_160.png)

We're then going to plot X， real and Y real in the same fashion that we did above with the line style being that dashed line and the label being real function。

 So we can see the true underlyingline function。

![](img/b2ac712cb25f0490f3a7935794d0e97c_162.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_163.png)

And then we're going to plot our X data again， but this time we're going to look at the actual predictions that are made。



![](img/b2ac712cb25f0490f3a7935794d0e97c_165.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_166.png)

And with that， we're going to put a triangle to see each one of our different predictions。

 setting alpha to 0。5 so that we can still see it so it's a bit transparent and we'll label it predictions with polynomial features。



![](img/b2ac712cb25f0490f3a7935794d0e97c_168.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_169.png)

We can then call PLT dot legends， and we're going to set the x label and y label to y data。

 x theta and y data。

![](img/b2ac712cb25f0490f3a7935794d0e97c_171.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_172.png)

And here we see our graph。

![](img/b2ac712cb25f0490f3a7935794d0e97c_174.png)

And。As I mentioned before， that 20 degree polynomial fit here perfectly to the data set。



![](img/b2ac712cb25f0490f3a7935794d0e97c_176.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_177.png)

So if we want to generalize to a value that would probably fall somewhere on that red dot。

 we would probably miss out given the function that we used in order to come up with the fit that we have on our actual training set。



![](img/b2ac712cb25f0490f3a7935794d0e97c_179.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_180.png)

So this is an example of overfitting our polynomial degree is probably too high。

 so next we're going to want to bring in some regularization。



![](img/b2ac712cb25f0490f3a7935794d0e97c_182.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_183.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_184.png)

So part 3， we're going to perform this regression on using the data with polynomial features。

 but this time using Rige with an alpha equal to 0。001。



![](img/b2ac712cb25f0490f3a7935794d0e97c_186.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_187.png)

And then we will also use a lessso with alpha equal to 0。0001。

 and then we will plot the results as we've done in question1。

 and we'll also plot the magnitude of each one of these coefficients。



![](img/b2ac712cb25f0490f3a7935794d0e97c_189.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_190.png)

Obtained from the regression。 I want you to start thinking about which coefficients will be larger。

 Those that are without regularization or those with regularization， and compare them to those again。

 obtained from linear regression without any regularization。



![](img/b2ac712cb25f0490f3a7935794d0e97c_192.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_193.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_194.png)

And the linear regression coefficients will likely need a separate plot or their own y axis due to their large magnitude。



![](img/b2ac712cb25f0490f3a7935794d0e97c_196.png)

So we're going to see here。

![](img/b2ac712cb25f0490f3a7935794d0e97c_198.png)

Once we get down to plotting both of those， that we'll have to start learning how to use two axes。

 two y axes as we plot out those coefficients。So we start here。



![](img/b2ac712cb25f0490f3a7935794d0e97c_200.png)

With from SK Learnear。t linearar model， we import our ridge and our Laso regressions。



![](img/b2ac712cb25f0490f3a7935794d0e97c_202.png)

We're going to set RR equal to our rid object。With an alpha equal to 0。001。



![](img/b2ac712cb25f0490f3a7935794d0e97c_204.png)

We're then going to fit that to our X poly that we defined before。

 so that's that 20 degree polynomial as well as our Y data。



![](img/b2ac712cb25f0490f3a7935794d0e97c_206.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_207.png)

And then we can quickly come up with the predictions once that's fit on the actual training set。



![](img/b2ac712cb25f0490f3a7935794d0e97c_209.png)

We can then do the same thing for Laso， setting our alpha hyperparmeter equal to 0。0001。



![](img/b2ac712cb25f0490f3a7935794d0e97c_211.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_212.png)

We fit it to our ex polyly again， that 20 degree polynomial。

 and we can predict on that 20 degree polynomial。

![](img/b2ac712cb25f0490f3a7935794d0e97c_214.png)

The first few lines of this code are going to be the same， where we have the。



![](img/b2ac712cb25f0490f3a7935794d0e97c_216.png)

Actual X data and Y data， which are those blue data points。



![](img/b2ac712cb25f0490f3a7935794d0e97c_218.png)

The next line is going to be the actual real underlying function。



![](img/b2ac712cb25f0490f3a7935794d0e97c_220.png)

The third line is going to be what we saw before， which is just X data and y pre using linear regression without any regularization where we saw it fit perfectly to each data point。



![](img/b2ac712cb25f0490f3a7935794d0e97c_222.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_223.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_224.png)

We're then going to pit plot x datata versus。

![](img/b2ac712cb25f0490f3a7935794d0e97c_226.png)

A ridge regression， and then X datata versus our Laso regression。

 Each of them were labeling according to what they are。 label is ridge。Label is Laso。



![](img/b2ac712cb25f0490f3a7935794d0e97c_228.png)

And then we're setting alpha equal to 0。5， so we have a little bit of transparency for each one of these points。

 and we're setting our x label and y labeled to x data and y data。



![](img/b2ac712cb25f0490f3a7935794d0e97c_230.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_231.png)

So we run this。And we immediately see so that green line was our initial linear regression function。

 Our ridge regression and our lasso regression are getting much closer to that true underlying function。

😊。

![](img/b2ac712cb25f0490f3a7935794d0e97c_233.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_234.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_235.png)

So we have done a good job of regularizing， bringing down the complexity of the model。

 so we upped the bias， reduced the variance， and found that nice trade off between bias and variance。



![](img/b2ac712cb25f0490f3a7935794d0e97c_237.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_238.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_239.png)

Now， let's look at the absolute value of each one of our coefficients for each one of these different models。



![](img/b2ac712cb25f0490f3a7935794d0e97c_241.png)

The coefficients were first going to create a blank data frame。



![](img/b2ac712cb25f0490f3a7935794d0e97c_243.png)

Then all we have to do is call coefficients linear regression， and we're calling L R dot co F。

 Here we have dot ravel just in case our coefficients are already because we're only working in one dimension。

 It's already going to be just one dimension。 Ravel will ensure that it's one dimension。



![](img/b2ac712cb25f0490f3a7935794d0e97c_245.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_246.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_247.png)

So it wouldn't make any difference to remove each one of these， so I'll just show you here。

 but worth understanding that ral is function that you can use。



![](img/b2ac712cb25f0490f3a7935794d0e97c_249.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_250.png)

Taking， let's say， you know， a three dimensional data frame and raveling it if it's 20 by3。

 it'll make it into one array that's just 60 units long rather than。



![](img/b2ac712cb25f0490f3a7935794d0e97c_252.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_253.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_254.png)

20 by three。So we're setting the linear regression that's going to be our first column is equal to Lr。

cof， so our original linear regression model， then our Rige regression。

 and then our last hour regression， each of them are going to get their own column in our coefficient data frame。



![](img/b2ac712cb25f0490f3a7935794d0e97c_256.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_257.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_258.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_259.png)

We're then going to take the absolute value of each one of those using the apply map。

 which will apply it to every single value in our data frame。



![](img/b2ac712cb25f0490f3a7935794d0e97c_261.png)

And then we're going to get a brief description of our data frame。



![](img/b2ac712cb25f0490f3a7935794d0e97c_263.png)

So what we should see here quickly is the huge difference in scale between non regularized versus regularized regression。



![](img/b2ac712cb25f0490f3a7935794d0e97c_265.png)

So， we have。Riddge regression is going from a min of zero to a max of 12。

Whereas linear regression goes from some large number to some large number， much larger number。

 right， There's seven more zeros at the end。So we see that we were able to scale down how big each one of these coefficients are。



![](img/b2ac712cb25f0490f3a7935794d0e97c_267.png)

I would also like to note that if you look at the coefficients。



![](img/b2ac712cb25f0490f3a7935794d0e97c_269.png)

That are。Greater than zero。Let's actually take the。Sun。



![](img/b2ac712cb25f0490f3a7935794d0e97c_271.png)

We see that as we discussed in lecture， the LAssso will actually zero out many more of the actual coefficients compared to Ridge and then obviously compared to linear。

 so we actually zeroed out only one for Ridge and we zeroed out six different coefficients using LaSso。



![](img/b2ac712cb25f0490f3a7935794d0e97c_273.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_274.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_275.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_276.png)

Finally， we just want to plot what each of these values of the coefficients actually are。

 starting with linear regression and then going back to Rige and Lassso regression。



![](img/b2ac712cb25f0490f3a7935794d0e97c_278.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_279.png)

So the way that we create。

![](img/b2ac712cb25f0490f3a7935794d0e97c_281.png)

Two different axes， when we're working with Mattpllib。



![](img/b2ac712cb25f0490f3a7935794d0e97c_283.png)

I we're going to first set x1 equal to PLT do axes， so we now have our first bounding box。

And then we're saying x2 equals x1 dot twin x。 So it's taking that x1 that we defined and saying I still want to plot on that same graph。

 we just are going to use a different y variable。 So that's that twin x。

 We're going to use the same x， but we can change our y variables。 So that's going to be our x 2。

 and then we can plot on x1 and x2 as if they were their own separate plots and they will plot one on top of the other with different y axes。



![](img/b2ac712cb25f0490f3a7935794d0e97c_285.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_286.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_287.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_288.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_289.png)

So on x1， we're going to plot our original linear regression， so Lr。cof。



![](img/b2ac712cb25f0490f3a7935794d0e97c_291.png)

And then we're just going to， where we pulled out these colors。

 this will just define certain colors from our color palette， and we're saying take that first color。



![](img/b2ac712cb25f0490f3a7935794d0e97c_293.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_294.png)

And that's going to be our linear regression。

![](img/b2ac712cb25f0490f3a7935794d0e97c_296.png)

Take the second color。

![](img/b2ac712cb25f0490f3a7935794d0e97c_298.png)

And now we're plotting on x2， right， that's the twin x， but we're allowed a different y axis。



![](img/b2ac712cb25f0490f3a7935794d0e97c_300.png)

And that's going to be colors one， and that's going to be our Rige regression and all of its coefficients。



![](img/b2ac712cb25f0490f3a7935794d0e97c_302.png)

And then finally， we get the Lasso and all of its coefficients。

 and that's also going to be plotted on x2 because x2 for which has Rige and Lassso。

 both ridge and Lasso should have similar coefficients compared to what we saw the coefficients for linear regression where they can be really blown up。



![](img/b2ac712cb25f0490f3a7935794d0e97c_304.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_305.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_306.png)

So here we're actually setting the Y limits， we see for x1， which is linear regression。

 we have to set these huge boundaries， whereas for x2。

 we're just going to set it between negative 25 and 25。



![](img/b2ac712cb25f0490f3a7935794d0e97c_308.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_309.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_310.png)

We then want to get all of our labels in one place。

 This get legend handles labels will output both the handles and the labels from each one of our axes。

 So from X1， we're getting H1 is just going to tell us that we're pulling from X 1。

 That's the bounding box。 H2 is saying that the handles coming from the second box。😊。



![](img/b2ac712cb25f0490f3a7935794d0e97c_312.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_313.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_314.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_315.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_316.png)

And then when we call legend， we can pass in both the bounding box。



![](img/b2ac712cb25f0490f3a7935794d0e97c_318.png)

Both the。Handles as well as the labels。 And that's going to tell us how we want to actually input our legends。

 input our labels。

![](img/b2ac712cb25f0490f3a7935794d0e97c_320.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_321.png)

I'll show you how that works just briefly in a second and then we'll close out the video。



![](img/b2ac712cb25f0490f3a7935794d0e97c_323.png)

We're then going to set our X label and Y label， and for x2， we're going to set a different y label。

 letting it know that it's ridge and bO regression。



![](img/b2ac712cb25f0490f3a7935794d0e97c_325.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_326.png)

So we run this and as expected， we see huge fluctuating values for linear regression。

 whereas the Lasso and Rige tend to really zero out or get close to zero for a lot of our coefficients。



![](img/b2ac712cb25f0490f3a7935794d0e97c_328.png)

This is going to be the magnitude of each one of our coefficients。

 and they're going to be on completely different scales。

 If you look here at the top left corner of the graph。

 you'll see that this isn't values between 0 and2， but between0 and2 times e to the 14。



![](img/b2ac712cb25f0490f3a7935794d0e97c_330.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_331.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_332.png)

So we have these astronomical， you know， two plus 14 zeros here。

 whereas rid and laer regression are just between negative 25 and 25。



![](img/b2ac712cb25f0490f3a7935794d0e97c_334.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_335.png)

Now just to show you what would have happened if I would have。

Removed one of these just to get an idea of bringing in these handles。



![](img/b2ac712cb25f0490f3a7935794d0e97c_337.png)

Then we just get the H1 if I pulled the L2 labels， H1 only allowed for one label。



![](img/b2ac712cb25f0490f3a7935794d0e97c_339.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_340.png)

But if I said I wanted that label equal to the L2， which had two labels。

 it would just pull out that first label， which was Rige regression。



![](img/b2ac712cb25f0490f3a7935794d0e97c_342.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_343.png)

So we need both H1 plus H2 and L1 plus L2， and this is the way that you have multiple y axes and it could be powerful as you create youngon grass later on。



![](img/b2ac712cb25f0490f3a7935794d0e97c_345.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_346.png)

That concludes the first half of this notebook， when we come back we will look at a true data set in order to see how we can use regular to improve our performance on holdout sets。

 thank you。

![](img/b2ac712cb25f0490f3a7935794d0e97c_348.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_349.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_350.png)

![](img/b2ac712cb25f0490f3a7935794d0e97c_351.png)