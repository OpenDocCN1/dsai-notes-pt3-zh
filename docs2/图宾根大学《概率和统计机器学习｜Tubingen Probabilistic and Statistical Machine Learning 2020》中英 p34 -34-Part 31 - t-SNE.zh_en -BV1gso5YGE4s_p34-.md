# 图宾根大学《概率和统计机器学习｜Tubingen Probabilistic and Statistical Machine Learning 2020》中英 p34 -34-Part 31 - t-SNE.zh_en -BV1gso5YGE4s_p34-

Today I want to talk about yet another algorithm for dimensionality reduction or data visualization。

 namely I want to talk about TN。😊，So far， we've already seen quite a number of algorithms that all take some data and either reduce the dimensionality or embedded into a Euclidean space in order to keep certain properties of the data intact。

 but maybe give up on other properties We have， for example。

 seen that principal component analysis is a technique that tries to achieve and embedding where the variance of the data is still as large as possible。

 so we only get rid of some dimensions where the variance is low hopefully it' just consists of noise where some other dimensions。

 the meaningful ones are being kept intact。 We also looked at multidimensional scaling where the main goal is to achieve that the distances between data points are kept more or less as they have been before but the measurement is taken on average。

 so on average we can make some statements about when multidimensional scaling is going to work。

We have also seen random projections where we measure the error。Of the embedding method point。

 whereas we we want to give give guarantees that can say for any pair of points。

 the distance did not increase or decrease by more than a factor one plus epsilon or1 minus epsilon。

And lastly， we've also looked at methods for manifold recovery。

 where the assumption is the data list on a low dimensional manifold。

 and the idea of the embedding is to unfold this manifold and and sort of。😊。

Keep the distance structure as it is given in the manifold distance intact。 but， of course。

 get rid of some dimensions， which are just due to the fact that this manifold was embedded in some large dimensional ambient space。

And now comes Tsney， which is yet another algorithm for a completely different purpose。

 The idea of Tney is not so much to recover manifold structure or so。

 but the idea of Tney is to recover cluster structure in your data。 So the overall goal is you。

 you want to find an embedding。Such that if your data has a nice cluster structure。

 the embedding brings out the cluster structure。😊，And what we are going to see is that this。

That TN is an algorithm that can do that up to a certain point。

 but that also means that we need to give up on many of the other geometric limitations or like geometric settings that we have in our original data。

There's lots of literature on Tsney， of course， here。 I just mentioned a couple of them。

 The original paper for the algorithm and by Fundnda Martin and Hinton was in 2008 in JMR visualizing data using T。

 There's a very nice online tutorial in distill from 2016。😊。

Where and I took some figures also from this online tutorial。

 then there's a reasonably new paper last year by some colleagues of mine。

 Mitri Kobeach and Philip parents who looked at how can you use T really in practice what are sort of good ways to use this algorithm and then there's also theoretical analysis which is cited down here which I'm going to mention in a couple of slides later。

😊。

![](img/af37889c17f4f79cfc811a6f9d7582bd_1.png)

So let's start TN is a funny name for an algorithm， it is really pronounced TN and not T as an E。😊。



![](img/af37889c17f4f79cfc811a6f9d7582bd_3.png)

And it's an abbreviation that stands for tea stochastic neighborhood embedding。



![](img/af37889c17f4f79cfc811a6f9d7582bd_5.png)

![](img/af37889c17f4f79cfc811a6f9d7582bd_6.png)

As it's written here on this slide it's a method for no nonlineardiality reduction or embedding and typically it is used for data visualization or for data exploration。

 so it's not so much a method that you would use if you want to preprocess your data and later on user a classification algorithm this is typically not very successful by using TN because lots of the global geometry of your data is being destroyed by this kind of embedding。

😊。

![](img/af37889c17f4f79cfc811a6f9d7582bd_8.png)

![](img/af37889c17f4f79cfc811a6f9d7582bd_9.png)

![](img/af37889c17f4f79cfc811a6f9d7582bd_10.png)

![](img/af37889c17f4f79cfc811a6f9d7582bd_11.png)

But for visualization purposes， it's often used and it's in fact very widely used in practice。😊。



![](img/af37889c17f4f79cfc811a6f9d7582bd_13.png)

![](img/af37889c17f4f79cfc811a6f9d7582bd_14.png)

And the idea is what we can see here I just took an example figure here from the paper by Ko imbalance how a typical Tney embedding might look like。

 so you see here there are a number of clusters in this data structure and the color code in this particular figure is by some ground truth so assume this is maybe biological data I don't really know you produce an embedding by TN and then you color the points according to classes that you might already know different types of proteins or different types of retina cells or I don't know and then what you can see here is often figures like this where the color code this roughly corresponds to the clusters that have been plotted by your algorithm。

😊。

![](img/af37889c17f4f79cfc811a6f9d7582bd_16.png)

![](img/af37889c17f4f79cfc811a6f9d7582bd_17.png)

![](img/af37889c17f4f79cfc811a6f9d7582bd_18.png)

