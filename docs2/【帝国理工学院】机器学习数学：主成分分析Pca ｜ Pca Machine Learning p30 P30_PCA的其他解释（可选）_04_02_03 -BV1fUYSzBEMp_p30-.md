# 【帝国理工学院】机器学习数学：主成分分析Pca ｜ Pca Machine Learning p30 P30_PCA的其他解释（可选）_04_02_03 -BV1fUYSzBEMp_p30-

![](img/5912cdcb373083bf61ec856e20570491_0.png)

We derive PCA from the perspective of minimizing the average squared reconstruction error。 However。

 PCA can also be interpreted from different perspectives in this video。

 we'll have a brief look at some of these interpretations。

Let's start with a recap what we have done so far。We took a high dimensional vector x。

And we projected it onto a lower dimensional representation Z using the matrix B transpose。

The columns of this matrix B are the eigenvectors of the data covariance matrix that are associated with the largest eigenvalues。

The Z values are the coordinates of our data point with respect to the basis vectors which span the principal subspace。

 and that is also called the code of our data point。

Once we have that low dimension of representation Z， we can get a higher dimensional version of it。

By using。The matrix B again。 So multiplying B onto Z。To get。A higher dimensional version。

Of the Z in the original data space。We found the PCA parameters such that the reconstruction error between x。

And。The reconstruction， extilder。Is minimized。We can also think of PCA as a linear auto encoder。

An auto encoder encodes a data point X。And tries to decode it to something similar to the same data point。

The mapping from the data to the code is called an encoder。Let's write this down So this。

Part here is called an encoder。The mapping from the code to the original data space is called the decoder。

If the encoder and decoder are linear mappings， then we get the PCA solution when we minimize the squared auto encoding loss。

If we replace the linear mapping of PCA with a nonlinear mapping， we get a nonlinear auto encodeder。

A prominent example of this is a deep auto encodeder where the linear functions of the encodeder and decoder are replaced with deep neural networks。

Another interpretation of PCA is related to information theory。

 We can think of the code as a smaller compressed version of the original data point。

 When we reconstruct our original data using the code， we don't get the exact data point back。

 but a slightly distorted or noisy version of it。This means that our compression is lossy。

Intuitively， we want to maximize the correlation between the original data and the lower dimensional code。

More formally， this would be related to the mutual information we would then get the same solution to PCA we discussed earlier in this course by maximizing the mutual information。

 a core concept in information theory， when we derived PCA using projections。

 we reformulated the average reconstruction error loss as minimizing the variances of the data that is projected onto the orthogonnal complement of the principle subspace。

Minimizing that variance is equivalent to maximizing the variances of the data when projected onto the principal subspace。

If we think of variances in the data as information contained in the data。

 this means that PCA can also be interpreted as a method that retains as much information as possible。

 We can also look at PCA from the perspective of a latent variable model。We assume that an unknown。

 lower dimensional code z。Generates data X。And we assume that we have a linear relationship between Z and x。

 So generally， we can then write that X is。B times Z plus mu， and maybe some noise。

We assume that the noise is。Iotropic with mean zero and covariance matrix sigma squared times I。

 we further assume that the distribution of this Z is a standard normal。

 so P of Z is Gaussian with mean0 and covariance matrix， the identity matrix。

We can now write down the likelihood of this model。 So the likelihood is。P of x， given z。

And that is a Gaussian distribution in X with mean。B Z plus mu。And covariance matrix。Sigma squared I。

And we can also compute the marginal likelihood。As。P of x。I's the integral。Of P of x given Z。

 So that is the likelihood。Times the distribution on Z。D it。

And that turns out to be a Gaussian distribution in x with mean。Mux and with covariance matrix。

 B times B transpose plus sigma squared。系。The parameters of this model are。Mu。Bi。And sigma squared。

 And we can write them explicitly down in our。Model up here。So models， model parameters are。B。And mu。

And sigma square。We can now determine the parameters of this model。

 using maximum likelihood estimation。And we will find that mu is the mean of the data。

 and B is a matrix that contains the eigenvectors that correspond to the largest eigenvalues。

To get the load dimensional code of a data point， we can apply base theorem to invert the linear relationship between Z and x。

In particular， we are going to get。P of Z， given x。As。P of x， given Z。So that is the， the likelihood。

 which is comes from here。Times P of Z。 So that's our distribution。That we have here。

Divided by the marginal likelihood P of x， which comes from here。In this video。

 we looked at five different perspectives of PCA that lead to different objectives。

Minimizing the square reconstruction error， minimizing the auto encoder loss。

Maximizing the mutual information。 maximizing the variance of the projected data。

And maximizing the likelihood in a latent variable model。

All these different perspectives give us the same solution to the PCA problem。

 The strengths and weaknesses of individual perspectives become more clear and important when we consider properties of real data。



![](img/5912cdcb373083bf61ec856e20570491_2.png)