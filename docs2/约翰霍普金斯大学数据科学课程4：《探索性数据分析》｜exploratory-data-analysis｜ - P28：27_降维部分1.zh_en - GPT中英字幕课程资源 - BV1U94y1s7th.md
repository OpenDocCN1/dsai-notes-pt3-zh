# 约翰霍普金斯大学数据科学课程4：《探索性数据分析》｜exploratory-data-analysis｜ - P28：27_降维部分1.zh_en - GPT中英字幕课程资源 - BV1U94y1s7th

![](img/fba5d3ae666094c2cc3664c22c982338_0.png)

Pinncipple components analysis and the singular value de compositionposition are really important techniques。

 both in the exploratory data analysis phase and also in the more kind of formal modeling phase。

 the techniques can be used very easily in both stages。

 but I'm going to talk a little bit about how it's used in the exploratory phase。

 and I want to talk kind what goes on underneath and kind of what their underlying basis is。



![](img/fba5d3ae666094c2cc3664c22c982338_2.png)

![](img/fba5d3ae666094c2cc3664c22c982338_3.png)

![](img/fba5d3ae666094c2cc3664c22c982338_4.png)

![](img/fba5d3ae666094c2cc3664c22c982338_5.png)

So if you suppose we have some matrix data here and I've just generated some random normal data here using this code right here。

 and you can see that the matrix that I plotted here using the image function is not particularly interesting。

 it looks pretty noisy and there's no real pattern as we would expect there to not be。



![](img/fba5d3ae666094c2cc3664c22c982338_7.png)

![](img/fba5d3ae666094c2cc3664c22c982338_8.png)

![](img/fba5d3ae666094c2cc3664c22c982338_9.png)

![](img/fba5d3ae666094c2cc3664c22c982338_10.png)

Now I could just run a hierarchical cluster analysis on this data set。

 I I can doer a cluster analysis on the rows of the data frame or the rows of the matrix and the columns of the matrix。

 and I can do this using the heat map function very easily in R。

 So when I run the heat map function you can see that the cluster analysis is done。

 I get the dendrograms printed on both the columns in the rows。 but again。

 there's no real interesting pattern that emerges and that's because there's no real interesting pattern underlying in the data。



![](img/fba5d3ae666094c2cc3664c22c982338_12.png)

![](img/fba5d3ae666094c2cc3664c22c982338_13.png)

![](img/fba5d3ae666094c2cc3664c22c982338_14.png)

![](img/fba5d3ae666094c2cc3664c22c982338_15.png)

![](img/fba5d3ae666094c2cc3664c22c982338_16.png)

So so that's fine。 But now what if we add a pattern to the dataset set。

 So let's try to add something and I do it with this code here， this for loop here。

 So I loop through all the rows and on a random row， I flip a coin and if it turns out to be a one。

 I just add a pattern I so that five of the columns have a mean of0 and another the other five have a mean of three。

 So I just kind of add a little shift here across the columns So now if I plot the data you can see that there the right of the right hand five columns are a little bit more yellow。

 which means they have a higher value then the left hand five columns which are a little bit more red which means they have a lower value。

 that's because some of the rows。

![](img/fba5d3ae666094c2cc3664c22c982338_18.png)

![](img/fba5d3ae666094c2cc3664c22c982338_19.png)

![](img/fba5d3ae666094c2cc3664c22c982338_20.png)

![](img/fba5d3ae666094c2cc3664c22c982338_21.png)

![](img/fba5d3ae666094c2cc3664c22c982338_22.png)

![](img/fba5d3ae666094c2cc3664c22c982338_23.png)

![](img/fba5d3ae666094c2cc3664c22c982338_24.png)

![](img/fba5d3ae666094c2cc3664c22c982338_25.png)

![](img/fba5d3ae666094c2cc3664c22c982338_26.png)

Have a mean of three on the right hand side and some of the rows only have a mean of zero on the right hand side。

 so you can see there's an obvious kind of step pattern there。



![](img/fba5d3ae666094c2cc3664c22c982338_28.png)

![](img/fba5d3ae666094c2cc3664c22c982338_29.png)

So now if I do if I run hierarchical cluster analysis on the data， you can see that that the。



![](img/fba5d3ae666094c2cc3664c22c982338_31.png)

![](img/fba5d3ae666094c2cc3664c22c982338_32.png)

The two sets of columns are easily separated out。 so you can either the dendrogram on the top of the matrix。

 which which is run on the columns。 see clearly splits into two clusters。 There's  five on the left。

 and there's 5 on the right on the rows。 is's not so obvious because there's no real pattern and like goes along the rows。

 And so that kind of gets reorganized into a random pattern。 and。