![](img/af37889c17f4f79cfc811a6f9d7582bd_19.png)

![](img/af37889c17f4f79cfc811a6f9d7582bd_20.png)

And the idea is now if you have an algorithm that can do that you can really use it for data visualization and also human data exploration。

 so as an expert you can now look at this figure you might be like if you have a nice toolbox you can zoom in and zoom out and try to really see structure in your data that you perhaps might not have been aware about without this embedding。

😊。

![](img/af37889c17f4f79cfc811a6f9d7582bd_22.png)

So here is the general hope It brings out the cluster structure much much better than many of the other methods for lower dimensional embedding and here is just a simple comparison。

 for example， that is also taken from the K balance paper。😊。

Here is in figure A on the left hand side， we have an embedding of some data based on multidimensional scaling in the middle we have an embedding based on PCA。

😊，And on the right hand side we see an embedding by the Tney algorithm and you can see that essentially figures A and B do not represent the cluster structure。

 which might not be too surprising because this is not what the algorithms have been designed for whereas TsY。

😊，I think one cannot say it has been designed for this purpose。

 but it turns out that it's good for this particular purpose， at least that's the story。

 So Tney is really an algorithm that brings out the cluster structure as you can see here on the right hand。

😊，I already added a note of caution here at the beginning。

 So the hope is it brings out the cluster structure and the question in parentheesis at the cost of what。

😊，Because typically if you a teasN embedding is a very strong distortion of your dataset and we are going to discuss it later and this distortion also destroys many of the other properties of your dataset and you always need to be aware that while it maybe produces some cluster structure that might be true or might not be true。

 there are many other things about your dataset that definitely get lost when you do a TeN embedding。

 we are going to discuss it in a minute。So what is the general idea of this algorithm， It'， in fact。

 a surprisingly simple idea。😊，So we start in a high dimensional space， we have points in RD。😊。

D typically being a high dimension。And we typically also embed in R2 because TN is really an algorithm mu to visualization。

 so you don't embed in R5 or anything you embed in R2， you generate a map of your data。😊，Now。

 the way this proceeds is as follows。On the input space you define a similarity function that is a function it's an nonsosymmetric function called PIJ。

 so for each fixed data point I you define this function PIJ which tells you how similar is every other data point to yourself。

This is essentially as we're going to see a Gaussian kernel。😊。

Where the current limit is being chosen for each data point individually in some particular way。

These similarities PI J all normalized for each， so it' is not the metric so I fixed data point A I compute the similarities to everybody else。

 I normalize them to have some one so I want to have a probability distribution here。😊。

Now this is what I do on my input space and now in the output space I compute essentially similar things so I again if I have a setting of points which is my current embedding。

 I again compute a similarity between the points in a similar fashion as in the input space but I use a different function and I'm going to discuss it later。

 the function that is used to compute a similarity in the output space is a heavy t distribution。😊。

This T is also the letter。Which entered the name T S。

so you have your input space and you record what are is the similarity structure and your input space。

 you have a way to measure the similarity structure and the output space according to Q and now you want to match those as closely as possible and now what is being done in this particular algorithm is you consider thequi black light that divergence between these two probability distributions and this is what you' are going to minimize over your whole space and typically use some kind of gradient descent then you output the result of this gradient descent as your embedding。

😊，Now， how are these similarities being measured in the input space we really do the naive thing we use a Gauss kernel。

😊，So to define the similarity between a point I and all its other points J。

 we essentially compute Gaussian kernel between Xi and Xj。😊，With a certain kernel with sigma squared。

And the denominatorator is just to normalize everything to have weight one。Observe that in the end。

 this is not symmetric because this normalization constant depends on the data point Xi。😊。

So the nominization is different for I than for J。 So P I J is typically not the same as P J I。

 but that doesn't matter。 So we have this non symmetric way of measuring the similarities。Now。

 the point is a really important point is how do we choose this parameter sigma in the Gaus can can。

And the trick is what we're going to do is we fix the sigma individually for each data point and now if you think back about the discussions at the very beginning of the lectures when we said how should we choose the width of a kernel and in particular if the Gaussian kernel I've often made these plots where you say。

 you know I mean we have the data point on this is the Gaussian centered on this particular data point and now you want to choose the width such that like the local neighborhood has a reasonable high similarity to this data point and everybody else has a reasonably low similarity and then I always said the local neighborhood is something like like if you have a k nearest neighbor classifier。

 you would maybe choose the parameter K on the order of lock n also and you should choose your kernel width is in a similar way such that approximately log n of your data points reasonably similar to your point that you're currently considering and everybody else might be dissimilar。

😊，And here we do exactly the same so what happens is we will see it in a couple of slides it's a bit different but intuitively what we do is we fix a parameter k and say we choose the width of this Gaussian on data point I in such a way that the K closest neighbors in our data are reasonably similar。

😊，And by by choosing Sigma， we can achieve that because depending on the local density of our data。

 there might be a part of the data where where the data points are really very dense。

 then you might choose sigma smaller and then there is some other part of the data space where the data is very loosely distributed and then you might want to choose sigma larger。

