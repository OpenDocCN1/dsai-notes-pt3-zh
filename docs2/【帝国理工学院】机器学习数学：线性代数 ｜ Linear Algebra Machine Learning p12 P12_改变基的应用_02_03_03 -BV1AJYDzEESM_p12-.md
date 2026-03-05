# 【帝国理工学院】机器学习数学：线性代数 ｜ Linear Algebra Machine Learning p12 P12_改变基的应用_02_03_03 -BV1AJYDzEESM_p12-

![](img/ca397c167d77def8c1645d50e817de25_0.png)

For example， say I have a bunch of of 2D data points like this。

And so they will more or less lie on a straight line， right， We can， we can kind of see that。

 These guys all more or less line a line that's gonna be something like that。

I can imagine reddescribing that data by mapping them onto that line and then saying how far theyre along that line。

 So I can map this guy down onto the line， and I could say the origin maps down there。

 and I can then say this data point is that far along the line。And he's also。

 so is that far along the line？😊，There and hes that this far away from the line。

 So I've got two dimensions here， how far I am along the line and how far I am from the line。

And these guys， they're all slightly different distances from the line。😡。

There's a little bit of an argument in sta as to whether we do the distance。That way。

 vertically or that way as a projection of the distance from the line， but。

It's sort of a theoretical argument， but notice that this distance from the line is effectively a measure of how noisy this data cloud is。

 if they are all tight on the line， they'd all be very small distances away。

 And if they were all quite spread， they'd be quite big distances away。

 So this distance from the lineness。Is effect of the noise。

 And that's information that isn't very useful to us。 So we might want to collapse it。

 except that that noise dimension tells me how good this line fit is。 If the best fit line was。

 was all skewed was all wrong。 I get a much bigger numbers for the noisiness。

And if the best fit line was as good as possible， I get the minimum possible number for the noisiness。



![](img/ca397c167d77def8c1645d50e817de25_2.png)

So that noise dimension contains information that's going to tell me how good my fit is。

 So what I'm doing data science it tells me how good my fit of to my data is and the way I've defined these two dis along the line and away from the line。

 they're orthogonal to each other so I can use the dot product to do the projection to map the data from the X Y space onto the space of the line along the line and away from the line。

😊，Which is what we deal learn to do in the last little segment。

 Now if we're thinking about a neural network in machine learning that recognizes faces。

 say maybe I'd want to make some transformation of all the fixed pixels interface a face into a new basis that describes the nose shape。

 the skin hue， the distanceson between the eyes， those sorts of things and discard the actual pixel data。

 So the goal of the learning process of the neural network is going be to somehow derive a set of basis vectors that extract the most information rich features of the faces。

So in this video， we've talked about the dimensionality of a vector space in terms of the number of independent basis vectors that it has。

 and we found a test for independence that the set of vectors are independent if one of them were a linear combination of the others。

And we've talked more importantly about what that means in terms of mapping from one space to another and how that's going to be useful in data science and machine learning。

