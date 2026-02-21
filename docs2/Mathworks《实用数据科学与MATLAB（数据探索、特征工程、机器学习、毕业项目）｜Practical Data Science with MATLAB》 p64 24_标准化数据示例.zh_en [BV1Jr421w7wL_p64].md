# Mathworks《实用数据科学与MATLAB（数据探索、特征工程、机器学习、毕业项目）｜Practical Data Science with MATLAB》 p64 24_标准化数据示例.zh_en [BV1Jr421w7wL_p64]

🎼，You've just seen why it can be important to normalize your data in order to compare variables with different units and ranges。

Now you'll learn how to perform different types of normalization in MElo。



![](img/47a874e5802de7faa493cacf87758730_1.png)

Let's load the September data from the Flights data and only consider a subset of flights from San Francisco to LAX。



![](img/47a874e5802de7faa493cacf87758730_3.png)

Start by making a histogram of the airtime column。 the data appears to be normally distributed。

 although there are a few outliers。

![](img/47a874e5802de7faa493cacf87758730_5.png)

You can remove these values with RM outliers。

![](img/47a874e5802de7faa493cacf87758730_7.png)

Much better。Notice that the number of bins is specified here。

 which will make it easier to compare with normalized histograms。To normalize the data in airtime。

 use the normalized function。This function takes a column from a table as input and returns a normalized version。

Let's check the histogram again。It looks exactly the same， but notice the units along the X axis。

Instead of a range from 50 to 70， the values range from around negative3 to 3。

The values here have been transformed into a Z score。

 which is the default method for the normalized function。

This type of normalization is useful because you can think of the values having units of standard deviations。



![](img/47a874e5802de7faa493cacf87758730_9.png)

For example， consider our normalized airtime values。

A value like positive one means the original value was one standard deviation above the mean。

Whereas value like negative 2 means the original value was two standard deviations below the mean。



![](img/47a874e5802de7faa493cacf87758730_11.png)

Now you can use normalization to compare variables with different ranges。

Repeat this normalization for the departure delay variable and create a scatter plot of airtime versus departure delay。



![](img/47a874e5802de7faa493cacf87758730_13.png)

![](img/47a874e5802de7faa493cacf87758730_14.png)

The values in departure delay aren't normally distributed。

 so the range here on the Y axis is different。Nevertheless。

 the values in both variables have a mean of0 and a standard deviation of 1。This raises the question。

 how do you normalize values that aren't normally distributed？



![](img/47a874e5802de7faa493cacf87758730_16.png)

The normalized function provides several methods for doing this。

 and you can include an additional argument to specify the method you want to use。



![](img/47a874e5802de7faa493cacf87758730_18.png)

![](img/47a874e5802de7faa493cacf87758730_19.png)

Let's start with a uniform distribution that has a well defined range。

Create a departure hour variable with the hour function and the scheduled departure time variable。



![](img/47a874e5802de7faa493cacf87758730_21.png)

These values range from 6 to 22， meaning that for flights from San Francisco to LAX。

 flights are scheduled to depart between 6 am and 10 pm。

You can normalize these values between the minimum and maximum by specifying the range method。



![](img/47a874e5802de7faa493cacf87758730_23.png)

Let's check the histogram again。Instead of ranging from 6 to 22。

 all the values are now between 0 and 1。This type of normalization can be a good choice for variables like departure hour that are uniformly distributed。



![](img/47a874e5802de7faa493cacf87758730_25.png)

Now let's return to a variable lake departure delay that isn't uniformly or normally distributed。

Instead of a standard Z score， one option is to calculate a robust version by adding the robust flag after Z score。

This flag will use the median absolute deviation instead of the standard deviation to scale the range of the data。

You might recall that the median absolute deviation is one of the outlier detection methods in MALAab。

That's because this statistic is less susceptible to distortions due to outliers than the standard deviation。

 so it's a good choice for non normal distributions like this one。After normalizing。

 you may notice that the range of values become smaller。

 but it's still much larger than you saw earlier with the standard Z score。



![](img/47a874e5802de7faa493cacf87758730_27.png)

That's because the large positive outliers had less effect on the scaling。

 so the values remained large even after normalizing。



![](img/47a874e5802de7faa493cacf87758730_29.png)

![](img/47a874e5802de7faa493cacf87758730_30.png)

To decrease the range to something comparable to before。

 you can remove the outliers first and then normalize。

Don't forget you can choose a threshold factor for specifying which values should be considered outliers。



![](img/47a874e5802de7faa493cacf87758730_32.png)

Let's check the histogram again。

![](img/47a874e5802de7faa493cacf87758730_34.png)

This looks better， meaning the normalized values have a reasonable range。

Now this variable can be more easily compared with others， such as the airtime values from earlier。



![](img/47a874e5802de7faa493cacf87758730_36.png)

Check the documentation page for the normalizedize function for other ways of normalizing your data。

 You may have to use different methods for different variables depending on how they're distributed。



![](img/47a874e5802de7faa493cacf87758730_38.png)

To recap， use the normalized function to create normalized versions of your table variables。

Don't forget that removing outliers beforehand can produce better results。



![](img/47a874e5802de7faa493cacf87758730_40.png)

And finally， use a normalization method that is appropriate for the distribution of the data。

 You may have to use different methods for different variables。



![](img/47a874e5802de7faa493cacf87758730_42.png)

Now it's your turn to try normalizing data in a graded problem。



![](img/47a874e5802de7faa493cacf87758730_44.png)

。