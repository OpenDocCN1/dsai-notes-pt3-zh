# 多伦多大学【中英⚡降维与流形学习｜2023,Dimensionality Reduction and Manifold Learning】 p01 P1 Introduction to Dimensionality Reduction - Presentation at WangLab in the Uni -BV1aeidBPEiQ_p1-

![](img/88a7e4a591a7aacb266dedd675a46392_0.png)

AndHere today we're going to talk about damage reduction， the reduction to that and afterwards。



![](img/88a7e4a591a7aacb266dedd675a46392_2.png)

哦 it's application。然后你。诶。So first introduction to dimensional reduction and what that is， by the way。

 please feel free to interrupt me whether we are online or in person。

 just let me know when you want to discuss our talking about assumptions。



![](img/88a7e4a591a7aacb266dedd675a46392_4.png)

![](img/88a7e4a591a7aacb266dedd675a46392_5.png)

![](img/88a7e4a591a7aacb266dedd675a46392_6.png)

好的。So manifold hypothesis， at first， what is data consider a measurement of the quantity can be anything as personal health data images or the specific chain and any kind of measurement that you have。

 we can consider a set of these instances as a data set。



![](img/88a7e4a591a7aacb266dedd675a46392_8.png)

![](img/88a7e4a591a7aacb266dedd675a46392_9.png)

![](img/88a7e4a591a7aacb266dedd675a46392_10.png)

And each point has a data point so each point can be multidimensional data， for example， an image。

 its dimensions or features are its pixels or personal health data。

 it can be different features such as age， blood pressure and different things。



![](img/88a7e4a591a7aacb266dedd675a46392_12.png)

![](img/88a7e4a591a7aacb266dedd675a46392_13.png)

![](img/88a7e4a591a7aacb266dedd675a46392_14.png)

So if you put together， put them together， every data point can be considered as a vector in the space and if you put the vectors column wise or row wise next to each other。

 you will have a matrix of data。

![](img/88a7e4a591a7aacb266dedd675a46392_16.png)

![](img/88a7e4a591a7aacb266dedd675a46392_17.png)

So。Your data sets will be considered as a matrix。

![](img/88a7e4a591a7aacb266dedd675a46392_19.png)

And as you capture your data usually naturally and your data is natural。

 it's not noise it's random noise， they usually lie on a submanifold。

 they don't cover the whole space， to agree with me。



![](img/88a7e4a591a7aacb266dedd675a46392_21.png)

![](img/88a7e4a591a7aacb266dedd675a46392_22.png)

Or yeah， because if it's random noise of course it might be everywhere for example soon your data is 3D right and then and if it is random noise it can cover the whole area in here。

 but if it's just the images of a scene where you can see trees and these things。



![](img/88a7e4a591a7aacb266dedd675a46392_24.png)

![](img/88a7e4a591a7aacb266dedd675a46392_25.png)

![](img/88a7e4a591a7aacb266dedd675a46392_26.png)

And shown that you only have three pixels hypothetically。

 then you only have some points in this space， specific regions in this space。

 not the whole area in this room。

![](img/88a7e4a591a7aacb266dedd675a46392_28.png)

![](img/88a7e4a591a7aacb266dedd675a46392_29.png)

It means that the data points lie on some subsspace。

 so they don't cover the whole space because they are not random， they are usually natural data。

 not noise。

![](img/88a7e4a591a7aacb266dedd675a46392_31.png)

![](img/88a7e4a591a7aacb266dedd675a46392_32.png)

And then， for example。In figure a， you can see that by there are 3 inter points but they lie on a linear。



![](img/88a7e4a591a7aacb266dedd675a46392_34.png)

hyperplane or plane here because you are 3D and they might be also non nonlinear so the subspace or sub manifold can be nonlinear such as here as it it's not a linear plane although locally topologically speaking it's the plane again however it's not nonlinear em but it in this space and it can also。



![](img/88a7e4a591a7aacb266dedd675a46392_36.png)

![](img/88a7e4a591a7aacb266dedd675a46392_37.png)

![](img/88a7e4a591a7aacb266dedd675a46392_38.png)

![](img/88a7e4a591a7aacb266dedd675a46392_39.png)

![](img/88a7e4a591a7aacb266dedd675a46392_40.png)

AndNot that here。So whenever it's linear， we usually call it subspace， whenever it's nonlinear。

 we usually call it submanifold or manifold。