Now here is how it is measured so people do not talk about the number of neighbors。

 they talk about what is called perplexity and in some sense perplexities。

 it is the way I understand it just some kind of continuous way of measuring the number of neighbors and I am a bit unhappy about this but maybe this perplexity comes from a different intuition and from a different field of research where people have like an intuitive meaning for what perplexity is。

 I don't have that but here is how it works。😊，嗯。So。

We fix a value of publicity in the beginning and say like for me。

 my intuition is you fix the number of neighbors and say 10。

 so you want to be similar to 10 neighbors。😊，So this is a global parameter that you fix for every data point that's in your space you want that the parameter sigma has chosen such that the data point is similar to its 10 nearest neighbors。

 for example。😊，And now how do you compute that now in practice？😊。

What you know is and you fix a value of sigma， so you fix first of all。

 the data point and for this data point I， you now want to find out what is the value value sigma I that you are supposed to use。

😊，So you start with some value of sigma。Now what you do is you compute the entropy of the current distribution of these similarity values PI J with this particular value of sigma。



![](img/af37889c17f4f79cfc811a6f9d7582bd_24.png)

And the entropy of a probability distribution is just this term。

 like you have a discrete distribution there are just finite many points。

 so you have sum of all these points， the value of the probability times lock of the probability。😊。



![](img/af37889c17f4f79cfc811a6f9d7582bd_26.png)

Okay so this is the typical formula for entropy if you haven't seen that before don't worry it's just a formula。

 if you have seen it it' is the standard formula of the entropy。😊。

Now what you do is you compute what is called the perplexity， which is2 to the power of this entropy。

😊，And now you choose a parameter， okay， and you can do this for different like you fix the data point I and you now can compute this for different values of sigma。

😊，And now you want to choose the parameter sigma of the Gauscon such that the perity matches your specified value。

And now you need to play with a parameter sigma， you might decrease it or increase it and this is typically reasonably easy because you can simply do it by binary search because it's perplexity and depends monotonically on sigma so you first choose a sigma which is much too small then you try to find a sigma which is much too large and then you sort of do binary search and you zoom into where your value of sigma is for this particular data point。

😊，So this is just how it's done。 But like the bottom line for myself is you do exactly what you're supposed to do when you set aous in kernel to the kernel width。

 then you choose the kernel width in such a way that each point is similar to。



![](img/af37889c17f4f79cfc811a6f9d7582bd_28.png)

A number of key nearest neighbors。

![](img/af37889c17f4f79cfc811a6f9d7582bd_30.png)

So now we've defined the similarity in the input space， what do we do in the output space？

There was an earlier version of the algorithm where people in the output space also simply used the Gaussian kernel now without any sigma because we want to get rid of this sort of scaling issue in the end we might want to have that the points have the same kind of density in the space and not like low density here and high density here so we sort of would say we can forget about this parameter sigma it would be the same for everybody。

And then wed simply use a cow scan。As the similarity function normalize it， however。

 this didn't work so well。 This was the first algorithm that they invented。

 It was called S& E stochastic neighborhoodhood embedding。

And then they realized that it's much better to use a more robust version and whenever you hear the word robust and statistic。

 it always means you need to have a heavy tail， which means that the data is not so much influenced by outlier points。



![](img/af37889c17f4f79cfc811a6f9d7582bd_32.png)

So what people did is instead of using a gaous distribution here， oh， in fact。

 there are minus signs missing here。 I'm sorry this is a typo。 I just take a note。



![](img/af37889c17f4f79cfc811a6f9d7582bd_34.png)

![](img/af37889c17f4f79cfc811a6f9d7582bd_35.png)

So it should be e to the minus the norm， of course。

And so what people now did is they use the t distribution instead of the Gaussian distribution and so the t distribution looks like this。

 so the similarity of data point I to data point a is now computed by this expression here。😊。



![](img/af37889c17f4f79cfc811a6f9d7582bd_37.png)

![](img/af37889c17f4f79cfc811a6f9d7582bd_38.png)

Which is the t distribution of one degree of freedom。



![](img/af37889c17f4f79cfc811a6f9d7582bd_40.png)

It's also the same as the the coursehy distribution。 If you have， if you know that。

There is no parameter， as I said， there is no kind of width parameter so because we want to have it equally spaced。

Okay， so now we have on our input space， we have the Gaussian similarity where we choose the kernel width at each particular data point in an appropriate way on the output space。

 we now have the t distribution and now we want to match the two。 so we we now。😊。



![](img/af37889c17f4f79cfc811a6f9d7582bd_42.png)

![](img/af37889c17f4f79cfc811a6f9d7582bd_43.png)

![](img/af37889c17f4f79cfc811a6f9d7582bd_44.png)

It's on the。

![](img/af37889c17f4f79cfc811a6f9d7582bd_46.png)

