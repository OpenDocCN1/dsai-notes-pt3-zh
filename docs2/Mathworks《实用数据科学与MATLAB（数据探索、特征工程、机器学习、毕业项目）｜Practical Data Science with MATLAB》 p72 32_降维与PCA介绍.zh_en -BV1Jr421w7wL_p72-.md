# Mathworks《实用数据科学与MATLAB（数据探索、特征工程、机器学习、毕业项目）｜Practical Data Science with MATLAB》 p72 32_降维与PCA介绍.zh_en [BV1Jr421w7wL_p72]

🎼，You've just learned how feature selection methods can be used to improve predictive models by retaining only the features that matter。



![](img/c992a86a122026e9fe76abb5d0bfeef2_1.png)

In particular， you used variance thresholdholding to evaluate a feature set and retain high variance features like X that are likely to be useful in a predictive model and discard low variance features like Y that aren't。



![](img/c992a86a122026e9fe76abb5d0bfeef2_3.png)

![](img/c992a86a122026e9fe76abb5d0bfeef2_4.png)

Vance thresholdholding is more difficult to apply to feature sets like this one， however。

Even though the data is distributed in a similar manner。

 the variance is now shared more evenly between the two features。In this video。

 you'll learn how principal component analysis or PCA。



![](img/c992a86a122026e9fe76abb5d0bfeef2_6.png)

Can be used to generate a new feature set that can help you capture the maximum amount of variance with the fewest number of features。



![](img/c992a86a122026e9fe76abb5d0bfeef2_8.png)

Let's start by returning to the original feature set。



![](img/c992a86a122026e9fe76abb5d0bfeef2_10.png)

This time， we just use a small sample of data points to make things easier to see。

If we use variance thresholdholding to eliminate why the number of features also known as the dimensionality of the feature set is reduced by one。

Gemetrically， this corresponds to the two dimensional Xy data being projected onto the axis of the remaining feature X。



![](img/c992a86a122026e9fe76abb5d0bfeef2_12.png)

Dimenssionalality reduction is a common step in data analysis and machine learning workflows that offers many of the same benefits as feature selection。



![](img/c992a86a122026e9fe76abb5d0bfeef2_14.png)

It enables you to focus your analysis on a smaller subset of important features。

 which are then easier to explore， summarizeize and visualize。

 It also helps you create simpler and more efficient machine learning models。



![](img/c992a86a122026e9fe76abb5d0bfeef2_16.png)

While there are many benefits of dimensionality reduction。

 there is a cost to removing a feature in the information it contains。

One measure of the information that's lost is the projection error。



![](img/c992a86a122026e9fe76abb5d0bfeef2_18.png)

Which is the total distance between the original and projected data points。



![](img/c992a86a122026e9fe76abb5d0bfeef2_20.png)

For this feature set， it's clear that the error incurred by projecting onto the X axis。

Is much smaller than if we had instead projected onto the y axis。



![](img/c992a86a122026e9fe76abb5d0bfeef2_22.png)

Looking at a sample of the second feature set。It's clear that the projection errors will be large for both the X and y axis。

And neither axis will minimize the error。However， you can minimize the projection error by defining a new axis。

The direction of this special axis is called the first principal component of the feature set。

Pinncipal components have a couple of properties that make them especially helpful for dimensionality reduction。

They determine the direction of the axis that minimizes projection error， and as it turns out。

 this is also the direction of maximum variance。In this example。

 since the principal component axis captures most of the variance。

You can use it to define a new feature， P。You can then replace both X and Y with P。

Reducing the dimensionality of the feature set by one。



![](img/c992a86a122026e9fe76abb5d0bfeef2_24.png)

The values of the new feature are determined by projecting the original feature values onto the new axis and measuring the signed distance from the origin to each projection。

These values are commonly referred to as the principal component scores。



![](img/c992a86a122026e9fe76abb5d0bfeef2_26.png)

So far， we've only talked about the first principal component。



![](img/c992a86a122026e9fe76abb5d0bfeef2_28.png)

The total number of principal components is equal to the dimensionality of the feature set。

The second principle component is the direction of maximum variance that isn't already accounted for by the first component。

 Its direction is therefore perpendicular or orthogonal to the first principal component。



![](img/c992a86a122026e9fe76abb5d0bfeef2_30.png)

![](img/c992a86a122026e9fe76abb5d0bfeef2_31.png)

In more than two dimensions， principal componentss are determined in order of decreasing variance as follows。



![](img/c992a86a122026e9fe76abb5d0bfeef2_33.png)

Start by obtaining the first principal component。

![](img/c992a86a122026e9fe76abb5d0bfeef2_35.png)

The second principal component lies in the direction of maximum variance。

Among all directions orthogonal to the first principal component。

The third principle component is the direction of maximum variance among all directions orthogonal to the first two components。

This process is continued until there is only one orthogonal direction remaining。

 which becomes the final principal component。

![](img/c992a86a122026e9fe76abb5d0bfeef2_37.png)

The result is a new coordinate system where the original axes have been rotated。

 so the variance is maximized along the new axes。

![](img/c992a86a122026e9fe76abb5d0bfeef2_39.png)

Now that you've learned what principal opponents are and how they are found。

Let's see how they can be used to reduce the dimensionality of your feature set。First。

 it's important for comparison purposes that all features have similar scales。

The feature set should also be centered at the origin so that the features all have zero meme。



![](img/c992a86a122026e9fe76abb5d0bfeef2_41.png)

The next step is to obtain the principal components。

As well as the corresponding scores and variances。

![](img/c992a86a122026e9fe76abb5d0bfeef2_43.png)

Next， apply variance threshold so that only the high variance components are retained。



![](img/c992a86a122026e9fe76abb5d0bfeef2_45.png)

Another common approach is to set a percentage of the total variance to preserve。

Then keep the smallest number of components， such that this condition is met。In either case。

 the result is a new， lower dimensional feature set。



![](img/c992a86a122026e9fe76abb5d0bfeef2_47.png)

Where the feature values are given by the scores for each retained component。Later in this lesson。

 you'll learn how to perform principal component analysis in MATLb to reduce the dimensionality of your feature sets。



![](img/c992a86a122026e9fe76abb5d0bfeef2_49.png)

🎼。