![](img/fba5d3ae666094c2cc3664c22c982338_34.png)

![](img/fba5d3ae666094c2cc3664c22c982338_35.png)

![](img/fba5d3ae666094c2cc3664c22c982338_36.png)

And that's the picture that emerges from the heat map。



![](img/fba5d3ae666094c2cc3664c22c982338_38.png)

Now we could take a look at a closer look at the patterns in the rows and the columns by looking at the kind of the marginal means the of the rows and columns。

 So for example， I can look at either the。

![](img/fba5d3ae666094c2cc3664c22c982338_40.png)

![](img/fba5d3ae666094c2cc3664c22c982338_41.png)

10 different column means， or can plot the 40 different row means in this matrix。

 So here with this code， that's exactly what I've done on the left hand plot。

 I got the original matrix data。

![](img/fba5d3ae666094c2cc3664c22c982338_43.png)

![](img/fba5d3ae666094c2cc3664c22c982338_44.png)

![](img/fba5d3ae666094c2cc3664c22c982338_45.png)

That's been kind of's been reordered to look according to the kind of hierarchical cluster analysis the of the rows。



![](img/fba5d3ae666094c2cc3664c22c982338_47.png)

And and and I've plotted in the middle plot here， the mean for each of the rows。

 if you look on the y axis， I've got the row number which goes from 1 to 40。

 so that kind of is roughly parallel with the image on the left and on the X axis I've got the mean of that row。

 So for example， you can see that for row 10， the mean is roughly minus0。25 or something like that。

 and that for row 30， the mean is roughly 1。5。 And so you can see that there's a clear shift。



![](img/fba5d3ae666094c2cc3664c22c982338_49.png)

![](img/fba5d3ae666094c2cc3664c22c982338_50.png)

![](img/fba5d3ae666094c2cc3664c22c982338_51.png)

![](img/fba5d3ae666094c2cc3664c22c982338_52.png)

![](img/fba5d3ae666094c2cc3664c22c982338_53.png)

![](img/fba5d3ae666094c2cc3664c22c982338_54.png)

![](img/fba5d3ae666094c2cc3664c22c982338_55.png)

In the mean as you go across the rows， Similarlyly， if you go across the columns。

 you can see across the 10 columns， there's a clear shift in the mean of each column。

 So the first 10 columns have roughly a mean of0 or close to it。

 and then the next 10 columns have roughly a mean of two because there's a shift there。

 So using the plots on in the middle and the right。

 you can see a clear pattern in the rows in the columns there。



![](img/fba5d3ae666094c2cc3664c22c982338_57.png)

![](img/fba5d3ae666094c2cc3664c22c982338_58.png)

![](img/fba5d3ae666094c2cc3664c22c982338_59.png)

![](img/fba5d3ae666094c2cc3664c22c982338_60.png)

![](img/fba5d3ae666094c2cc3664c22c982338_61.png)

![](img/fba5d3ae666094c2cc3664c22c982338_62.png)

So some related problems so cluster analysis is useful for kind of identifying these types of patterns。

 but we can maybe take a little more a slightly more formal approach that kind of takes advantage of the matrix structure of the data and so the base there are two kinds kinds of problems we might want to look at so if we have a lot of variables and。



![](img/fba5d3ae666094c2cc3664c22c982338_64.png)

![](img/fba5d3ae666094c2cc3664c22c982338_65.png)

![](img/fba5d3ae666094c2cc3664c22c982338_66.png)

![](img/fba5d3ae666094c2cc3664c22c982338_67.png)

We want to create a new set of variables that are uncorrelated and explain as much variance as possible。

 So the idea is that we have a lot of different variables suppose we have hundreds or maybe thousands or tens of thousands of variables in our data and the idea is that they're not all independent thing measurements of something right so a lot of them will be related to each other that'll be correlated with each other。

 for example， you might have two measurements that are like height and weight and so those will obviously be related to each other and so they're not all independent kind of factors so the idea is that we want to create a set of variables that is smaller than the original set of variables that we have and that are all uncorrelated with each other so that they kind of represent a different types of variation in your data。



![](img/fba5d3ae666094c2cc3664c22c982338_69.png)

![](img/fba5d3ae666094c2cc3664c22c982338_70.png)

![](img/fba5d3ae666094c2cc3664c22c982338_71.png)