We， we now start with an initial distribution on the output space due to tune it such that it fits better and better the distribution of the of the similarity values gets closer and closer to what we've seen in the input space。



![](img/af37889c17f4f79cfc811a6f9d7582bd_48.png)

![](img/af37889c17f4f79cfc811a6f9d7582bd_49.png)

![](img/af37889c17f4f79cfc811a6f9d7582bd_50.png)

So given input sorry given the input similarities， the goal is to find an embedding point configuration in R2 such that the output similarities match the input similarities as well as possible。

😊，And the way we measure it is thequiulver light that divergs。 So the cost of an embedding。

s essentially we compute the Kba liveular divergence between like for each data point I。

 we compute this input the the input similarities P and the output similarities of the current point position Q I。

 we compute the K liveular divergence between the two and then we sum this overall data points。

 So this is really very straightforward pretty naive。😊，嗯。And if you write down the formula。

 that's it。This is now the cost function for each point configuration。

 we can compute this cost function， and now we can minimize this cost function by a gradient descent。

It is not a complexve cost function。 It is a very complicated cost function， but still。



![](img/af37889c17f4f79cfc811a6f9d7582bd_52.png)

We can simply try to do it。Now what is sort of the interpretation here。

 if you stare at this cost function for a while and I don't want to really go into the details here but you can look in the literature if you want。

 what happens is that you will incur large costs if you have points that are close in the input space but far in the output space so what you want to have is that if two points are in the same local neighborhood in the input space they should again be in the same local neighborhood in the output space。

But the other way around， you don't really care so much if you have points that are far in the input space。

 but close in the output space， you don't really care， at least not so much。😊。

So essentially it means if something is far in the input space。

 I don't have an opinion where they should be in the output space。

 but if two points are close in the input space， they also need to be close in the output space。

And I like for machine learning， this perfectly makes sense because you would say。

 at least if I mean， if you destroy the local neighborhoods， then all your information is gone。

 machine learning is very often about saying that similar input should lead to similar output。

 So if you have points which are close by in a classification scenario。

 they should also get the same label。 So if I destroy this。

This notion of being close by by my embedding， then it's very likely that in the end。

 I destroyed all the information that's in my data。Now this high level interpretation is nice。

 you can also look at it more closely and you can compute the gradient。😊，It is surprisingly simple。

 you can compute the gradient of the schoolLila divergence and you can sort of split it into different terms。

 and I don't have them on my slide， but if you won't look at some of the papers that I've mentioned。

😊，And then what you can see is that this gradient consists of two， always a sum of two two terms。

 one term that corresponds to attractive forces and one that corresponds to repulsive forces。

Now there are all these embedding algorithms， which are called spring embedding algorithms。

 where you the intuition is you have your original data set。

And for you have these little springs like between each of the data points， you have a little spring。

And now the embedding is sort of a distortion where you try to arrange two points in a different way。

 so if you try to pull apart like if here we have two points and there is a short string attached between them and I want to embed them and they would end up here。

 the string would pull these two points back together because they belong together。

And you might also have repulsive springs， which are sort of like if you have points here which are far apart。

 then maybe you might have a repulsive spring here that at least exerts a certain repelles and such that these points don't necessarily end up on the same spot。

And this is there is a huge glass of algorithms embedded called spring embedding algorithms。

 in particular in the field of graph drawing， for example。😊。

And you can interpret these in some way such a system。 So in the end。

 what you will see if you look at this gradient， all points are repelleed from each other by standard。

😊，But then points that are neighbors of each other， they are also being attracted to each other。

And now the final point configuration that you find is， of course。

 sort of a balance that brings all of them into some stable position。O。Now here。

 Tesney can be really， really cool and this is why it is so widely used in practice。 I mean。

 people have simply observed that in many cases， if you do Tesney embeddings，😊。

The cluster structure that you see in the embedding is very meaningful with respect to some ground truth clustering that you might have in your data。

 And here I have one particular example which is taken from the Lindaman paper。

 This is a theoretical paper。 and they just in the introduction， they present this example。

Here is the Tney output for some particular dataset set I forgot what it is about so this is what TsN produces and now if you color code your data according to some now known ground truth structures so for example these are cells and you know the types of these cells and you assign different colors to different types of cells to see that this Tney plot very nicely separates at least some aspects so we have lots of like the green points are more or less here here if orange points。

 blue points， red points and then this white gray area which contains points of all colors which is sort of a bit funny but at least we see that there are big parts of the clusters which seem pretty homogeneous with respect to the color。

😊，So it seems that Disney has discovered some structure that is meaningful at least in this dataset set。

😊，And these plots often look really cool。 And I think really this is one of the main motivations from or this is maybe a bit too negative。

 but a big motivation is that if you write a paper and these tea plots they are often very beautiful so people like these plots and they often confirm what they think should be in the data and this is why it's used so often。

😊，No， there are theoretical results which say that at least under certain circumstances。

 TsN really happens like you can prove that TsN。😊。

![](img/af37889c17f4f79cfc811a6f9d7582bd_54.png)