![](img/88a7e4a591a7aacb266dedd675a46392_42.png)

![](img/88a7e4a591a7aacb266dedd675a46392_43.png)

So and what's is manifold hypothesis， Manfold hypothesis says that data points usually lie on some submanifold。

They don't color the whole space。You always have the somehe。



![](img/88a7e4a591a7aacb266dedd675a46392_45.png)

我。Even if it starts smoothness of sub manfold， you can feed some smooth sub manifold usually so you want to feed some sub manifold。

 which is usually smooth because it's easier to work with and take derivative。



![](img/88a7e4a591a7aacb266dedd675a46392_47.png)

![](img/88a7e4a591a7aacb266dedd675a46392_48.png)

![](img/88a7e4a591a7aacb266dedd675a46392_49.png)

诶。

![](img/88a7e4a591a7aacb266dedd675a46392_51.png)

So categories of damage shelter reduction。

![](img/88a7e4a591a7aacb266dedd675a46392_53.png)

We can divide and generally speaking we can divide dimension reduction two into three categories。

 although I I know that some of you might say there is effort one we will talk about that too but。



![](img/88a7e4a591a7aacb266dedd675a46392_55.png)

![](img/88a7e4a591a7aacb266dedd675a46392_56.png)

There is a spectral methods， there are probabilistic methods and there are neural network based methods for these methods some might say。

 okay， there are Rimanian methods too how that we can cover Rimanian methods in these categories so it can be considered as a sub category。



![](img/88a7e4a591a7aacb266dedd675a46392_58.png)

![](img/88a7e4a591a7aacb266dedd675a46392_59.png)

![](img/88a7e4a591a7aacb266dedd675a46392_60.png)

![](img/88a7e4a591a7aacb266dedd675a46392_61.png)

And we'll talk about each of these categories。So the first one category。

 which is spectral dimensional reduction。Usually they have geometrical approach。

And they usually reduce at the end when you solve the optimization problem of these methods。

 they usually reduce to generalized eigenvalue problems。

And I assume that you all of you know what eigenvalue and generalized eigenvalue problems are。

 but just for a brief review， so whenever you have a matrix what is eigenvalue and eigenvector whenever you have a matrix this matrix shows some important directions in the space usually and these directions you can consider them as eigenvectors so we have different types of matrix decomposition and what is matrix decomposition is that whenever you decompose a matrix into multiplication of two or three or b optical matrix。



![](img/88a7e4a591a7aacb266dedd675a46392_63.png)

![](img/88a7e4a591a7aacb266dedd675a46392_64.png)

![](img/88a7e4a591a7aacb266dedd675a46392_65.png)

![](img/88a7e4a591a7aacb266dedd675a46392_66.png)

![](img/88a7e4a591a7aacb266dedd675a46392_67.png)

![](img/88a7e4a591a7aacb266dedd675a46392_68.png)

![](img/88a7e4a591a7aacb266dedd675a46392_69.png)

That's what matrix decomposition。Does of the one of the decompositions is eigenvalue decomposition and eigenvalue decompositionposition gives you the important directions of matrix an example when you have data and when when the real matrix is a covariance matrix what are the important directions of the coence matrix are the directions ofvari of the data or spread of data so whenever you get the eigenvectors of the covarience matrix you will get the directions where the data are spread and that's exactly PC which will cover so and eigenvalues are the amount of that importance of the directions。

😊。

![](img/88a7e4a591a7aacb266dedd675a46392_71.png)

![](img/88a7e4a591a7aacb266dedd675a46392_72.png)

![](img/88a7e4a591a7aacb266dedd675a46392_73.png)

And generalized eigenvalue problem is a more generalized eigenvalue problem where you have another matrix。

 so you have two matrices kind of。

![](img/88a7e4a591a7aacb266dedd675a46392_75.png)

And spectral our methods usually reduce to those argumentgon problems and also they have geometrical approach where you can see like this。

 for example in figure a you can see that they are lying on a non nonlinear manifold and we want to unfold it in the space so we know that this is the subspace the sub manifold theres the sub manifold is locally d2 dimensional although it's embedded in the3 manifold today so。



![](img/88a7e4a591a7aacb266dedd675a46392_77.png)

![](img/88a7e4a591a7aacb266dedd675a46392_78.png)

