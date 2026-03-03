# Vizuara【中英⚡机器学习基础｜Foundations for Machine Learning】 p11 P11 Foundations for ML ｜ Simple intuition of eigenvalues and eigenvectors ｜ Line [BV1wosSzREF7_p11]

![](img/84409780c430974df09c4add315b30db_0.png)

Hi， welcome back to our course on foundations for machine learning。

 we are continuing to learn mathematical foundations and especially within that linear algebra。😊。

In the future lectures we'll of course be learning statistics probability etc。

 but this will be the last lecture where we will be covering basics of linear algebra meant for machine learning in this lecture I'm covering one of my favorite topics eigenvalues and eigenvectors。

😊，The reason why this is one of my favorite topics is because the intuition for getting intuition for understanding eigenvalues and eigenvectors is not really taught in the way this is taught in colleges when I was learning this concept for the first time it was definitely not introduced to me in an intuitive manner but rather there was too much focus on mathematical aspects of eigenvalues and eigenvectors and for that reason I immediately forgot this concept itself and before even forgetting I had a very difficult time understanding in this lecture we'll be trying to develop a very simple geometric intuition behind eigenvalues and eigenvectors and of course we've been looking at this in the through the lens of linear transformations so throughout this course we have been looking at linear transformations right so just to recap we looked at a matrix as a linear transformation if the matrix is a square matrix it will perform linear transformation within that space it it is a non-qua matrix it might transform a vector from let's say a 2D space into3。

Space or from 3D into 2D so the dimensionality might increase or decrease。

We also saw that while matrix to vector multiplication is a linear transformation of a vector。

 a matrix to matrix multiplication is compounded like a complex linear transformation where two linear transformations are applied back to back。

And if you have a rotation transformation and scaling transformation。

 all you need to do is like multiply the vector multiply with the matrix corresponding to rotation and followed by that multiply it with the matrix corresponding to let's say expansion or shear or whichever is your second transformation in this lecture we'll be looking at eigenvectors and eigenvalues from the point of view of transformation linear transformation and this will help us understand a simple geometric intuition rather than a mathematical framework alone。

So mathematically， Im sure you have you are familiar with eigenvalues and eigenvectors。

 most likely if you have not heard of this just in simple terms。😊。

If you have a as a matrix acting on a vector x， ax equal to lambda x。

 if you have something like this here x is called as the eigenvector of matrix a and lambda is called as the corresponding eigenvalue。

Now here a is a linear transformation which transforms the vector x。

 but here the transformation is happening such that the vector the original vector x that is being transformed is simply getting scaled and lambda is that scaling factor。



![](img/84409780c430974df09c4add315b30db_2.png)

So。