Shows or brings out the cluster structure in the data。



![](img/af37889c17f4f79cfc811a6f9d7582bd_56.png)

This is funny because there was a work by Lindaman and they had put their results in archive and then San Aurora and some colleagues took it in the same year and brought and sort of developed the results further。

 and I think Lindaman had presented them in a somewhat more moderate fashion and Aurora said Tesney is really I mean。

 in this paper it sort of made the final conclusion that I think Lindaman also wanted to make。

 but didn't put so strongly and this was published and called at the same time。

 And how Lindaman's original paper was published a bit later， I think last year at some point。



![](img/af37889c17f4f79cfc811a6f9d7582bd_58.png)

![](img/af37889c17f4f79cfc811a6f9d7582bd_59.png)

So here is just but just to see where this is heading to。

 here's one result that's taken from the Aurora paper from the cult paper。😊。

And it's an informal version， but essentially it says something like this。

 assume you have some points in your high dimension space。😊。

And assume these points are gammapherically and gamma well separated clusterable data。

 So of course you need to define now what does it mean that a dataset set contains cluster structure and they come up with a definition they said it's gamaspherical and gamma well separated so spherically means clusters are roughly round sets you can sort of encapsulate them in a sphere and well separated means that the clusters don't overlap but you have a cluster here and the cluster here and there's a separation and the width of the separation is quantified by some parameter in some way in this parameter gamma。



![](img/af37889c17f4f79cfc811a6f9d7582bd_61.png)

So they say， assume we have a data set that really consists of K nicely separated round ground twoth clusters。

Then if you use Tney with early exaggeration， this is now a particular technique related to Tney。

Then its outputs a full visualization of x with high probability where this full visualization。

 you would need to look it up again and the paper means essentially that it shows the correct cluster structure。

😊。

![](img/af37889c17f4f79cfc811a6f9d7582bd_63.png)

Okay， and this is one of the theorems that says at least if there's a very clear ground truth cluster structure in the in your data and you apply a vanilla version of。

 of T， then you will see these clusters also in the output space。



![](img/af37889c17f4f79cfc811a6f9d7582bd_65.png)

Now， as I said this teaney can be really cool， but the thing that is maybe not so cool about Tney is that the result and the output of Tney really。

 really， really depends a lot on the parameters and there are many parameters in the algorithm and I simply want to highlight a bit of it during the next couple of slides if you want to understand it more you really need to to read the literature this is just to give a bit of an outline。

😊，So the first thing I want to show is。Here is a figure that is again taken from Kobar and parents where they in in this paper。

 essentially they give some guidelines on how to use T to really produce good results that sort of match certain ground truth。

😊，And here they take an example， so this is a Tney plot that has been published in an earlier paper。

😊，I forgot what it is about but this is sort of the original Tney plotot that you get。

 It already looks very nice。 And now they say look we find a different parameter setting for which we find for which we really get a much better separation already so and here you can see the matching。

 So here for example， cluster 1 I think you have maybe these are cells also I don't really know and then you have here the type1 cells and here again in this new plot your also have T 1 cells。

 but for example， the type 20 cells are very nicely separated。

 The type 29 cells are very nicely separated and so on。😊，And essentially。

 the main message of the paper is if you have a careful choice of parameters。

 then you can produce even better tea leaf plots。😊。

So what what this shows is these are just for two different settings of parameters。

 so you can really produce widely different plots just by playing with the parameters of Tsney。😊。

Heres yet another figure。😊，Again， what they did it's always the same kind of data here it's a genomics dataset and now you can apply a different variance of TI and I don't even want to go into all the details。

 but here you have like you have five different figures ABC DE each of them looking at the different variant of TN so here for example you have a different number of data points so between the left and at the right hand now you have here and see it's a plot without early exaggeration。

 this is a technique that's often used regarding to the。😊，To the optimization procedure indeed D。

 you have it without downse， whereas in some other plot。

 it's with down sampling And you have the default， T parameters and so on。

 And if you're interested you can look into the paper and really read more about the details。

 my point here is just。😊，You achieve different resultss with Tsney by playing with the parameters。

And now I want to show you how this really works。 and to this。

 I refer to this distilled paper from 2016 by Woten Dark I。Who really brought this out very clearly。

 And I encourage you to also look at this one because this is really very simple。

 And many of these plots are now taken from this particular paper。

So what we see here is and we have an original data set consisting just of two mixtures of Gausss。

 I guess， or two。😊，Point clouds if you want。 So this is the original data。 It lives already in R 2。

 and now we want to again em it using Tesney into R 2。

 and then we can always compare like does the Tney embedding really produce the same result as our original data。

Now what we can see here in this top row。😊，They essentially always applied the same algorithm but with different parameters of this perplexity and this perplexity。

 if you remember， it is the number of neighbors that we consider similar and what we can see here is the perplexity on sorry on this first so on the very left is the original data and then the next5 or6 tables show different embeddings for different values of perplexity here we have perplexity2。

5， 30， 50 and 100。😊，I guess there's 100 data points。

