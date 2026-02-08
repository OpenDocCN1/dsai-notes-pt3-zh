# 延世大学《新兴技术从智能手机到物联网再到大数据Emerging Technologies From Smartphone to IoT to Big Data》 - P28：27_4.2 Spark ML算法（第2部分）.zh_en - GPT中英字幕课程资源 - BV18hpFewEcG

![](img/6e1c4de16cf7e6df46dd1450964db925_0.png)

Decision tree technology。A logical region is identified。

 classified in a sequence of recursive splitting decisions in an effective way。

Fewer number of processing steps are used， and each step has lower computation。

 which is great when you're analyzing big data。Results in a hierarchical tree shape form。

The hierarchical algorithm is used in supervised learning training of the decision tree。

 What does this mean supervised learning？Supervised learning is a training used in machine learning systems。

 where we have label data that is data with a desired output already known。

Since the desired output is known and we use it as an input to compute an output。

 then we know the desired output， we know actually what the output was so we can compute the error。

 and we can use the error to go and train the system。

 the machine learning system to make it more accurate。That is what we do in back propagation。

 where the error is back propagated into the system and we retune it。

 we do the learning process to make it more fine tuned and accurate。

Decision tree example is provided here where for classification， decision boundaries on the data。

 white dots and red dots can be determined using a decision tree。

That looks like this where we have x larger than H1 as one decision threshold。

 and then we have y larger or smaller than H2 can be another decision mechanism。If it passes one。

 then basically a red dot domain， if it passes the second decision boundary。

 then we can divide it into red or white based on did it pass or not now placing the decision boundaries on the graph over there you can see H1 to the right side is where we classify the red dots and then we use H2 below that blue line is where we classify the red dots using H1 and H2 in a decision tree mechanism we can classify where the red dots are。

Collaborative filtering。This is a machine learning algorithm that collects preferences or taste information from many users。

And it uses this information to make automated predictions about the interest of other users。

Looking into the terminology， because we're using combined， collect information。

 that's where we get collaborative。😊，And then we're going to filter out the less probable options until we find the most probable prediction result that's why we call it filtering and combining these two words together is where we get the name collaborative filtering。

😊，For example， of collaborative filtering being used。

 a music vendor can recommend music to a new user based on information on user A whose characteristics seem similar。

We have a new user that entered our domain。 We want to recommend some music。

 but we don't know what the new user would like。 no reference value。

 So we go through and find a similar user with similar characteristics and find what that user likes。

 like music B。 And then when we use that to recommend that to our new user。

 This type of results can be obtained through collaborative filtering。😊，Clustering technology。

 this is a process of finding similar characteristics in a data set to form groups of data。

Training data consists of a set of input vectors without any corresponding target values。

Data set contains no information， no labels on data and cluster relation。

That is why unsupervised learning is needed。Kminan's algorithm is one of the most popular。

 most famous clustering algorithms that exist。So we'll take a look into it。

Unlabeled data is classified into K classes， the number of classes K is what you may specify in your algorithm and meaning that it's unlabeled means that we do not have a desired output labeled to the input data that we have。

 so therefore we have to use this unlabeled data to go ahead and train the system and make a decision on how we are going to do the clustering。

The mean， the average of each class is updated when new data vector is received。

And the mean value is used to update the division of the classes， the clusters。

All data is originally color less， but I'm going to go ahead and use yellow as its original color before we classify it as red or white。

For a first step， it goes to decide the two centers of the classes randomly。In the figure over there。

 you see two x's， they're just placed anywhere。And based on that， in step two。

 allocate the data into the nearest cluster， so based on these two x's that we have here。

 we're going to ahead and classify the data， and then we're going to draw a line right here。

 the blue line， which will be the division of the two clusters， the two classes。Then in step three。

 calculate the mean of each class based on the average distance。

 and that is what you're doing over there。And then allocate the data into the nearest center。

 which you see the blue line right here， dividing it up。

Then we're going to calculate the mean of each class again based on the average distance。

 which you see that's being processed over there。And then in the final step。

 we're going to allocate the data vector into the nearest centers again over here。So as you see。

 we've been updating this going back and forth a couple of times， recalculating the average。

 then calculate the nearest distance， then do the clusterization again。

 and then we go back and calculate the average， and then we do this over again。And then eventually。

 we have a good division of clusters。If new data， a new vector joins in。

 then we will repeat this process again so that it is properly classified。It took a couple of steps。

 but it was so simple to do that is why K means is such a popular and effective。

Clustering algorithm In addition， it was unsupervised based。

 meaning that we did not have any reference information at the beginning。 however。

 eventually we found a good way to classify and cluster the data。Dimenssality reduction。

This is used to reduce dimensionality by projecting the data to a lower dimensional subspace。

It captures the essence of the data， it reduces the complexity of the classifier and regressor。

Complexity depends on the number of inputs， both the time and space complexity needs to be considered。

For an example， the drone management map generation is used here where data that we have for a drone is three dimensional。

 longitude， latitude and altitude， where we're going to map longitude to x。

 latitude to y and altitude to the Z axis individually。And therefore， it is three dimensional。

However， if we want to draw a simplified two dimensionmensional longitude and latitude drone map。

 then we can go ahead and do this process。 Now， I must say in events that dimensionality reduction is done on much more complicated problems。

 I chose this problem to make it as simple as possible for you to understand。 However， the concept。

 I hope will be well transferred。 So from a three dimensionmenal location of a lot of drones there that have longitude latitude as well as altitude we can go ahead and map them down to the longitude and latitude by removing the altitude information and therefore。

 we map it down here。 where。😊，This information mapping is done over here and we take the map results from 3D to 2D。

Then we see that we can remove the Z axis since we already remove the altitude information。

And then we can flip this up to get that result over there in a 2D structure， X and Y。

Assuming that altitude information Z is not needed。

 we can conduct this and by eliminating Z from data。

 we can capture the essence of the data in a two dimensional structure。

 This is what dimensionality reduction is about。Machine learning algorithms that we looked into included the basic statistics ones。

 classification and regression ones and these other ones。

 and all of them are very powerful and Spark uses them in the machine learning library to analyze data to filter data to do predictions therefore Spk is so powerful in addition as I mentioned in my former lectures。

 the Mahat engine does this for Hadoop as well so therefore Mahat is the machine learning engine that can be used in Hadop。

And these technologies will help spark technology events much more in the future。

These are the references that I use and I recommend them to you， Thank you。



![](img/6e1c4de16cf7e6df46dd1450964db925_2.png)