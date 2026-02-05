# EPFL《机器学习｜Machine Learning Course CS-433 fall 2020-2021》中英字幕（deepseek - P39：[39]Exercises 13_ getting started video.zh_en - GPT中英字幕课程资源 - BV14SwyeNEvW

![](img/9bb0a661f5d036c51a8fc2f41c1adeda_0.png)

Hello and welcome to this session where I'll talk you through this exercise where we implement a recommender system using matrix factorization。

So you should think of a recommender system as a model that thinks as an input。A user。 And let's say。

 movie。And the output of the system is the predicted rating that this user would give to the movie。嗯。

Zhen。This could be any model in principle。 if you， if you had features about users and about movies。

You could just train a model to do this。 But the challenge here is that for all the users and all the movies。

 we don't really have features。 We just know that it's user 13 and movie 512。So。

Just based on those numbers， you can't say anything。What recommend systems do is kind of implicitly。

Dive features。From the other recommendations of a user。Like。If I always like science fiction movies。

诶。It can look at other users that also like science fiction movies and recommend more of those to me。

Okay， so let's go through a notebook。嗯。

![](img/9bb0a661f5d036c51a8fc2f41c1adeda_2.png)

We' start by loading a data set with movie movie ratings from movie lens data set。



![](img/9bb0a661f5d036c51a8fc2f41c1adeda_4.png)

This dataset set consists of 100000 ratings。And a rating here is a pair of a movie。



![](img/9bb0a661f5d036c51a8fc2f41c1adeda_6.png)

A user and a given rating。So the way we store it here is as three arrays of the same length。

 Like which movie， which user and what did the user think about the movie。



![](img/9bb0a661f5d036c51a8fc2f41c1adeda_8.png)

You don't have to do anything here。 there just loads the data。



![](img/9bb0a661f5d036c51a8fc2f41c1adeda_10.png)

Okay。

![](img/9bb0a661f5d036c51a8fc2f41c1adeda_12.png)

Next， we want to look at the distribution of how many ratings each user gave and how many ratings there are for each movie。



![](img/9bb0a661f5d036c51a8fc2f41c1adeda_14.png)

![](img/9bb0a661f5d036c51a8fc2f41c1adeda_15.png)

嗯。You'll see that there are some movies or users。

![](img/9bb0a661f5d036c51a8fc2f41c1adeda_17.png)

That are just very rare in this dataset and if you only have one example rating for a movie。

 it's too unreliable to make predictions out of it。

 so in the next section here we'll remove entries from the dataset that have two few ratings。



![](img/9bb0a661f5d036c51a8fc2f41c1adeda_19.png)

![](img/9bb0a661f5d036c51a8fc2f41c1adeda_20.png)

So we remove movies that that don't have to don't have enough ratings available。Okay。

 so you have to fill in the blanks here。And the tests can tell you when you did a good job。



![](img/9bb0a661f5d036c51a8fc2f41c1adeda_22.png)

Okay， next。We'll split this dataset into a train and a test split。In this case。

 I will use 10% of the data of the data for testing and 90% for training。



![](img/9bb0a661f5d036c51a8fc2f41c1adeda_24.png)

诶。That just means we'll have some movie。User pair pairs for which we have a rating available。

 but that we don't use for optimizing。The model。ok。诶。

So the way we thought about this data set so far is as three lists。Of information， like which user。

 which movie and which rating。But you can also think of this in a matrix form， which is quite common。



![](img/9bb0a661f5d036c51a8fc2f41c1adeda_26.png)

诶。Where the matrix is basically on the X axis， we have movies， on the Y axis， we have users。

 and the number inside the cell is the rating that the user gave to the movie。M。

This matrix black based on the training set， for example， will have lots of。



![](img/9bb0a661f5d036c51a8fc2f41c1adeda_28.png)

Unknown cells， because we don't have the ratings， but。

The challenge you could see the challenge of recommending as filling in this matrix。

 Like if you fill in this matrix， you know all the possible。

Ratings that any user could give to any movie。

![](img/9bb0a661f5d036c51a8fc2f41c1adeda_30.png)

Okay。

![](img/9bb0a661f5d036c51a8fc2f41c1adeda_32.png)

Next， we'll start to really make predictions。

![](img/9bb0a661f5d036c51a8fc2f41c1adeda_34.png)

And we'll compare a couple of baselines to this matrix vectorization solution。



![](img/9bb0a661f5d036c51a8fc2f41c1adeda_36.png)

And all the methods that are implemented have this form。

 like they will be a class that looks like a predictor。

 here you will already see there is global mean predictor。



![](img/9bb0a661f5d036c51a8fc2f41c1adeda_38.png)