Now what you see is depending on this value of the perplexity。

 you get very different results here if you have very very very small perplexity too that's maybe two I mean I would also say like if you a canous neighbor algorithm with cake was two that's maybe a bit not enough so what then is going to happen is you have too many replisive forces and you don't have enough attractive forces so essentially the data gets all mixed up。

😊，And scrambled over the space then for perplexity 5 and 30 and 50。

 I would say you get somehow reasonable embeddings and they show the cluster structure that you are supposed to see and once the perplexity is too high。

 then everything gets mapped on top of each other because essentially you say everybody is similar to everybody else and you lose the structure completely。

Okay。So maybe it I don't find it so surprising that the results of T are really sensitive to the parameter of the perplexity because this is similar to the parameter K in K nearest neighbor classification or embedding or also if you use a K nearest Ne graph for isOm。

 that's also sort of sensitive to this。But now there are many more parameters。

 for example typically people use early stopping in the gradient decent algorithm when they when they embed with Tney so here in the bottom row everything has been kept similar so perplexities over 30 for example。

 but now they use different early stopping rules once they stop after 10 steps after 20 after 60 after 120 and 1000 steps。

And what you see is here again， you get quite different results。 I mean， in in this particular case。

 in many of these， in many of these plots， the cluster structure gets。At least it gets identified。

 but still these plots look very different from each other。And in particular， for example。

 here you have essentially two very dense clusters which are very far from each other。

 here you have two clusters which are not so dense and very close to each other。😊。

And this already shows a message that we are also going to see on the next couple of slides that like distances in teasney plots are really something you cannot rely on at all。

 Disance information is being lost completely in a Tney embedding。

So what the point I want to make now is that the choice of parameters is really crucial and there are here I just listed a couple of parameters and heuristics that are being used。

 so the initialization of the algorithm is really really important because the global layout of I mean。

 it it's a gradient descent algorithm so you start with some initial point configuration and then use a gradient descent。

 So if your initial point configuration is something completely random it might be really difficult because essentially you're going to end up in a local optimum。

😊，And it might， might be problematic within a couple within a few gradient de steps to sort of rearrange a whole global geometry of data points。

So typically what people do is as an initialization。

 they already use something that is at least somehow meaningful， for example。

 a PCA embedding or an MDS embedding of your dataset sets。😊。

And the algorithm is really very sensitive to what kind of initialization you use。

Then there's of course this perplexity parameter as I said。

 and then there are millions of more parameters that are all related to different heuristics that are being used in the gradient descent。

 so there's a learning rate。 So the step size in the gradient descent there is early stopping that's used a lot a lot。

 then there is a technique called early exaggeration and I don't even want to go into it there is momentum there there are many。

 many techniques that are being used and whenever use one of these techniques。

 your result are going to look very different from other results。😊，嗯。

And the important point here is you really need to be careful when interpreting plots that are being generated with teasney。

And this is the headline of my slides， and this is really important to me that you remember this。😊。

And there are a couple of things that you really need to be careful about。

 So cluster sizes in teas these plots don't mean anything。

 if there is a small cluster or a large cluster， you cannot trust this at all and let me maybe go back for example。

 yes to this figure here。 So here we have some large clusters and some small clusters。😊。

And there is no truth in these sizes of the clusters you can have very large clusters in the original space that end up as being small clusters in embedding in the other way around so you cannot like by just looking at a figure you cannot say oh here's a large cluster and here's a small cluster for example this green one looks reasonably large and maybe this pink one is reasonably small but then here' is another cluster outside here which is really really small but this is completely meaningless。

 you cannot trust this and let me show you why。😊，Here's an example that's， again。

 from this tool paperper。So here we have here we have the original data set it consists of two clusters。

 the blue cluster here which has a pretty large variance and the orange cluster it's a bit hard to see maybe on the slide which has a very。

 very low variance， the same number of points。😊，Now again。

 we see different embeddings with different parameters of perplexity。😊，And what we see here is。

 I mean just compare the size of the orange and blue clusters and you will see that in many of these cases。

 essentially all the clusters they seem to have the same size。😊。

And somehow it's also clear where this comes where this comes from。

 because remember in the input space， what we did when we assigned the similarity function。😊。

We tuned the parameter sigma to have to include sort of the same like the 10 nearest neighbors for example。

 and we did this on purpose in such a way that if the data points are very loosely distributed here。

 then maybe sigma should be large so that we contain 110 data points in the nearest neighborhood and here if the data points are very densely together then sigma is smaller but we choose it again in such a way that the closest 10 data points are significant。

😊，And in the output space， we do not have any scale。 So essentially。

 if there is a space in like in our input space， there's a region which is very dense。

 we sort of maybe inflated a bit in our output space。 And if in the input space。

 there is a region that is very loosely populated， we might decrease it a bit in the output space。

 So in the end that the distances between nearest neighbors are roughly the same。😊，嗯。But this。

 on the other hand， it means that if a cluster is large or small， you cannot。

 it doesn't mean anything regarding the the size of the cluster in the input space。

