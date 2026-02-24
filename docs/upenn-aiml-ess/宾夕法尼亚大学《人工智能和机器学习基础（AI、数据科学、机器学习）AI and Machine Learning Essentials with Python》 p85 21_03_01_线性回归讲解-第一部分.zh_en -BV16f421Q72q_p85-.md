# 宾夕法尼亚大学《人工智能和机器学习基础（AI、数据科学、机器学习）AI and Machine Learning Essentials with Python》 p85 21_03_01_线性回归讲解-第一部分.zh_en -BV16f421Q72q_p85-

![](img/6c0f877a8d14bf6edd1c73326237d57a_0.png)

Welcome to this recitation on Linear regression。So in this recitation。

We're going to work with the following two data sets。The college data and the Boston data。

We're going to do linear regression and we're going to have to install several packages。

 so were starting here in this cell by importing all the required libraries Okay so we have clabities for datargling plotting linear models and modeling and define some colors。



![](img/6c0f877a8d14bf6edd1c73326237d57a_2.png)

![](img/6c0f877a8d14bf6edd1c73326237d57a_3.png)

![](img/6c0f877a8d14bf6edd1c73326237d57a_4.png)

Now in this cell on the top， we're going to import the data set as a panda data frame。so for that。

 we're going to use the method， read and CSv to import the college do CSsv file。

And we're going to rename the columns of this data frame to handle them easier。Okay。

 so using data ahead， we can have a sneak preview of this data frame。 Okay。

 and we have here some of the variables。

![](img/6c0f877a8d14bf6edd1c73326237d57a_6.png)

So we have in the data set and in here we have this could be the first input。

 remember that in Python the first index is0， not one okay so for the first input with the index0 these are the features for that particular university in the college data set for the second university this could be the features and so on and so forth。



![](img/6c0f877a8d14bf6edd1c73326237d57a_8.png)

Now。In this cell here at the top。We're going to make a copy of that particular data because we're going to add an extra column。

That extra column is the accept rate。Which is the ratio between the variable except and the variable apps。

 which is the number of applicants。

![](img/6c0f877a8d14bf6edd1c73326237d57a_10.png)

Now， we're going to look at different models to make ordinary squares。

 So we're going to start with the stats model。Way of performing ordinary list squares。

And is by calling SMMF dot small case O。So。で？Arguments of this function， or this method is。

As a string， you put the y variable， gra rate， then tilde， the input variable x， which is top 25%。

 you fit the data and you call the method fit。Okay， so then you' going na。Otain。A model fits0。

 and using print。 we can check out the summary。

![](img/6c0f877a8d14bf6edd1c73326237d57a_12.png)

Of the linear regression results。Okay， so in here you have some statistics of importance。

More importantly for us is the error square value，0 0。20 to 8。



![](img/6c0f877a8d14bf6edd1c73326237d57a_14.png)

And then in here， the lower part of the table is where the most relevant information is。

 So here we have。The value of the estimated intercept， which is 42。 So this is what we call。Better。

 not hat。And then a a value of beta1 hat。 the estimate of the slope is 0。41。In here。

 we have the standard errors for beta 0 and beta 1。The the values。

 which are thus the ratios of the coefficient of the standard errors。

The P values and the 95% confidence intervals。 right So in particular。

 the 95% confidence interval for the。A slope is 0。36 to 0。46。



![](img/6c0f877a8d14bf6edd1c73326237d57a_16.png)

So there is another way to perform a linear fitting， which is with the SMm。



![](img/6c0f877a8d14bf6edd1c73326237d57a_18.png)

Dot capital O S， So what we do in this cell is first， we define the input variable， which is top 25%。

 Now， something important。When you use a capital Os is to add a constant to take into account the intercept。

 So you essentially need to add a second column in the x variable。

Then the y is going to be the graduation rate。 and on here we call the method capital Os to perform the fit。

 Okay so we call this fit1。 We check out the object fit one using print and we obtain exactly the same table as before。