![](img/88a7e4a591a7aacb266dedd675a46392_79.png)

![](img/88a7e4a591a7aacb266dedd675a46392_80.png)

![](img/88a7e4a591a7aacb266dedd675a46392_81.png)

![](img/88a7e4a591a7aacb266dedd675a46392_82.png)

So we can unflow you。

![](img/88a7e4a591a7aacb266dedd675a46392_84.png)

And it will become a 2D thing。

![](img/88a7e4a591a7aacb266dedd675a46392_86.png)

Because they're actually locally2D if you apply as this is a non nonlinear manifold。

 if you apply a non nonlinear dimensional reduction method。

 you will get figure B so it unfolds it correctly because it's considering geo distance or if you apply a linear method you will ruin。



![](img/88a7e4a591a7aacb266dedd675a46392_88.png)

![](img/88a7e4a591a7aacb266dedd675a46392_89.png)

![](img/88a7e4a591a7aacb266dedd675a46392_90.png)

![](img/88a7e4a591a7aacb266dedd675a46392_91.png)

Something like if you apply PCA on that， for example， which is a linear method。

 you will ruin that because it only considers the Euclidean distances between them and not the geodesic distances along the manifold。

 therefore， for example， the green points and the red points which are far away from each other。



![](img/88a7e4a591a7aacb266dedd675a46392_93.png)

![](img/88a7e4a591a7aacb266dedd675a46392_94.png)

![](img/88a7e4a591a7aacb266dedd675a46392_95.png)

They will collapse until 2。 August because you apply linear methods， so these are spectral methods。



![](img/88a7e4a591a7aacb266dedd675a46392_97.png)

![](img/88a7e4a591a7aacb266dedd675a46392_98.png)

And what are the probabil negative， Okay， consider this figure， for example， you have a sculpture。



![](img/88a7e4a591a7aacb266dedd675a46392_100.png)

And you are looking at it from different angles， right？



![](img/88a7e4a591a7aacb266dedd675a46392_102.png)

So。You can see that all of them are showing the same thing。



![](img/88a7e4a591a7aacb266dedd675a46392_104.png)

And all of the images are the same structure， what is the only difference between these？

Re the angle exactly the angle， we can see it as two or three angles。

 but the difference is just angles。

![](img/88a7e4a591a7aacb266dedd675a46392_106.png)

![](img/88a7e4a591a7aacb266dedd675a46392_107.png)

So， we can say that。

![](img/88a7e4a591a7aacb266dedd675a46392_109.png)

Your data， your observed data， which are the images Xi。



![](img/88a7e4a591a7aacb266dedd675a46392_111.png)

Are conditioned from some latent variable， latent random value variable。

 which that actually plays the important role because except that。

 for example here the pixels are not important， the angle is important。



![](img/88a7e4a591a7aacb266dedd675a46392_113.png)

![](img/88a7e4a591a7aacb266dedd675a46392_114.png)

![](img/88a7e4a591a7aacb266dedd675a46392_115.png)

And the angle is making the important rule here， so probabilistic thermo reduction says that I assume that the data is a multidimensional random variable。



![](img/88a7e4a591a7aacb266dedd675a46392_117.png)

![](img/88a7e4a591a7aacb266dedd675a46392_118.png)

However， it's conditioned on a latent bed a lower dimensional latent random variable。

 so if you assume that this random bed a latent random variable is lower dimensional than the actual data then you would have dimensional reduction if you try to find these lower dimensional random variable so this is what and you can probabilistic graphical model you can dry itize this。



![](img/88a7e4a591a7aacb266dedd675a46392_120.png)

![](img/88a7e4a591a7aacb266dedd675a46392_121.png)

![](img/88a7e4a591a7aacb266dedd675a46392_122.png)

![](img/88a7e4a591a7aacb266dedd675a46392_123.png)

So we try to find the Zpi。

![](img/88a7e4a591a7aacb266dedd675a46392_125.png)

And another approach is neural network based or deep di reduction and so it has an information theoretic approach。

 you might say how is it related to that because is that well usually have an encoder and decor and you try to you try to pass your data through a bottleneck and initially your。



![](img/88a7e4a591a7aacb266dedd675a46392_127.png)

![](img/88a7e4a591a7aacb266dedd675a46392_128.png)

![](img/88a7e4a591a7aacb266dedd675a46392_129.png)