# IBM数据科学专业证书课程7：《使用Python进行数据分析》data-analysis-with-python（中英字幕） - P37：36_多项式回归与流水线.zh_en - GPT中英字幕课程资源 - BV1sP41147Bz

In this video， we will cover polynomial regression and pipelines。



![](img/529ca9ce3a2cec898117dff99c48e65d_1.png)

![](img/529ca9ce3a2cec898117dff99c48e65d_2.png)

What do we do when a linear model is not the best fit for our data。

 Let's look into another type of regression model， the polynomial regression。



![](img/529ca9ce3a2cec898117dff99c48e65d_4.png)

We transform our data into a polynomial， then use linear regression to fit the parameter。

 Then we will discuss pipelines。 Pipelines are a way to simplify your code。



![](img/529ca9ce3a2cec898117dff99c48e65d_6.png)

![](img/529ca9ce3a2cec898117dff99c48e65d_7.png)

![](img/529ca9ce3a2cec898117dff99c48e65d_8.png)

Polynomial regression is a special case of the general linear regression。

This method is beneficial for describing curvalinear relationships。



![](img/529ca9ce3a2cec898117dff99c48e65d_10.png)

What is a curvilinear relationship？

![](img/529ca9ce3a2cec898117dff99c48e65d_12.png)

It's what you get by squaring or setting higher order terms of the predictor variables in the model。

 transforming the data。The model can be quadratic， which means that the predictor variable in the model is squared。

 We use a bracket to indicate it as an exponent。 This is a second ordered polynomial regression with a figure representing the function。



![](img/529ca9ce3a2cec898117dff99c48e65d_14.png)

![](img/529ca9ce3a2cec898117dff99c48e65d_15.png)

![](img/529ca9ce3a2cec898117dff99c48e65d_16.png)

The model can be cubic， which means that the predictor variable is cubed。

 This is the third order polynomial regression。 We see by examining the figure that the function has more variation。



![](img/529ca9ce3a2cec898117dff99c48e65d_18.png)

![](img/529ca9ce3a2cec898117dff99c48e65d_19.png)

There also exists higher order polynomial regressions when a good fit hasn't been achieved by second or third order。

 we can see and figures how much the graphs change when we change the order of the polynomial regression。

The degree of the regression makes a big difference and can result in a better fit if you pick the right value。

In all cases， the relationship between the variable and the parameter is always linear。

Let's look at an example from our data， where we generate a polynomial regression model。



![](img/529ca9ce3a2cec898117dff99c48e65d_21.png)

In Python， we do this by using the polyfit function。



![](img/529ca9ce3a2cec898117dff99c48e65d_23.png)

In this example， we develop a third order polynomial regression model base。

 We can print out the model symbolic form for the model is given by the following expression。



![](img/529ca9ce3a2cec898117dff99c48e65d_25.png)

![](img/529ca9ce3a2cec898117dff99c48e65d_26.png)

Negative 1。557 x1 cubed plus 204。8 x1 squared plus 8965 x1 plus 1。37 times 10 to the power of 5。

 We can also have multidimensional polynomial linear regression。 The expression can get complicated。

 Here are just some of the terms for a two dimensional second order polynomial。

 nu Pi's polyfit function cannot perform this type of regression。

 We use the pre processing library in psi kit learn to create a polynomial feature object。

 The constructor takes the degree of the polynomial as a parameter。

 Then we transform the features into a polynomial feature with the fit underscore transform method。

 Let's do a more intuitive example。😊。

![](img/529ca9ce3a2cec898117dff99c48e65d_28.png)

![](img/529ca9ce3a2cec898117dff99c48e65d_29.png)

![](img/529ca9ce3a2cec898117dff99c48e65d_30.png)

![](img/529ca9ce3a2cec898117dff99c48e65d_31.png)

![](img/529ca9ce3a2cec898117dff99c48e65d_32.png)

![](img/529ca9ce3a2cec898117dff99c48e65d_33.png)

![](img/529ca9ce3a2cec898117dff99c48e65d_34.png)

![](img/529ca9ce3a2cec898117dff99c48e65d_35.png)

Consider the features shown here。 App the method we transform the data。

 We now have a new set of features that are a transformed version of our original features。

 As the dimension of the data gets larger， we may want to normalize multiple features in Psit learn。

 Instead， we can use the pre processing module to simplify many tasks。 For example。

 We can standardize each feature simultaneously。 We import standard scalar。 We train the object。



![](img/529ca9ce3a2cec898117dff99c48e65d_37.png)

![](img/529ca9ce3a2cec898117dff99c48e65d_38.png)

![](img/529ca9ce3a2cec898117dff99c48e65d_39.png)

![](img/529ca9ce3a2cec898117dff99c48e65d_40.png)

![](img/529ca9ce3a2cec898117dff99c48e65d_41.png)

![](img/529ca9ce3a2cec898117dff99c48e65d_42.png)

Fit the scale object。

![](img/529ca9ce3a2cec898117dff99c48e65d_44.png)

Then transform the data into a new data frame on array x underscore scale。



![](img/529ca9ce3a2cec898117dff99c48e65d_46.png)

There are more normalization methods available in the pre processing library。

 as well as other transformations。

![](img/529ca9ce3a2cec898117dff99c48e65d_48.png)

We can simplify our code by using a pipeline library。 There are many steps to getting a prediction。

 For example， normalization， polynomial transform and linear regression。 We simplify the process。

 using a pipeline。

![](img/529ca9ce3a2cec898117dff99c48e65d_50.png)

![](img/529ca9ce3a2cec898117dff99c48e65d_51.png)

![](img/529ca9ce3a2cec898117dff99c48e65d_52.png)

Pipelines sequentially perform a series of transformations。 The last step carries out a prediction。

 First， we import all the modules we need。 Then we import the library pipeline。



![](img/529ca9ce3a2cec898117dff99c48e65d_54.png)

![](img/529ca9ce3a2cec898117dff99c48e65d_55.png)

We create a list of tuples。 The first element in the tuple contains the name of the estimator model。



![](img/529ca9ce3a2cec898117dff99c48e65d_57.png)

![](img/529ca9ce3a2cec898117dff99c48e65d_58.png)

The second element contains model constructor。We input the list in the pipeline constructor。



![](img/529ca9ce3a2cec898117dff99c48e65d_60.png)

We now have a pipeline object。We can train the pipeline by applying the train method to the pipeline object。

 We can also produce a prediction， as well。

![](img/529ca9ce3a2cec898117dff99c48e65d_62.png)

![](img/529ca9ce3a2cec898117dff99c48e65d_63.png)

The method normalizes the data， performs a polynomial transform， then outputs of prediction。

