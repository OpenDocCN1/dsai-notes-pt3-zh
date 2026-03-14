# 【帝国理工学院】机器学习数学：主成分分析Pca ｜ Pca Machine Learning p29 P29_高维PCA_04_02_02 -BV1fUYSzBEMp_p29-

![](img/92b704636940694cfb85ac1fc02fb1ff_0.png)

In the last video， we've gone through the steps of the PCA algorithm。In order to do PCA。

 we need to compute the data covariance matrix。Indeed。

 it mentions the data covariance matrix as a D by D matrix。If D is very high。

 so in very high dimensions， then computing the eigenvalues and eigenvectors of this matrix can be quite expensive。

It scales cubically in the number of rows and columns。 In this case， the number of dimensions。

In this video， we provide a solution to this problem for the case that we have substantially fewer data points than dimensions。

Assume we have a data set。Given as。X 1。Up to。X， N in。R D。

 and we assume that the data is sentenced or has mean 0， then the data covariance matrix。

It's given us S equal to 1 over n times x transpose。Times x。

Where we define x to be the matrix that consists。Of x1 transpose up 2。X， and transpose。

And that is in。N by D matrix， We now assume that n is significantly smaller than D。

 That means the number of data points is significantly smaller than the dimensionality of the data。

And then the rank of the covariance matrix is n。So rank of S equals n。

And that also means it has d minus n plus1 many eigenvalues， which are 0。

That means that the matrix is not full rank， and their rows and columns are linearly dependent。

 In other words， there are some redundancies。In the next few minutes。

 we'll exploit this and turn the D by D covariance matrix S into a full rank n by N covariance matrix without eigenvalues 0。

I've just moved the Cavariance definition up here to have a bit more space on the board。In PC。

 we ended up with the following eigenvalue eigenve equation。

 We had S times B equals lambda I times B， where B is a basis vector of the orthogonal complement of the principal subspace。

 Now， let's rewrite this equation a little bit。 We're now going to replace S with a definition up here。

 So we'll get。1 over n。Times x transpose x， this is S。Times， B， I equals。Lnda eye。Times B I。

And now we multiply x from the left hand side。So we would get。X。Times。X transpose x。B I。

Time to1 over n。Equals。Lada eye。Times。X。Times。BI and now we have a new eigenve eigenvalue equation。

So Lambda i is still an eigenvalue。And now we have eigenvectors x times bi。Which we call C I。

Of the matrix1 over n times x times x transpose， this means that1 over n times xx transpose has the same nonzero eigenvalues as the data covariance matrix。

But this is now an n by n matrix so that we can compute the eigenvalues and eigenvectors much quicker than for the original data covariance matrix。

All right， so this is。An n。By n matrix。Whereas S used to be a D by D matrix。

So now we can compute the eigenvectors of this matrix 1 over n times xx transpose。

And we use this to recover the original eigenvectors， which we still need to do PCA。Currently。

 we know the eigenvectors of 1 over n times xx transpose。

And we want to recover the eigenvectors of S。If we left multiply our eigenvalue eigenbacter equation with x transpose。

 we get the following。You get。1 over n。Times， x transpose。Times x times x transpose。Times。Xiai。

Equals lambda， I times。Ex transpose。Times。C i。And now we find our S matrix again。This。Is S？

And this also means that we recover cover x trans pulse times C as an eigenvector of S that belongs to the eigenvalue lambda I In this video。

 we reformted PCA such that we can efficiently run PCA on data sets where the dimensionality of the data is substantially bigger than the number of data points。

