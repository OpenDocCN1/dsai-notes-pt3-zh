# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p63 P63 Recitation 12 Dimensionality reduction PCA Apr 9 -BV1Lcnhz1E7P_p63-

Welcome， everybody。 Let's get started。 This station would be on dimensionality reduction。

 specifically PCA and kernel PCA。嗯。So first， what we mean when we are talking about dimensionality reduction specifically linear dimensionality reduction。

We have a data set X。This data set consists of n examples。And each example of is of dimensional L TD。

 So the notation here might be。Different from what we have seen before in the regulation。

 for example， where those are examples， here， columns are examples。

And we would like to present this smatic X。As。A product of two mat。The Umatics is a ds k。

Where K is supposed to be much。lowower人体。And Zed。Is a caseos and matrixtic。Diamond， like from。Now。

 the number of dimension point of view of this multiplication should result in a deco ands。嗯。

If we look at each column of these matrix zip I， we can think of each column as。

Some representation of X I， but in K dimensional space other than a D dimensional space。

 So it's a lower dimensional representation。嗯。Of Z， I， of X I。嗯。And this song。Linear transformation。

I will call it。See science force。Such that Z I is C trans X I。U。And also。

 we would like to have a way to reconstruct back our。Relational X， iPhone Z I。

We won't be able to do that perfectly， but let's say， approximately this。Some transformation。

 linear transformation。 And I will call it you。Such that approximately X I is equal to U Z I。Okay。U。

If we look at this matrix representation， we can easily see that this matrix U and these matrix U are the same。

 right， So each X I is equal to U Z I。😊，嗯。And if you is an also normal mes。Then。This is also you。

Basically。Youd， you multiply youth transpo by you， youll get an identity。And so， Z， I is indeed。

U transpo Excel。So。Okay。Now， they are like various kinds of。Dimmenality reduction techniques。

 And basically， their difference is。Like， what's the criteria of finding the best。U Z effectization。

And the one that we have seen in the lecture is principal component analysis。

And the criteria for principle component analysis is that we want to find。U and Z。

 such that I can equally select X with minimal L。And so we will go into that with more detail。

 But before we do that， why would we do this kind of dimensionality reduction thing。

So we are replacing our axiss with a lower dimension Z。And that。Would help us。嗯。

From implement like computational and the storage efficiency efficiency point of view。Also。

 like it will， we have seen that， like sample complexity。

For supervised learning depends on the number of features。

And so if you use the number of features you acquire。This samples。嗯。It。

 it's also useful for interpretation and visualization。

 So if I give you a bunch of 100 dimensional examples， it would be difficult to like。

Look at the data， understand the structure， the clustering。This sort of aspects。 But if you do。

 for example， PC A， you can project them to a two dimensional space。And。If you are lucky。

You can get patterns， like。That the data is clustered into。Looks clustered into three groups。

 for example。嗯。Even if we like if we are not doing machine learning。Dimensity reduction can。

Can be used as， like， a compression。Mechan is。So， for example， the phase data that we've seen。

 like if you have。En faces。嗯。Rather than installing all。Like。

 rather than showing the exact image of each face。You can do PCA that PC A will get you。

A lower dimensional presentation of each face， each image would be presented by K numbers other than D numbers。

 and K could be as low as 10， whereas D could be like 1000。诶。And all you need。

 And rather than keeping that rather than storing all faces。

 you need to store whats what we have called the eigenfaces。 You need to store the Umatics。

So that you can equistruct。A face。Given its lower dimensional representation。So。In a nutshell。

 we have data X。Okay。We figured out you。From that， we can compute Z equals。U sign equal x。

And we can keep the Z as a lower dimensionia representation of the data。嗯。

If we have a new data point that was not in our data。So let's call it X。We kind of still。

Find a lower dimensional presentation of that new point using the umatic that we already learned。嗯。

Now we can build our classifiers， our clustering algorithms。嗯。

All our influence albums on the lower dimensional Zs。If we。Have， like。

 if we stole the lower dimensional presentation and we want to go back to the full dimensional presentation。

We approximate。X I as U ZR。Okay。So。So let's start with PCA。And assume our full。

 because we are doing this on the blackboard。We want to compress。

Two dimensional data point into a one dimensional data point。嗯。And so we have a bunch of examples。

Okay。Each example is two dimensional。And we want。To present each example。As a single number。U。

And we will assume that the examples。Haves you mean。So the data is centered around zero。

And we want to find that a presentation。 We want to find Z， I。Is equal to。U transpo Xi。Okay。U。

So in this case， you would be a vector。We basically。

 we are searching for a vector that is like a direction direction。