The other thing that I find much more important， even is。😊。

The distances between the clusters in your output space typically do not mean nothing。

So the relative position of the clusters with respect to each other is arbitrary。

And this is something that I think is even more misleading than the previous point we had。

 So consider just this case。 We have here an original data set where the blue and orange cluster are very close together。

 And then we have a green cluster， which is far away。

 And now look at all these different teas embeddings。 So in most of these embeddings。

 you don't see any difference here between the distances here， maybe in the last couple of points。

 you see a distance。 But here， the perplexity is 50 or 100 is probably already too large。😊。

So in all these kind of embeddings。😊，You do not see the structure。

 you do not see the correct distances。And this is now here in the first row。

 the perplexity growth and the step number of steps was held constant。Here， in the second。

In the second row， what's another different。嗯。In fact。

 I don't know because it's the same kind of parameters。

 maybe it's just a different initialization of of the of the algorithm。 So again。

 what we see here is sorry I forgot what is the difference between the first and the second row。

 but the main message is in in the second row row even more more pronounced that the distance is between the cluster that in the end。

And the Tney embeddings do not match the distances in the input space。

And now let me go back to what this really means。 So if I now have a teasney embedding like this guy here。

Typically as a human， you look at this embedding and you say， oh， here。

 this light blue cluster and the dark green cluster here they are very close。

 but now I have this neural crest cluster here， the pink cluster 24 that's at the other side of my plot。

 So this must be something completely different。 So so when I as a human interpret this plot。

 I say light blue and light and dark green。 So cluster 20 and 29。

 a sort of similar verse 24 is very far away。😊，And this is wrong。

 You simply cannot conclude anything from this kind of from the information between the clusters。

And this is something that I find pretty problematic because I think most people who use T as a toolbox they don't know about this and of course as a human I look at this figure。

 so what else should I do， I mean this is sort of the kind of way I use like if I explore some data of course what do you do。

 you have your map of your data and you try to see what is close to each other and what is far from each other。

😊，And this is nothing that we can trust， trust in a teas nuot。



![](img/af37889c17f4f79cfc811a6f9d7582bd_67.png)

Okay then the third thing that is being mentioned， I think that something that happens in many algorithms。

 but still it also happens here。 random noise doesn't always look random。

 So what we have here is just a random point cloud there is no structure no cluster structure。

 whatever。😊。

![](img/af37889c17f4f79cfc811a6f9d7582bd_69.png)

![](img/af37889c17f4f79cfc811a6f9d7582bd_70.png)

![](img/af37889c17f4f79cfc811a6f9d7582bd_71.png)

Now we do an embedding and of course， like with a low perplexity here。😊。

And all of a sudden you see it seems like there are clusters emerging。

 but of course this data set doesn't contain any clusters， it's just random noise。

 but you see random clusters emerging。😊。

![](img/af37889c17f4f79cfc811a6f9d7582bd_73.png)

![](img/af37889c17f4f79cfc811a6f9d7582bd_74.png)

![](img/af37889c17f4f79cfc811a6f9d7582bd_75.png)

So。Not not everything that you see that looks like a class really is a class semi ground truth。



![](img/af37889c17f4f79cfc811a6f9d7582bd_77.png)

Again， this is something that happens also for many of the other methods and if you plot a random graph or like a random can you snaper graph。

 you will see similar things。😊。

![](img/af37889c17f4f79cfc811a6f9d7582bd_79.png)

![](img/af37889c17f4f79cfc811a6f9d7582bd_80.png)

But it's something to be aware of。

![](img/af37889c17f4f79cfc811a6f9d7582bd_82.png)

The next thing is about preserving topology。😊。

![](img/af37889c17f4f79cfc811a6f9d7582bd_84.png)

And so there is now， depending on the papers， you read some papers say， oh。

 but I find a parameter setting that does preserve the the topology others say， well。

 it does not preserve the topology。 Heres an example。

 So here we have a point cloud that consists of a small blue cluster in the middle and lots of orange points round the middle。



![](img/af37889c17f4f79cfc811a6f9d7582bd_86.png)

Now we see different T embeddings for different perplexity values， so here for perplexity 2 and5。

 the topology is not preserved at all。😊，Pplexity 30 up to a certain point already preserved the topology 50100 so so towards the end the topology is preserved a bit more even though again here like for perplexity 100 it looks I mean here in the original image it's not like an orange ring and then a large distance in a blue point as it as we have it here。

 but here it's sort of a orange point cloud and in the middle there's a blue point。



![](img/af37889c17f4f79cfc811a6f9d7582bd_88.png)

![](img/af37889c17f4f79cfc811a6f9d7582bd_89.png)

![](img/af37889c17f4f79cfc811a6f9d7582bd_90.png)

![](img/af37889c17f4f79cfc811a6f9d7582bd_91.png)

嗯。So maybe so essentially none of these figures also really brings out this topology。

 but maybe they bring it out a bit。So what I mean with the slide it says it might or might not preserve topology。

 so if you're lucky it does。😊。