![](img/6c0f877a8d14bf6edd1c73326237d57a_20.png)

Now， there is a third way to。Do a linear regression with psych kit。In here。

 we're going to use the double bracket to define the input variable。

And we define the output variable， as we did before。

We build a mobile which is going to be a linear regression where the intercept is included。

And use model dot fit to find a fit for that mode。So now we can use deer。

To make a list of all the attributes。Of the object fit too。 So this is a list of the attributes。

And in particular， in coef and intercept， we get the values of the coefficientient， the beta1 hat。

 and the intercept beta0 hat。

![](img/6c0f877a8d14bf6edd1c73326237d57a_22.png)

![](img/6c0f877a8d14bf6edd1c73326237d57a_23.png)

Now， looking at these results， we can see that the values of the estimates are。



![](img/6c0f877a8d14bf6edd1c73326237d57a_25.png)

Beta 0 hat and beta1 hat as I mentioned before， so what this coefficient means is that for every unit mean a 1% increase in the top 25% variable。

 there is a 0。41% increase in the output variable graduation rate。



![](img/6c0f877a8d14bf6edd1c73326237d57a_27.png)

Let's move on to include some plots。 So in here we're going to plot。



![](img/6c0f877a8d14bf6edd1c73326237d57a_29.png)

The data set in red where we have the input variable here and the output variable graduation rate。

This is what this lining here performs essentially in this scatter plot we're going to use the outputs of the shape O in color red。

 we also include the straight fitted line， essentially in this blue line we use as inputs the predictions of our models for values in this range in here。

 and we finally include the labels so we got the original data set in red and the fitted straight line in blue。



![](img/6c0f877a8d14bf6edd1c73326237d57a_31.png)

Also， you can look at the quality of your fit using a Qq plot。

 So these are the theoretical quantiles here and the sub sample quantiles。

 So it's a straight line that means that this is a good quality fit we can also fit the residuals substantially for each fit value we can compare the value of the residuals with。



![](img/6c0f877a8d14bf6edd1c73326237d57a_33.png)

![](img/6c0f877a8d14bf6edd1c73326237d57a_34.png)

With the value of 0， which is here in this red line。



![](img/6c0f877a8d14bf6edd1c73326237d57a_36.png)

And based on these quantities， we can cover some important statistics。 So， for example。

 we have the RSs， which is the residual sum of the squares。

Which is the sum over all the samples of the true value of the output minus our estimate value of the output square。

 So this is essentially。The value of the residual inside the parenthses。

 and we do the square and sum all these values。We can also compute the residual standard error， R C。

As the square root of the RSs divided by the number of degrees of freedom。

 which is defined as n minus p -1。In this case， we have a single input， so the value of p is 1。

 and the denominator will be n minus-2。We also have T S S， which is the total sum of the squares。

 In this particular case， we do the sum of the squares of the error between。

The true value of the output and the average value of the outputs。

so notice that the RSS and the TSS have a similar form。

 and here we compare the output y with a simple estimate if you may want to call it that way。

 which is just the average output。Now， the added square。



![](img/6c0f877a8d14bf6edd1c73326237d57a_38.png)

Is going to be the ratio between the difference of TSs and RSs divided by TSS。

So notice that the TSS is always going to be greater or equal than the RSs。

 and this is a way to normalize that value。

![](img/6c0f877a8d14bf6edd1c73326237d57a_40.png)

In this cell in here， we program these formulas from scratch so we do the sum of the residualitals squares。

 we compute the RSC as the RSs divided by the Df of the degrees of freedom of the residuals。

And in here we compute the TSS。And the aisqua。Okay， now。

We don't need to program these values from scratch。

 there is actually a methods in Python to compute the error square。



![](img/6c0f877a8d14bf6edd1c73326237d57a_42.png)

Call in this method in here。And also， we can directly access the RSC using this formula here。

As we have seen in class， the Ody is important because it provides an estimate of sigma。

