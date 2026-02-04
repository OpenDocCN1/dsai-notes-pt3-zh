# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P114：25_高斯核支持向量机第1部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/b27423f2623e70674e059337c1b6dec8_0.png)

So now our goal here is to come up with a boundary that's going to separate out our pink dots that we have here from our blue values。



![](img/b27423f2623e70674e059337c1b6dec8_2.png)

And our first approach is going to be to create features from the ones that we already have。



![](img/b27423f2623e70674e059337c1b6dec8_4.png)

And this is something that we're familiar with， an example is when we create our polynomial features earlier in earlier courses。



![](img/b27423f2623e70674e059337c1b6dec8_6.png)

![](img/b27423f2623e70674e059337c1b6dec8_7.png)

We create from our original two features here， three additional features。 Hence。

 we have three more dimensions。

![](img/b27423f2623e70674e059337c1b6dec8_9.png)

Using budget squared ratings squared and budget times ratings。

 So rather than just having budget and ratings， we have these three additional features。

 These three additional features represent three national dimensions in our decision space。



![](img/b27423f2623e70674e059337c1b6dec8_11.png)

![](img/b27423f2623e70674e059337c1b6dec8_12.png)

![](img/b27423f2623e70674e059337c1b6dec8_13.png)

Now， another more sophisticated approach is to define similarity functions and then use those similarity functions to transform our space to higher dimensions。

 So how do we go about doing this。

![](img/b27423f2623e70674e059337c1b6dec8_15.png)

![](img/b27423f2623e70674e059337c1b6dec8_16.png)

![](img/b27423f2623e70674e059337c1b6dec8_17.png)

Here we're trying to identify the winners of the Top award at the Cans Film Festival using budget as well as IMDB ratings。



![](img/b27423f2623e70674e059337c1b6dec8_19.png)

And we can look to the particular movies in our data set and see the similarity to each one of our different movies。

 So our first function is going to define the similarity to pulp function。



![](img/b27423f2623e70674e059337c1b6dec8_21.png)

![](img/b27423f2623e70674e059337c1b6dec8_22.png)

![](img/b27423f2623e70674e059337c1b6dec8_23.png)

Then the next function will define the similarity to black swan。



![](img/b27423f2623e70674e059337c1b6dec8_25.png)

And then our third function that we'll have here will define the similarity to transformers。



![](img/b27423f2623e70674e059337c1b6dec8_27.png)

![](img/b27423f2623e70674e059337c1b6dec8_28.png)

So what does this similarity function look like？We'll look at each one of these movies。

 and then we're going to create a Gaussian function to define the similarity given our features。

 our features of another movie to this movie， how similar it is。



![](img/b27423f2623e70674e059337c1b6dec8_30.png)

![](img/b27423f2623e70674e059337c1b6dec8_31.png)

![](img/b27423f2623e70674e059337c1b6dec8_32.png)

So here we create a Gaussian function feature one here being pulp fiction。

 and we see the distance for each one of our different features。



![](img/b27423f2623e70674e059337c1b6dec8_34.png)

![](img/b27423f2623e70674e059337c1b6dec8_35.png)

Two the features for pulp fiction。

![](img/b27423f2623e70674e059337c1b6dec8_37.png)

We can then have another function for similarity to Black Swan， again。

 using this Gaussian function in order to come up with some similarity metric for all of our other movies to the Black Swan movie。



![](img/b27423f2623e70674e059337c1b6dec8_39.png)

![](img/b27423f2623e70674e059337c1b6dec8_40.png)

And finally， we can do the same thing for transformers for our third feature to come up with the similarity to this movie Transformers for each one of our other movies。



![](img/b27423f2623e70674e059337c1b6dec8_42.png)

![](img/b27423f2623e70674e059337c1b6dec8_43.png)

So how do we leverage these new functions in order to map our data that we started off with into higher dimensional space？



![](img/b27423f2623e70674e059337c1b6dec8_45.png)

![](img/b27423f2623e70674e059337c1b6dec8_46.png)

So for a given x1 x2， so for a given rating and a given budget。

 those being our x1 and x2 in this plane， we can create three numbers using these three radial basis functions that we just discussed using that Gaussian functions。



![](img/b27423f2623e70674e059337c1b6dec8_48.png)

![](img/b27423f2623e70674e059337c1b6dec8_49.png)

![](img/b27423f2623e70674e059337c1b6dec8_50.png)

![](img/b27423f2623e70674e059337c1b6dec8_51.png)

So those three numbers will represent the similarities to the different movies in our data set that black Swwaann。

 pulp fiction， and transformformers。

![](img/b27423f2623e70674e059337c1b6dec8_53.png)

And we can use these numbers that we have here A1 equals 0。9 A2 being 0。92， A3 being 0。3。

 each of them being， again a similarity metric to our original movies in order to map our original two dimensional space of just IMDB user rating and budget to three dimensions where those three dimensions are these three values。

 A1， A2 and A3。

![](img/b27423f2623e70674e059337c1b6dec8_55.png)

![](img/b27423f2623e70674e059337c1b6dec8_56.png)

![](img/b27423f2623e70674e059337c1b6dec8_57.png)

![](img/b27423f2623e70674e059337c1b6dec8_58.png)

![](img/b27423f2623e70674e059337c1b6dec8_59.png)

Then for a different point。We just have different values for A1， A2 and A 3， All of them again。

 being defined by their respective similarity to each one of these different movies。



![](img/b27423f2623e70674e059337c1b6dec8_61.png)

![](img/b27423f2623e70674e059337c1b6dec8_62.png)

And this will ensure that these similar movies are closer together once we map them to higher dimensional space。

 making it easier to find this linear hyperplane to separate them out。



![](img/b27423f2623e70674e059337c1b6dec8_64.png)

![](img/b27423f2623e70674e059337c1b6dec8_65.png)

In the next video， we'll visualize what this transformation into a linearly separable。

 higher dimensional space actually looks like。 All right， I'll see you there。



![](img/b27423f2623e70674e059337c1b6dec8_67.png)

![](img/b27423f2623e70674e059337c1b6dec8_68.png)

![](img/b27423f2623e70674e059337c1b6dec8_69.png)