But this is just like an example of how it functions。You create the class and。

When you created your past training data， so what you can do in here is optimize the predictor or like train it。

It also held the predictors also have a coal method implemented。

That means you can use it as a function， kind of。

![](img/9bb0a661f5d036c51a8fc2f41c1adeda_40.png)

Like this is an example of how you would use it， you create the predictor with training data。

 so this could train it， for example， and then to make predictions。



![](img/9bb0a661f5d036c51a8fc2f41c1adeda_42.png)

诶。We call it like a function that that's using this call。With。New date that you want predictions for。



![](img/9bb0a661f5d036c51a8fc2f41c1adeda_44.png)

Okay。So here the first example you'll implement is global mean predictor。

 that means we'll just look at the average prediction that was given by any user to any movie。

 and that's what we'll say。

![](img/9bb0a661f5d036c51a8fc2f41c1adeda_46.png)

For any user movie bear， we'll just say， I think you like it 3。5。



![](img/9bb0a661f5d036c51a8fc2f41c1adeda_48.png)

诶。That's a pretty stupid baseline。 But， you know， it it's good to have those。 It's easy to implement。

 and it gives us a number of quality we can compare our other methods to。

 if they perform worse than this， it's no good。

![](img/9bb0a661f5d036c51a8fc2f41c1adeda_50.png)

![](img/9bb0a661f5d036c51a8fc2f41c1adeda_51.png)

The way we'll compare method is using mean squared error。



![](img/9bb0a661f5d036c51a8fc2f41c1adeda_53.png)

Like over the test set， we'll look at the average squared error of the predicted rating and the real rating。

 and you'll have to implement that here。

![](img/9bb0a661f5d036c51a8fc2f41c1adeda_55.png)

Okay。

![](img/9bb0a661f5d036c51a8fc2f41c1adeda_57.png)

Now， we'll get into slightly more serious baseline。One here is called the user Me predictor。

What it does is for any movie user pair， the rating that will give is the average rating of the user over all movies in a scene。

So if you tend to hate all movies， will guess that you'll hate the next movie， too。

 And if you like all movies， well guess that you'll like any other movie， too。



![](img/9bb0a661f5d036c51a8fc2f41c1adeda_59.png)

Okay。So there's a question here。Is this working better than predicting the global mean in terms of error。



![](img/9bb0a661f5d036c51a8fc2f41c1adeda_61.png)

What do you expect that maybe you should think of this before actually coding it up。



![](img/9bb0a661f5d036c51a8fc2f41c1adeda_63.png)

There's also a question。 why would always predict the user' mean be pretty useless in practice。



![](img/9bb0a661f5d036c51a8fc2f41c1adeda_65.png)

So think about that。

![](img/9bb0a661f5d036c51a8fc2f41c1adeda_67.png)

嗯。And then we can move to the next predictor。 This is the movie's mean predictor。

 It's basically the same thing， but now we will return the average of all movie ratings for a particular movie。



![](img/9bb0a661f5d036c51a8fc2f41c1adeda_69.png)

Irespective of the user。

![](img/9bb0a661f5d036c51a8fc2f41c1adeda_71.png)

So this can be a better model， I think。And you should think for yourself。

 like under which assumption is this a good model。

![](img/9bb0a661f5d036c51a8fc2f41c1adeda_73.png)

嗯。I'll leave that question to you。And again， you should compare the quality you get here to the two we have seen above。

音讯。Think for yourself。 if that matches your expectations。



![](img/9bb0a661f5d036c51a8fc2f41c1adeda_75.png)

Okay， next we'll get into the real meat of。Of this exercise。

You are going implement matrix factorization。And let me just go over the model you're expected to implement。

So。To each movie I in the dataset set， we will assign a D dimensionional trainable representation vector。

 M I。Okay， so the。These vectors。Are going to represent the movies， and if movies are somehow similar。

 meaning that the same users like them， those vectors should also intuitively be similar。

LikeAnd in the same way for each user J。They will also have a D dimensional representation vector。

 U J。And if users have similar taste， those should also be similar vectors。Okay。

 so we can think of those as like separate vectors for each user。

 but you can also stack up all those vectors into matrices。

 Like there is a movie representation matrix M。You know， it has a number of movies。

 rows and D columns。And you can have a user representation matrix U。

 and it has size number of users by D again。So this model。

After we've optimized those representations and we'll see later how to do that。

 it can predict the score that a user。J will give from a movie I as the dot product between those representations。

 like if the user representation and the movie like a line， then this is a high number。

You could think of this as like a kind of cosine that is not normalized。Okay。就。Again。

 so and this is this is formulated as a model now， you know， it has inputs INJ。

It looks up these embeddings or representations， and it gives you a number。