![](img/fba5d3ae666094c2cc3664c22c982338_72.png)

![](img/fba5d3ae666094c2cc3664c22c982338_73.png)

![](img/fba5d3ae666094c2cc3664c22c982338_74.png)

![](img/fba5d3ae666094c2cc3664c22c982338_75.png)

![](img/fba5d3ae666094c2cc3664c22c982338_76.png)

![](img/fba5d3ae666094c2cc3664c22c982338_77.png)

And similarly， we want this reduced set of variables to explain as much of the variability in your data set as possible。



![](img/fba5d3ae666094c2cc3664c22c982338_79.png)

![](img/fba5d3ae666094c2cc3664c22c982338_80.png)

So another related problem is that if you put all the variables together in one matrix。

 so like the matrix that we showed in the image， you want to find the best matrix that's created with fewer variables but still explains the original data the idea is that more technical term is that you want to find the lower rank matrix that somehow explains the original data reasonably well So the first goal here is a statistical one and it's a common problem that's solved by the method of principal components analysis and the second goal here is more of a of data compression problem where you want to find a kind of smaller representation of the original data and one way to think about that problem is with the singular value decomposition。



![](img/fba5d3ae666094c2cc3664c22c982338_82.png)

![](img/fba5d3ae666094c2cc3664c22c982338_83.png)

![](img/fba5d3ae666094c2cc3664c22c982338_84.png)

![](img/fba5d3ae666094c2cc3664c22c982338_85.png)

![](img/fba5d3ae666094c2cc3664c22c982338_86.png)

![](img/fba5d3ae666094c2cc3664c22c982338_87.png)

![](img/fba5d3ae666094c2cc3664c22c982338_88.png)

![](img/fba5d3ae666094c2cc3664c22c982338_89.png)

So the singular value de compositionposition can be written in mathematical terms in matrix terms as if you have a matrix X where we can think of each column in this matrix as a variable or a measurement and each row of the matrix as an observations so you might have many。

 many observations for a given matrix， so for example。

 the rows of your matrix might represent individual people and each column represent a measurement on those people。

 so for example， the first column might be the height and the second column might be the weight。



![](img/fba5d3ae666094c2cc3664c22c982338_91.png)

![](img/fba5d3ae666094c2cc3664c22c982338_92.png)

![](img/fba5d3ae666094c2cc3664c22c982338_93.png)

![](img/fba5d3ae666094c2cc3664c22c982338_94.png)

![](img/fba5d3ae666094c2cc3664c22c982338_95.png)

![](img/fba5d3ae666094c2cc3664c22c982338_96.png)

So then the idea is that if you have a matrix X that's formatted in this way。

 then the singular value decomposition or the SVD is a matrix decomposition which decomposes the original matrix into three separate matrices。

 one is called U one is called D and the other called V and so the columns of U are orthogonal。

 so they're independent of each other， they're called the left singular vectors and the columns of V are also orthogonal and they're called the right singular vectors and then d is a diagonal matrix which contains the singular values。



![](img/fba5d3ae666094c2cc3664c22c982338_98.png)

![](img/fba5d3ae666094c2cc3664c22c982338_99.png)

![](img/fba5d3ae666094c2cc3664c22c982338_100.png)

![](img/fba5d3ae666094c2cc3664c22c982338_101.png)

![](img/fba5d3ae666094c2cc3664c22c982338_102.png)

![](img/fba5d3ae666094c2cc3664c22c982338_103.png)

So that's the basic idea of the singular value decomposition I'll talk about these components a little bit later on Pri components analysis also usually known as PCA is it uses the singular value decomposition and is a related technique and the basic idea is that if you were to take your original data matrix and subtract the mean of each column from each so subtract the column mean from each column and divide by the column standard deviation and then run an SVD on that kind of renormalized matrix the principal components would be equal to the right singular values of the matrix so the V matrix。



![](img/fba5d3ae666094c2cc3664c22c982338_105.png)

![](img/fba5d3ae666094c2cc3664c22c982338_106.png)

![](img/fba5d3ae666094c2cc3664c22c982338_107.png)

![](img/fba5d3ae666094c2cc3664c22c982338_108.png)

![](img/fba5d3ae666094c2cc3664c22c982338_109.png)

![](img/fba5d3ae666094c2cc3664c22c982338_110.png)

![](img/fba5d3ae666094c2cc3664c22c982338_111.png)

![](img/fba5d3ae666094c2cc3664c22c982338_112.png)

![](img/fba5d3ae666094c2cc3664c22c982338_113.png)