![](img/af37889c17f4f79cfc811a6f9d7582bd_93.png)

And and observe like topology from a mathematical point of view always talks just about the global layout。

 but not about distances。 So topology is just something is inside or something is outside or or some sets intersect or they don't intersect。

😊。

![](img/af37889c17f4f79cfc811a6f9d7582bd_95.png)

![](img/af37889c17f4f79cfc811a6f9d7582bd_96.png)

![](img/af37889c17f4f79cfc811a6f9d7582bd_97.png)

But distances are sort of meaningless。So if you're lucky， your tea might preserve some topology。

 if you're unlucky， it does not。 definitely， it is nothing you can trust。

 So if you see a data set and you see a particular topology。

 you can never conclude that this is really the topology of your dataset。😊。



![](img/af37889c17f4f79cfc811a6f9d7582bd_99.png)

![](img/af37889c17f4f79cfc811a6f9d7582bd_100.png)

![](img/af37889c17f4f79cfc811a6f9d7582bd_101.png)

So， let me summarize。Tisney is an algorithm that is very， very widely used。

 and I think one of the reason is because you really produce very nice plots。 They look nice。

 but apparently they also help people to explore their data， at least in certain circumstances。😊。

From my point of view， it is really， I mean， not just from my point of view。

 this is what everybody reports is that this algorithm is really sensible to the choice of parameters。

So so far， I think everybody agrees for myself， my interpretation， if I read something like this is。

😊，I'm always very， very careful with these algorithms because it means， I mean。

 what do you do in practice。 You know， the results are very different if you choose different parameters。

 So you play a lot， you choose perplexity。 You choose exaggeration。 use momentum。 you don't use it。

 So so there are millions of choices。 and you will sit。 and it's a visualization thing。

 So you have your toolbox。 There are lots of buttons by which you can sort of tune your parameters。

 So you will sit in front of for your screen for a couple of hours。

 play with your data set and try to find parameters。😊，Now。

 how are you going to determine whether a parameter setting is okay。

 You will determine this parameter setting if you say this is roughly how I would expect my dataset set to be。

 So maybe there is something you already know about your dataset because you're a biologist and you already know there are certain classes of proteins。

 for example， and if you see these classes then you might be happy。

But what does it mean on a high level， It means you tune the parameters so long until you see the result that you expect internally to see。

 So you have a prejudice what your dataset set is about。

 You have millions of parameters to tune and you tune them so long until you see exactly what you hope to see。

😊，And this you see already that this might be problematic。 I mean， in some sense， in some cases。

 it might help。But there might also some cases where you produce complete bullit because what you think the data is is maybe not what is in the data。

 but because you have so many different choices of parameters you might even be able to recover what you think is your data。

😊，Even though for some other parameter choices， you get something completely different。

And so it is really， really difficult to interpret Tney plots。 They are very beautiful。😊。

But you cannot rely on distances， you cannot rely on topology。

 you cannot really rely on sizes of cluster。 So essentially whatever you look at as a human。

 you can't really rely on。So， I mean， okay， I'm a theoretician。

 I it's not my daily work to produce such plots and explore data。

 And apparently people who use like who work in data exploration in their particular field find Disney plots helpful。

 but I am very， very careful about it。 And my personal bottom line is not the following。😊，So。

If you like use TN， it might reveal things in your data you don't know and this is what explorative data analysis is about Explorative data analysis is you want to explore your data and come up with new insights into your data and what is a new insight from from a scientific point of view an insight is a hypothesis。

So the hypothesis might be O， here's a group of proteins that I didn't know about。

 or the inside might be O， here's this group of proteins。 I know this group already。

 but there are now two other proteins that are in this group that I didn't know should be in this group。

😊，And now you can form a hypothesis and this is now a scientific approach。

 you now produce a hypothesis that says these two proteins belong to the same group of proteins。

 maybe you can argue about the function of these proteins and so on。😊。

So data exploration is about formula formula finding hypothesisthees。

 but now you must do the second step and try to verify this or fal this hypothesis in a scientific manner without looking at a plot。

 So now you need to come up with an experiment that can test your hypothesis and then see whether it's still true or not。

And my point is that。Apparently， T helps people to find this hypothesis。😊。

But you always need to test them independently。 You can never trust。

 like if a paper says or here are these plots。 And now my finding is that there are two clusters in the data。

 you simply cannot trust it unless people did an external verification of falsification of the hypothesis。

So in this sense， you really need to follow the。Good scientific practice of coming up with a hypothesis。

 but then testing your hypothesis and testing it strongly。

 always with the potential outcome that the hypothesis is wrong。😊。

And this is what I also wrote here on the slides。😊。

When your explorative data analysis has suggested some new insights。

 then go and validate your insights independently， meaning not with another visualization tool。

 but in some different way。😊，Never trust a paper that presents a teaney plot as the final evidence。

 It is a step on the way， or it can be a step， but it is never the end。

 You always need to have this validation at the end。

