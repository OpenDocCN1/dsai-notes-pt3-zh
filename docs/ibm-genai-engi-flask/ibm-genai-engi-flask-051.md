# 051：IBM《生成式人工智能工程｜Falsk、生成式AI应用、数据分析、机器学习、Keras、架构和数据、NLP基础、transformer、微调、高级微调、RAG》 p51 21_多项式回归和管道.zh_en -BV1NAq6Y9E7z_p51-

![](img/abe584ba67296b12e0ae5a20734e9277_0.png)

嗯。

![](img/abe584ba67296b12e0ae5a20734e9277_2.png)

In this video， we will cover polynomial regression and pipelines。

What do we do when a linear model is not the best fit for our data。

 Let's look into another type of regression model， the polynomial regression。

We transform our data into a polynomial， then use linear regression to fit the parameter。

 Then we will discuss pipelinelines。 Pipelines are way to simplify your code。



![](img/abe584ba67296b12e0ae5a20734e9277_4.png)

Polynomial regression is a special case of the general linear regression。

This method is beneficial for describing curvalinear relationships。

 What is a curvalinear relationship。It's what you get by squaring or setting higher order terms of the predictor variables in the model。

 transforming the data。

![](img/abe584ba67296b12e0ae5a20734e9277_6.png)

The model can be quadratic， which means that the predictor variable in the model is squared。

 We use a bracket to indicate it as an exponent。 This is a second order polynomial regression with a figure representing the function。

The model can be cubic， which means that the predictor variable is cubed。

 This is a third order polynomial regression。 We see by examining the figure that the function has more variation。

There also exists higher order polynomial regressions when a good fit hasn't been achieved by second or third order。

 we can see and figures how much the graphs change when we change the order of the polynomial regression。

The degree of the regression makes a big difference and can result in a better fit if you pick the right value。

In all cases， the relationship between the variable and the parameter is always linear。



![](img/abe584ba67296b12e0ae5a20734e9277_8.png)

Let's look at an example from our data， where we generate a polynomial regression model。In Python。

 we do this by using the polyfi function。In this example。

 we develop a third order polynomial regression model base。 We can print out the model。

Symbolic form for the model is given by the following expression。 Neative 1。557 x 1 cubed plus 204。

8 x 1 squared plus 8965 x1 plus 1。37 times 10 to the power of 5。



![](img/abe584ba67296b12e0ae5a20734e9277_10.png)

We could also have multidimensional polynomial linear regression。 The expression can get complicated。

 Here are just some of the terms for a two dimensional second order polynomial。

 nupy's polyfit function cannot perform this type of regression。



![](img/abe584ba67296b12e0ae5a20734e9277_12.png)

We use the pre processing library in S Ki Learn to create a polynomial feature object。

 The constructor takes the degree of the polynomial as a parameter。

 Then we transform the features into a polynomial feature with the fit underscore transform method。

Let's do a more intuitive example。 Consider the features shown here。

 Apply the method we transform the data。 We now have a new set of features that are a transformed version of our original features。

 as the dimension of the data gets larger。 We may want to normalize multiple features in Ps kit learn。

 Instead， we can use the pre processing module to simplify many tasks。 For example。

 we can standardize each feature simultaneously We import standard scalar。

 We train the object fit the scale object。

![](img/abe584ba67296b12e0ae5a20734e9277_14.png)

Then transform the data into a new data frame on array X underscore scale。

 There are more normalization methods available in the pre processing library。

 as well as other transformations。

![](img/abe584ba67296b12e0ae5a20734e9277_16.png)

We can simplify our code by using a pipeline library。There are many steps to getting a prediction。

 for example， polynomial transform， normalization， and linear regression。

We simplify the process using a pipeline。Pipelines sequentially perform a series of transformations。

 The last step carries out a prediction。

![](img/abe584ba67296b12e0ae5a20734e9277_18.png)

First， we import all the modules we need。

![](img/abe584ba67296b12e0ae5a20734e9277_20.png)

Then we import the library pipeline。We create a list of tuples。

 The first element in the tuple contains the name of the estimator model。

The second element contains model Conor。We input the list in the pipeline Conor。

We now have a pipeline object。

![](img/abe584ba67296b12e0ae5a20734e9277_22.png)

We can train the pipeline by applying the train method to the pipeline object。

 We can also produce a prediction as well。 The method normalizes the data。

 performs a polynomial transform， then outputs a prediction。



![](img/abe584ba67296b12e0ae5a20734e9277_24.png)