Which is the standard deviation of the measurement error。RightNow using this value of sigma。

 we can compute confidence interval。So remember when you make a prediction。

 you not only care about the value of the prediction。

 but also how confident you are about your prediction。And to make that。

 you need to provide confidence intervals around the values that you predict。Now。

 remember that the confidence interval for a random variable is going to be mu。

 which is the mean of that random variable plus minus not set。

 so this value of set is going to depend on your confidence。Times standard error So for example。

 in the case of 95% confidence intervals this value offset set will be 1。96。

 typicallyy we round this at2 for it just easier to memorize right so for example if we want to compute the 95% confidence interval for the variable beta one we put here be one hats。

Which is an ambitiousbiased estimate of beta 1， meaning the mean of beta 1 is equal to 0。41。And。

We do plus minus2 times roughly the standard error。

 which is an estimate of the standard deviation right so from this formula here we get the values 0。

36 and 0。46 so the interpretation of this interval is that with 95% probability the true value of beta 1 that nature is using to generate the data is contained in this intervalin here。

We can now move on to hypothesis testing and P values。 Now in hypothesis testing。

 we want to ask the question if the input that were using is statistically significant。Now。

We formulate the problem as a null hypothesis and an alternative hypothesis。 So in the nu hypothesis。

 at not， we assume that there is no relationship between the input and the output。Mathematically。

 this is equivalent to say that the value of metata 1 is equal to 0。Now。

 the alternative hypothesis is the negation of this essentially that there is a relationship between the input and the output or equivalently。

 that better one is different than 0。We can make a statistical decision。

About what hypothesis we should accept or reject based on the P values that we obtain in the linear fit。

So when the P value is small， we reject the nu hypothesis。

Depending on the particular significant level， which typically we choose to be 0。

05 threshold for the P value。And in if the P values is small。

 we say that there is a relationship between the input and the output at that particular significant level。

 which typically is 95% so。The value that we use to threshold the P values is going to be 0。05。

 If the P value is greater than 0。05。We fail to reject the neural hypothesis at that significant level。

 which is 95 per cent。 And we claim that there is no association between the input and the output。

So in that case， we don't accept the nu hypothesis， in other words， we fail to reject it。Now。

 these are the P values that we obtain for beta 1。Right， orbit betterta1 had to be more precise。

 You can see that this is a very small value。Much is smaller than 0。05。

 so we do reject the nu hypothesis。And we claim that there is a relationship between the input and the output。

Now we move on to prediction intervals。So as I mentioned before， we。Want to make predictions about。

 for example， the graduation rate in this case， given the top 25% of a particular university。

And we can make predictions just by using the linear regression formula， right， so this could be。



![](img/6c0f877a8d14bf6edd1c73326237d57a_44.png)

Better not hat。 This would be beta1 hat， and this would be the input for which you want to make and prediction for the output。

 In this case， the graduation rate。

![](img/6c0f877a8d14bf6edd1c73326237d57a_46.png)

So if we use this formula， we get a 60% prediction for the graduation rate。



![](img/6c0f877a8d14bf6edd1c73326237d57a_48.png)

Now， apart from the prediction， we also want to make。



![](img/6c0f877a8d14bf6edd1c73326237d57a_50.png)

Confidence intervals， or we also want to build a confidence interval for our prediction。



![](img/6c0f877a8d14bf6edd1c73326237d57a_52.png)

Again， using the same logic as before， the 95% confidence in value is going to be the average value of the prediction output。

 which is the value that we are1 in here。

![](img/6c0f877a8d14bf6edd1c73326237d57a_54.png)

Plus， minus twice the R C。

![](img/6c0f877a8d14bf6edd1c73326237d57a_56.png)

You can use this cell to program these prediction intervals。

 essentially the mean plus minus twice the sigma， which is the RS that we can calculate in this line and the prediction interval for the output with a 95% confidence interval would be 36 and 97。

So this is the end of this lecture， and in the last lecture we'll re up from here。



![](img/6c0f877a8d14bf6edd1c73326237d57a_58.png)