But you can also simultaneously express the predicted scores for all movies and all users as you know。

 this matrix we've discussed before， like a number of movies by number of users。And， you know。

 combining all those predictions that are do products， we'll get a matrix product。

 and that is M U transpose。And is this interpretation as a matrix product。

That gives the name matrix factorization to this type of model。Okay。

 so the last thing we need to discuss is how are we going to optimize those movie and user representations。

That's going to we're just going to do that by optimizing the predicted ratings over the training set。

 so we have an average over a training set。Over it like triples of user movie and rating。

We'll make a prediction of the movie in the user and compare to the real rating。诶。

This gives us like one number per triple。 And we average those Thats the loss。So here。

You expected to。Initialize the movie and the user representations。嗯。Normally， you should。

But like if you want to write good code， you should probably put the training code in here。But。

For now， we just， we will skip the training and we will implement that separately later so we can go step by step。

In the core method here， you should implement this dot product prediction for you know。

 and you should give one rating for each entry in the test dataset set。



![](img/9bb0a661f5d036c51a8fc2f41c1adeda_77.png)

Okay。

![](img/9bb0a661f5d036c51a8fc2f41c1adeda_79.png)

This is a much more complicated model and you know than the baselines。

 so you should really compare the results you got here to the results above。



![](img/9bb0a661f5d036c51a8fc2f41c1adeda_81.png)

And if this is not as good as before， either you made an error or you should consider。

Using a simpler model， like being a simpler is always better。



![](img/9bb0a661f5d036c51a8fc2f41c1adeda_83.png)

Okay。

![](img/9bb0a661f5d036c51a8fc2f41c1adeda_85.png)

Oh sorry， sorry here it shouldn't work yet because it's not trained。 That's what we'll do next。

 and then you should compare。

![](img/9bb0a661f5d036c51a8fc2f41c1adeda_87.png)

Okay。

![](img/9bb0a661f5d036c51a8fc2f41c1adeda_89.png)

One way to optimize this model is to optimize those representations using stochastic gradient descent。

So the stochasticity comes from like sampling one triple of movie user rating。If at each step。嗯。

Or in this case， cycling through it in e box。And then。You knowOnce you sampled one of these terms。

 you compute the gradient and take a small gradient step on M and on U of that particular entry we sampled。

And that's what you' optimize here。

![](img/9bb0a661f5d036c51a8fc2f41c1adeda_91.png)

And。To check if you did well， you should expect the test error to go down below 1。0。

 that's slightly better than the other models。

![](img/9bb0a661f5d036c51a8fc2f41c1adeda_93.png)

O， because this is toastic gradientding descent。 the results can be quite sensitive to the learning rate you used。



![](img/9bb0a661f5d036c51a8fc2f41c1adeda_95.png)

And the weight decay parameters。

![](img/9bb0a661f5d036c51a8fc2f41c1adeda_97.png)

诶。

![](img/9bb0a661f5d036c51a8fc2f41c1adeda_99.png)

So I forgot to talk about weight decay。Wt decay means。Will add it and。you've seen this before。

 Its the same as L2 regularization。 And it means we would like。The。

 the representation is M and U to remain small。 So we add a lost term。That is。You know。

 squared entries of M。And square entries of U weighted by a regularizer term。

I'll update this in the notebook。 So you have it written out here。



![](img/9bb0a661f5d036c51a8fc2f41c1adeda_101.png)

嗯。

![](img/9bb0a661f5d036c51a8fc2f41c1adeda_103.png)

Okay， so。Another way to optimize this is using alternating list squares。And here。

 instead of stochically sampling triple's movie user rating。What we'll do is。

Fix all the user representations。And if you do that， if you fix those。

 then optimizing for M is just a quadratic problem and which we can exactly solve。

And if you on the other hand， keep all the movie representations fixed。

 we can optimize all the user representations， then this is just a quadratic problem。就。

That's and the alternating part of this is that will go iteratively between the two。

 so you fix the user representations and then perfectly optimize the movie representations and then in the next step you fix the movie representations and perfectly optimize the user representations。

And then you go back and forth between those。

![](img/9bb0a661f5d036c51a8fc2f41c1adeda_105.png)

So。We expect this to give the best results。And it's not that you couldn't get this with HGT。

 but it's just a bit more tricky to tune if you use the default parameters we gave here。



![](img/9bb0a661f5d036c51a8fc2f41c1adeda_107.png)

![](img/9bb0a661f5d036c51a8fc2f41c1adeda_108.png)

This should work better。Okay。Good luck with this。 And let us know if you have any questions on the form。



![](img/9bb0a661f5d036c51a8fc2f41c1adeda_110.png)