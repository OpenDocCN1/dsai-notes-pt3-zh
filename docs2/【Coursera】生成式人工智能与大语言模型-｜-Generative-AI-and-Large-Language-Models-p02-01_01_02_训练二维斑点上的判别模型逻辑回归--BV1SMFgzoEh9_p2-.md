# 【Coursera】生成式人工智能与大语言模型-｜-Generative-AI-and-Large-Language-Models-p02-01_01_02_训练二维斑点上的判别模型逻辑回归--BV1SMFgzoEh9_p2-

Welcome back。 Today we'll create a simple machine learning model that can separate two groups of data points。

 Think of it like teaching a computer to draw a line between two types of dots。



![](img/af8c39e3bd1d4ae804615df3eeef3050_1.png)

First， let's create some practice data。Our code creates 300 data points， splits them into two groups。

 purple and yellow。Gives each point two features like X and Y coordinates。



![](img/af8c39e3bd1d4ae804615df3eeef3050_3.png)

Look at our scatter plot。 See how the purple dots cluster separately from the yellow ones。



![](img/af8c39e3bd1d4ae804615df3eeef3050_5.png)

Now， we need to convert our data into a format Pytorrch understands。

 Think of it like translating our data into piytorrch's language。

 We also create batches of 32 points。 batch underscore size equals 32。



![](img/af8c39e3bd1d4ae804615df3eeef3050_7.png)

Shuffle the data for better learning。

![](img/af8c39e3bd1d4ae804615df3eeef3050_9.png)

Here is where the magic happens。We create a logistic regression model。



![](img/af8c39e3bd1d4ae804615df3eeef3050_11.png)

Our training process uses BCE loss to measure mistakes， updates the model using SGD。

 like small steps toward better predictions。Runs for 50 epochs， completete passes through the data。



![](img/af8c39e3bd1d4ae804615df3eeef3050_13.png)

Watch how the loss number of mistakes gets smaller over time。



![](img/af8c39e3bd1d4ae804615df3eeef3050_15.png)

Finally， let's see how our model separates the groups。Gray area shows the decision boundary。



![](img/af8c39e3bd1d4ae804615df3eeef3050_17.png)

Lightside predicts yellow group。

![](img/af8c39e3bd1d4ae804615df3eeef3050_19.png)

Dark side predicts purple group。

![](img/af8c39e3bd1d4ae804615df3eeef3050_21.png)

See how the model drew a smooth line between our clusters。



![](img/af8c39e3bd1d4ae804615df3eeef3050_23.png)

Today， we learned how to teach a computer to separate two groups of points using logistic regression。

 The decision boundary shows us exactly how the model makes its predictions。



![](img/af8c39e3bd1d4ae804615df3eeef3050_25.png)

![](img/af8c39e3bd1d4ae804615df3eeef3050_26.png)