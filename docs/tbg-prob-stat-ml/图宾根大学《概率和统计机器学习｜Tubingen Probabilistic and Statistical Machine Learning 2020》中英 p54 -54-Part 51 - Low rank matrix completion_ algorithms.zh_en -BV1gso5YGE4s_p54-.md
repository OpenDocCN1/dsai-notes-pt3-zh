# 图宾根大学《概率和统计机器学习｜Tubingen Probabilistic and Statistical Machine Learning 2020》中英 p54 -54-Part 51 - Low rank matrix completion_ algorithms.zh_en -BV1gso5YGE4s_p54-

Today， we want to discuss about low rank matrix completion。If you want to read up on that。

 I recommend highly the book by Hasti Tiiprani and Wainwright Statly learning with Sprssity。

 which covers this whole chapter of the lecture as well。

 and maybe to give you also some historical perspective I put a number of original references here。

 for example that' the seminal paper by Kands andreh， everybody knows that one that was in 2009。😊。

Which sort of brought up many of the important conditions when low rank matrix factorization is is working and gave some theoretical results。

And then here are two papers， but there， I mean， there are many more papers out there。

 but I ci two of them from which we take some algorithms in this lecture。

Let me start you start by telling about the Netflix problem。

 So consider Netflix you have lots of users and you have lots of movies and certain users watch a movie and then maybe they give a recommendation so you have and you can try to store all these recommendations in a matrix and I'll try to simply write it on the iPad we have a big matrix。

😊。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_1.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_2.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_3.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_4.png)

The row correspond to users， the column correspond to movies。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_6.png)

And maybe a particular movie has a particular user has seen a particular movie and gives a rating of one and then somebody else has seen a different movie gives a rating of five and so on so you have a number of ratings。

😊，In this matrix。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_8.png)

But the big part of this matrix is empty because most users haven't seen most movies。

And now the question is if you want now if you provide an extra Netflix service and you want to recommend a movie to a user。

😊。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_10.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_11.png)

Then it would be good to complete this matrix to know what would be the rating of this movie。😊。

For this particular move of this user， for this particular movie。 So， for example。

 there might be a this user here that we have in this particular row。 and maybe the user has watched。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_13.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_14.png)

Three movies already ready and gave ratings and now you want to recommend a new movie now it would be interesting to know what are the values of this row for all the other movies and then take one for which their recommendation is good。

😊。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_16.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_17.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_18.png)

And this problem is called the matrix completion problem。 So if we have it here on this slide。

 So we there's a matrix， and we are only given few entries in this matrix。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_20.png)

And the matrix completion problem is to estimate all the missing entries。😊。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_22.png)

And the purpose would be， for example， in movie recommendation to recommend new items to a user。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_24.png)

More than 10 years ago there was a challenge in the machine learning community that was really。

 really famous at the time it was the Netflix challenge。

 that was sort of just the time when all these competitions started and Netflix was the first competition where you could really win a lot of money so it was launched in 2006。

😊。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_26.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_27.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_28.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_29.png)

And the data at that time consisted of about 20，000 movies， 500，000 users。

 and 10 to the pair of nine ratings。😊。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_31.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_32.png)

And if you sort of to the math， it means that about 1% of the entries were known and the rest of the matrix was unknown。

And the goal was to provide an algorithm for for like a matrix completion algorithm。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_34.png)

And to predict the missing entries better than Netflix。 So the the the。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_36.png)

The conditions of this competition was that the first team that beats Netflix's own algorithm by an improvement of at least 10% wins $1 million。

😊。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_38.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_39.png)

And like many people in the machine learning community started to work on this problem and then in fact it went on for a couple of years and finally it was achieved in 2009 and at the end it was really。

 really tight on the leaderboard there were a couple of groups that like all had sort of similar performance very close to 10% and if I remember correctly at the end the best couple of teams emerged and joined the effort and tried to combine all the tricks that they found to finally managed to get jointly beyond these 10% and win the prize。

😊。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_41.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_42.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_43.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_44.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_45.png)

So this was a historic event in the machine learning community。😊。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_47.png)

But now let's come back to this general problem of matrix completion。😊。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_49.png)

So the general setup for this and the following lecture is now we have a matrix M times n。

 so it's not a square matrix because one column the user say in won the movies。😊。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_51.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_52.png)

The matrix is unknown。Now we get to see some entries in the matrix and we will need to talk about how we generate these entries。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_54.png)

Namely， the strong assumption that we make in the following is always that the position of the revealed entries is random。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_56.png)

So you can consider several scenarios now in this matrix completion scenario。

 but what we assume is that when like if if I were to simulate the data。

 there' is a matrix somewhere in the background and I can ask for the for for。😊。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_58.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_59.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_60.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_61.png)

The contents of random positions in this matrix in particular。

 this excludes that there's an adversarial setting where sort of some adversary is allowed to pick lots of misleading entries and then of course it's difficult to compute on and to complete。

 So it's a bit like in the standard classification setting where we say the entries in our training in our training set are drawn randomly but II from the underlying distribution and here we do make a similar assumption we assume that there is no structure and no adversary can fool us completely。

 So the position of these entries is random。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_63.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_64.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_65.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_66.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_67.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_68.png)

And now we have some entries that we observed chosen randomly。

 and now the goal is to estimate all the unknown entries。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_70.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_71.png)

And maybe when you see such a problem it's always good to lean back for a second and think about under which conditions might this problem be easy。

 is it always easy， is it always difficult， is it possible to solve that at all or might there be some reasons why it's really impossible to solve that and I think it's really good to try to maybe switch off the movie for a few minutes and try to think about these questions。

😊。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_73.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_74.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_75.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_76.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_77.png)

To practice getting this inherent feeling for problems。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_79.png)

Now， when you start thinking about this problem。😊。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_81.png)

You will realize that we probably need to make some assumptions on the underlying matrix。

 its a bit like in classification if you have random points in a space and then they can get random labels。

 it is probably hard to predict。😊。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_83.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_84.png)

And similarly， if you have now a matrix and say the ground truth matrix has been generated by randomly flipping a coin for each of the entries。

 and so you have entries which are either0 or1。 but this has been generated like all entries are chosen independently of each other。

 then no matter how many entries you will observe， there is nothing you can say about entries that you haven't seen yet。

😊。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_86.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_87.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_88.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_89.png)

So in this sense， this data generating process is too general。

 you will not be able to solve that problem。😊。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_91.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_92.png)

And if we think about this a bit more in the terms of what we discussed in the beginning of the lecture and in learning theory as well。

 what is missing here is an in bias， so we will need to make some assumptions that this matrix satisfy some in bias。

 what we are looking for that sort of excludes this completely random case。😊。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_94.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_95.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_96.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_97.png)

And in particular， some of these assumptions will need。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_99.png)

To state something about how these entries of the matrices of the matrix are related to each other。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_101.png)

And if we don't have anything to say about that， then probably the problem is hard to solve。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_103.png)

Now another insight that we got from learning theory is that typically it's good to have a function class or maybe hear a class of matrices in which we are searching for the optimal solution that is reasonably small so we tend not to overfit so much so what we are now looking for is an inductive bias that induces that we have a small set of ground truth matrices that we can try to look for and try to fit through the data that we have。

😊。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_105.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_106.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_107.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_108.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_109.png)

And now the assumption that everybody uses in this field is now that we are going to look for a matrix that has low rank。

 So the idea is the set of matrices that have low rank is sort of smaller than the set of matrices that have a higher rank。

😊。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_111.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_112.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_113.png)

So this is from a theoretical perspective nice， but also it turned out that in practice。

 this is an inductive bias that tends to work very well。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_115.png)

Maybe just is a sendity check。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_117.png)

We just said on the previous slide that probably we could not achieve this matrix completion if the entries of the matrix are completely random。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_119.png)

And now if you start thinking about we say we look for a low rank matrix。

 maybe it would be in the first place it would be good to make the sanity check whether random matrices would have a low rank or not and the answer is no。

 I mean if you want you can simply try that in Matlaap or in Python generate a random matrix。

 computer rank like look at the eigenvalues of this matrix and check whether I mean either the rank or also look at the absolute values of these eigenvalues。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_121.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_122.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_123.png)

Whether it's many of them have a small value or not。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_125.png)

The answer that you' are going to find is that random matrices tend to have a high rank and in principle。

 I mean this is something that is really well known。

 the eigingvalue follow what is called the semicircle law。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_127.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_128.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_129.png)

So they。Rand the matrices explicitly are not matrices that might be well modeled by this low rank kind of approximation。

 which sort of makes sense because otherwise this inductive bias wouldn't really fit together with what we said on the previous slide。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_131.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_132.png)

Now let us write write up how this matrix completion problem actually works。

 So we now will denote by omega the set of entries of this matrix that have been observed。

 So we always have a matrix Z。 This is the ground truth matrix。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_134.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_135.png)

We observe a number of entries。 These entries are going to be called omega。

And so this is a set of indices， Ij， and for the ones that are in omega。

 we know what these values are， namely CIJ， someone we can sample these matrices at these values or someone gives the values to us。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_137.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_138.png)

And now what we want to solve is we want to find a matrix M。Such that。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_140.png)

On the entries that we have been observing， the entries of M in the perfect case I exactly coincide with the values that we have been observing。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_142.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_143.png)

But at the same time， we want to have a matrix M that has a low rank。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_145.png)

Because we hope then that we don't overfit so much。

Now often it's quite strong to hope that we can exactly recover all the entries here so I mean here we go for exact recovery we really want to perfectly recover the entries maybe often we are not it's fine if we sort of approximately recover these entries so you can write a slightly weaker version which just says we sum essentially the squared errors of all the entries that we have been observed and they are pro values and the sum of all these entries of all these errors should not be smaller than a certain constant data。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_147.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_148.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_149.png)

Or this is now a heart constraint where you say the error shouldn't be larger than delta。

 typically what you often do in machine learning in these cases is you don't want to have a heart constraint on the error but you look at a regularized version and where you say I want to minimize both the empirical error of my matrix。

M plus lambda times the complexity term， which in this case is the rank of the matrix。Okay。Now。

 we can now start thinking about this problem and again now it's interesting to think about whether you think this is a difficult problem or not。

When it' is written on this slide here already it's an NP heart problem like in any of these formulations。

 the problem is really hard。😊，I suggest that you maybe take a minute to try to get a feeling for why is it hard。

 Why is this a problem that could be NP hard， What is difficult about this problem。

Maybe I give you one little explanation， I mean typically problems at least they tend to be simple if there is some kind of gradient that you can compute。

 you can do some gradient descent and so on， the question then is still whether there are many local optim or not。

 but this makes our life easier。😊。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_151.png)

Now the rank of a matrix。😊，Is a function that is completely non continuous。 So assume we have。

 say you have a matrix。 The matrix is the the complete0 matrix。 It has rank 0， of course。

 and consists of just zeros everywhere。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_153.png)

But now assume you instead of 10， you put a little epsilon here。

 then all of a sudden this matrix has ranked one。And now say you put a little epsilon here。

 the matrix has rank 2， and now you put a little epsilon here and the matrix has rank 3。

 So tiny changes in the entries of this matrix can completely change the rank of this matrix。

 And this is typically an indication for the fact that an optimization problem is really。

 really hard to solve。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_155.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_156.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_157.png)

Just as aside from mock。Now we can sort of try to come up with heuristics that still help us to solve this problem with NPhar。

 and maybe it doesn't always work， but maybe we can find heuristics that sort of work well in practical settings。

😊，Now here is the first one， which is called heart impute。

 so imputation is always like if you have missing values in a data。

 the procedure to put in some plaus values is to be called imputation and now here this problem is being called heart imputute。

😊。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_159.png)

Or the algorithm。So what we now do is we are given this matrix and so we don't know the matrix。

 we just observe some entries of this matrix。😊，And we do now an iterative procedure for the entries that we haven't seen。

 we start with some initial gas， say pick random numbers from anoma distribution， for example。

 and put them in the in the entries that you didn't know。Now。

 what we do is we compute a singular value decomposition of this matrix and just keep the first R singular components。

And then this is now our first iterative matrix we call this Z2。

AndNow what we do is we clamp the values of the ones of the matrix that we have seen already and fill in the rest with the values of C2 and then we start over again so in each step we make we make an approximation of the matrix with a low rank matrix。

Then we make sure that after we did the approximation。

 the entries that we know exactly coincide to the ones that we have observed。

 We do another lower rank approximation， and we do this iteratively。😊，And conversion， hopefully。Now。

 the statement I want to make here on the slide is that sometimes this already works reasonably。

But it's sort of， it's not really completely satisfactory， I， at least in my opinion。

So now the idea is maybe instead of doing this hard imputation。

 we can do something that is a bit softer， have a bit of a relaxed version and find。

 but find a solution that maybe works a bit better in practice and maybe one for which we can also say something。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_161.png)

And now the problem about this heart problem is always a strong rank constraint。

 So what we now want to do is we want to find a replacement for this strong constraint on the rank by a function that is a bit softer in some sense。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_163.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_164.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_165.png)

And this sort of brings us back to to some things that we have already seen， for example， in Laso。

 So where we where we again， we also looked at sparsity， we said we want to recover。

 we want to find a vector of coefficients for which most coefficients are0。

 And then the question was， how do we measure。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_167.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_168.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_169.png)

The number of nonzero coefficients we can simply count them which was sort of the zero norm of this vector but then we said well counting is really not the best thing because it also needs a nonconvex problem and then we replace the01 by norm by the one norm and we found that in practice measuring sparsity by the one norm of the vector is still a good replacement and leads to solutions that tend to be sparse。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_171.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_172.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_173.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_174.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_175.png)

Now with this as a background， we now look at this problem where we say we want to find a matrix that has low rank。

😊。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_177.png)

And if you want the rank of a matrix is if you write all the eigenvalues of this matrix in a vector。

 the rank of the matrix is essentially the zero norm of this vector。😊。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_179.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_180.png)

And this is now what I want to describe on the slide here。

 so we are given this matrix a and let's denote by sigma。

 the vector sigma and all these singular values of the matrix。😊。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_182.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_183.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_184.png)

And now the rank of the matrix is given as the zero norm of this vector of course。

 because if a matrix has rank 5， then we have five eenvalue with general or singular values that are non0 and the rest of them are zero。

😊。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_186.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_187.png)

But now this is sort of leads to this NPhar problem and what we want to do now is we want to instead of looking at the zero norm as in Laso we now want to look at the one norm of this vector so we now take the eigen vector sorry the vector of eigingvalue and instead of minimizing the zero norm we now say we minimize the one norm of this particular vector and the one norm is I mean that's clear the sum of the absolute values of the eigenvalue in this case。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_189.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_190.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_191.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_192.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_193.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_194.png)

And now if you consider a matrix and you consider the one norm of the eigen vectors。

 of the vector of eigingvalueary。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_196.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_197.png)

This norm has a particular name。 It is called the trace norm of a matrix。

 So this is not a definition， the trace given a matrix。

 the trace norm is the one norm of the vector of all its singular values。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_199.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_200.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_201.png)

S in the case of the 0，1 norm approximation for the laso， also in this， in this particular。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_203.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_204.png)

A case of the norms of matrix norms if you one can prove that this trace norm that is sometimes also called the nuclear norm is the tightest convex relaxation of the rank of a matrix so if you want to have an obsim mutationut problem where the rank is。

 for example， a constraint and you want to find a convex relaxation then the tightest one that you can find is looking at the nuclear norm or the trace norm which is the same。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_206.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_207.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_208.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_209.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_210.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_211.png)

So with this in our background， we now try to look at the optimization problems if we replace the rank constrained by nuclear norm constraints or trace norm constraints。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_213.png)

So instead of the rank， we now have minimized the trace of your matrix。

If this formulation or the second formulation where we look at the regularization formulation was the trait like again minimize the empirical error。

 but then minimize now the trace norm of the matrix that we're looking for。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_215.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_216.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_217.png)

Again， these two problems are essentially the same， you can sort of convert them to each other on。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_219.png)

So what we've done so far is now we made the problem maybe simpler from a conceptual point of view and now we still want to figure out how can we solve this problem because still I mean。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_221.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_222.png)

Sort of if if you don't have any background and someone comes to you and says， well。

 minimize this problem here like an optimization problem where you have sort of a quadratic error term but then the trace of a matrix it doesn't sound completely obvious how to do that。

 right。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_224.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_225.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_226.png)

So the big questions are now， can we find an efficient algorithm that finds this global optimum for any of the two problems。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_228.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_229.png)

And by efficient， I mean， this bird efficiency is really important because if you think about Netflix it has millions of users and millions of movies。

 so this matrix is say a million by a million and if you have an algorithm that scales say quadraically in the size of your matrix like then this already might be too large to be able to sort so you need to find an efficient algorithm。

😊。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_231.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_232.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_233.png)

And then the second question is， of course， if we have an algorithm。First of all。

 can we give any theoretical guarantees about the solution。

And the other one that is interesting from a theoretical point of view is really。😊。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_235.png)

Like assume we have 1000 movies and 1000 users。 So how many entries would we need to observe in principle before we would be able to make a reasonable guess about the rest of the matrix？

 So would it be enough if we have 1000 movies and 1000 and 1000 users say we have 1000 times1000。

 Is it enough to sample 1000 entries do we need to sample 10000 entries or 100000。

Simply to get a feeling for how many entries would we need in order to be able to solve this problem。

 And again， considerations like this are really important。

 like if a manager naturally comes to you with this new idea of making this matrix completion。😊。

Then maybe before you start diving into it for half a year。

 you might consider briefly what is the amount of data that you believe you would need and if you would need like half of the entries of the matrix to be able to predict the remaining entries then maybe this is not the approach that you might want to follow up for the next half here。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_237.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_238.png)

嗯。So there is a first way to formulate this problem in terms of what is called a semi definite program。

A semideinite program is typically one where you have constraints。

 one of the matrices is positive semi definite and then you make some have for example。

 the rank of a matrix is some part of your optimization problem。

This can be solved in polynomial time， but typically， I mean， polynomial， it's polynomial。

 but slow polynomial。 So these problems typically take very long and it's not really very efficient to solve them。

 I don't want to go into any of these details here because this is not what people would do in practice at this particular time。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_240.png)

Now here's another strategy。😊，And this is what I want to describe now。

So we we now do something we use something that is called soft thresholding and I'm going to explain in a minute what this is。

 but heres the strategy once we know what soft thresholding would be。

 we start again with an initial guess for the missing values。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_242.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_243.png)

We compute singular very decomposition。😊。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_245.png)

Then we apply what is called soft thresholdholding。

 which essentially tries to make the rank of the matrix even lower。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_247.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_248.png)

sort of it's also a smoothing operation anyways。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_250.png)

And then you start over again。It is a bit， It sounds a bit similar to to this hard impute algorithm where we said we do an SVD。

 We always claim the first K eigenvectors fill in the missing， like。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_252.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_253.png)

Cp the values for the for the values that we have seen and always approximate with with the k the K highest singular values。

 and we keep on doing that。 Now what we do additionally on top is that we do introduce a soft threshold soft threshold operation。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_255.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_256.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_257.png)

嗯。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_259.png)

And now maybe it's time to explain what soft thresholding is。

So soft thresholding is a way to sort of slightly reduce the whole spectrum of this matrix so assume we have this matrix Z and assume for now we know the matrix Z this might be a matrix is some intermediate matrix in our algorithm we do a singular value decomposition of this matrix and for now simply denote the singular values by DI。

😊。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_261.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_262.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_263.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_264.png)

Now what we do is and we replace each of these singular values by this soft singular value which is or by this soft thresholdholding function So if so lambda is the parameter。

 this thresholding parameter and essentially what we want to do is all the eing values that are between0 and lambda we simply set them to0 immediately so the sort of significantly reduces the rank it essentially gets rid of the tail of all these eingvalue So if there are many I if you have many some few few high singular values at many small singular values essentially thresholding at some singular value Lada means you set all。

😊。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_266.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_267.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_268.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_269.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_270.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_271.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_272.png)

Eenvalue or singular values that are smaller than lambda。 you set them to 0。 exactly。

 This is what this operation does。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_274.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_275.png)

And now if you have a singular values at a higher， you will reduce them simply by subtracting lambda。

😊。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_277.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_278.png)

So this is a method。 It's at this point， not completely obvious。 I mean。

 I think there' is one positive consequence that you would see is that you would set the tail of all these eigenvalues to 0。

It also does something to the first avalue， it's not at this point not really clear whether this is really helpful or hurts。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_280.png)

One fact that you can， of course， state is that soft thresholdholding always decreases the trace norm。

Because all e values are deduced by a Lada， and it often also decreases the rank if you have many small e values that are being set to exactly zero。

 because then you change the rank of the matrix。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_282.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_283.png)

And now why do people， Why is it interesting to look at this soft thresholding now here's a really nice proposition about soft thresholding。

Now， what we do is we consider one step of soft thresholding just one step。

 and we assume that we have a matrix that is completely known right So， I mean。

 this is just an intermediate proposition。 So assume theres a matrix C。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_285.png)

That is completely known。And now we choose some thresholding parameter at Al Lata。

And value lambda at larger than 0。And now we consider this optimization problem that we are interested in。

 namely we want to minimize we want to find a matrix M。😊。

That approximates the original matrix in terms of the Frbiusome。Plus。

 and now we have the straightoff term we want to plus lambda times the trace norm of this matrix。

 so now we have a regularization problem which says given this original matrix which is completely known approximated by another matrix that has hopefully small rank and instead of the rank we look at the trace norm。

And Lada is our trait of constant。 and we measure the empirical error between the two matrices in terms of the Frbeus。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_287.png)

And the serum now says， assume you want to solve this problem。😊。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_289.png)

Then the solution to this problem is given by the result of one round of soft thresholding。

 So you apply soft thresholding once and then you solve this problem。

This is sort of quite surprising and neat and elegant。

Now I don't want to go through the proof if you want to look at it。

 you can really look at the original paper， which is this J and our paper。

 which is just cited at the bottom of the slide。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_291.png)

So now we want to exploit this and do something similar for this matrix completion problem where we don't know all the entries。

 maybe let's go back。 So the important thing here is that this of course only works if we have all the entries of the matrix Z。

Otherwise。This sort of， I mean， this is simply an assumption we have in this proposition。

 now the question is， can we still make use of this soft thresholding operation if not all of the entries unknown。

 we just observe some of them。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_293.png)

And to be able to discuss this case， we now need to introduce a bit more notation。

 so what we've already seen as omega is the set of the indices for which we have observed the entries of the matrix。

And now we need to define two project operators that are called projection operators in that book。

 it is not really a projection， so what I want to say here is so assume we have this original matrix Z and this projection to omega and Z。

😊，Is simply a new matrix that has zeros everywhere。

 except at the places where we have observed the entries。 and there we put the actual entries。

 So maybe on the iPad。If we have this matrix C。It is unknown in many places。

 but maybe here we know it's a five， here a four， here's a three， and here's a one。

But we don't know the entries in the rest of the matrix。 I just put stars。 It could be anything。

And now this matrix P sorry， P omega of C。This is now a matrix that has the same structure，5 here。

 1 here， four here， 3 here， but all the other entries are0。Okay， so this is。

This is what is quality of the projection on omega on the observed entries。

And we also have a projection the orthogonal projection in this notation。

 which is a projection on all the other entries， so here if we look at the projection on the orthogonal space of omega of C this is essentially。

😊，You have zero at the entries where we have observed something and then we have all the stars。

 I mean， I don't know what these entries are， but if you know the matrix of course you know these entries so you keep all the entries that have not been observed。

OkayAnd so I mean， just to get used to this notation。

 if you look at the empirical error of an approximation so you have your original matrix C。😊。

You have observed it at a number of entries and you approximate this matrix C with another matrix M。

And you compute the empirical error by just on the observed entries。

Then this is the same as the Frbeusome。When you take the matrix C。

 just project on the interesting entries， you take the matrix M。

 just project on the interesting entries， and then you compute the for penus norm。Right。

 and because the other entries are going to be set to 0。

 and then they don't contribute to the for at all。And here， I mean， regarding this operation now。

 additionally。😊，And what we have is that the matrix Z is now given as the projection on the observed entries plus the projection on the non observed entries。

Now I want to look at this algorithm that is called soft imputute and annoyingly sort of the slides have been scrambled so I just changed something before recording the lecture sorry So Z is now supposed to be this partially observed matrix。

The one that we want to complete and the input to the algorithm is also a sequence of parameter called Lada 1 to Lada K。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_295.png)

And here is now the algorithm that was meant to be on the previous slide as well。

 so as I said the input is this matrix C that we want to complete and or the entries that we have observed maybe and these parameters are lambda k and now what happens？

😊，So we start with like its going to be an iterative algorithm so we have the oldest sort of the starting matrix。

 we simply start with a completely zero matrix and then we have a for loop which runs over a number of rounds。

 K rounds。😊。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_297.png)

And now lets maybe for now ignore what these lambdas are or maybe lets say it like this。

 so these lambdas are going to be the threshold values that we are going to apply in the soft thresholding algorithm。

😊。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_299.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_300.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_301.png)

And we start with a value of lambda that is large， so we have a highest thresholding。

 a highest threshold which means we look at like we subtract a large value of all the eiging values。

 which means that if we have many eing values， we put this threshold very early so that already pretty large eingvalue are going to be still set to0。

😊。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_303.png)

But then later on， in this algorithm， we are going to reduce the threshold。

 so we are going to see more angle if you want。Okay。

 so we start with a large threshold lambda and now what we do is we compute the new。

 which is now this soft thresholding operation with this value of lambda k。😊。

And the matrix we look at is and we take the observed entries of the matrix Z。

 this is just the values this is our training data essentially。😊，And plus， all the other values。

 we fill up the matrix with the previous estimate that we had。😊。

AndThe previous estimate at this point is just a0 matrix， but， we repeat this often。

 So this is sort of a for loop that runs inside。 So this is。This I mean。

 it's not a very elegant way of writing this essentially。

 but you repeat until you have some exit criterion。

 which means that your approximation is well enough。😊，But as long we are not well enough。

 we repeat essentially always this line line1， which is we take the existing values， clam them。

 we fill the matrix with the current best estimate that we have， we apply soft thresholdholding。

And then we assign like the matrix that we found now is now called old new and then so sort of we repeat。

 So we always have。Given the current matrix。You do one soft thresholding operation。

On the on the current matrix， but you make sure that on the current matrix。

 the entries in the observed positions are exactly the correct ones， and you repeat this often。

Until in line 2 here， you have some convergence criteria matched。This was part A。And then。

 this is sort of。Now。You have this and this is now the solution of what is what corresponds to this value of lambda that you're currently looking at。

And now you do this for all these values of Lada and now you output the sequence of these solutions。

 And then the question is what to do with it， But this is sort of the soft impute algorithm。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_305.png)

Okay。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_307.png)

And here again I have the sort of the intuition so the inner loop is for a fixed lambda you clam the observed values and fill in the rest by a lower rank matrix completion。

 including the soft thresholding。😊。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_309.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_310.png)

And the outer loop， which is the ones for the lambmbdas is。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_312.png)

Here this this for loop。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_314.png)

If you start with an easy case where this lambda， I mean the rank that you're looking for is very low。

 so it's easier to approximate something with a low rank than with a medium rank or even a high rank and then start of you work away towards more difficult values of Lada。

Like meaning smaller values， okay。

![](img/afd64bdb3310ca35511ef030f3b8e4b3_316.png)

And now the what， what can we say about this algorithm， I don't want to present any proofs。

 but I want to say what is sort of the。The intuitive meaning of the results that are being stated。

 you can now prove that this solution always converges to the global solution of the problem that we actually want to solve for a suitable choice of these values and this is now a bit more complicated and if you want to read all the details。

You can do that in the paper， it says essentially they exist a choice for these values such that the solution converges to the correct solution。

😊，嗯。So this is nice because we can give some theoretical guarantees that the algorithm is really going to solve the problem that we are looking for。

 I mean recall the soft stretching solves this problem if we know all the matrix entries and now we don't know all the entries but the statement is now it can still be solved in this particular way。

😊，And now the other thing that is really important is that this algorithm also can be implemented efficiently even if the matrix is huge。

😊，And for example， I mean， just to get a feeling on this whole Netflix data set that I cited in the beginning。

 this whole thing runs within a couple of hours。😊，And this is， again。

 something that needs a lot of experience to figure out how to how to run these algorithms really efficiently。

 And the matrix in this particular case is that we can decompose so observe this matrix。😊。

I can't really market this matrix E that we're looking for as a dense matrix。

 it's the movie ratings of everybody， so theres nothing。

 it's not a sparse matrix because we want the rating for all movies。😊，And the main trick is now。

That we can decompose this matrix into a sum of two matrices， and one is spas。

Meaning only fulfilled values are on 0。 and one has a low rank。

 which also means that there's lots of structure by which which we can exploit。 So if we write it。

 So the original matrix， as we hadn't seen already， the original matrix C。

 we can write it in this way， the projection on the on the observed entries and the rest。

 And now the the。Protection on the， on the observed entries is of course spa。

 because we've only seen few entries。And now this other matrix here。

 this is supposed to have low rank。And and or at this in the algorithm always has low rank because we do a low rank approximation in all of these steps。

In exploiting this， you can manage to write really efficient code for for this problem。

If you want to try it， there is an R package that you can use， if you want to read the theory。

 please look at the paper。Now let's maybe look at how does this algorithm behave in practice。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_318.png)

And practice here， first of all， means the Netflix data。

So here are two figures that I took from the book Statistic Learn with Spsity。

And which is how this algorithm behave on the Netflix data except。

 So this is really the data of this Netflix competition。😊，You see two plots。

The green line is always the result of the heart impute algorithm。

 The red line is the one of the soft impute algorithm。

Here on the left hand side what we see is we have training and test error。

 once its with field dots so the test error this is what were interested in is the one up here。

 this is with field dots and the training errors are the ones within nonfil dots。😊。

And what is plotted here on the x axis is the rank。That we use in this soft impute。

And on the Y axis you see the would mean square error。 So this is a measure of error。嗯。

And so what we can see here at least we can compare sort of the training and testing error the training error goes nicely to0。

 this is what you would expect in such an optimization procedure and the test error sort of remains it sort of I mean it does something and what we can also observe is that hard impute and soft imp。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_320.png)

Behave slightly differently， but also training like the test errors are not vastly different from。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_322.png)

From each other so I mean and maybe just to give a sanity check or like again。

 if you see such figures， it's always good to figure out what does the y axis really mean and what would be the error that you might be able to expect。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_324.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_325.png)

I did a simulation here， so the random guessing would be about having root means got error2。😊。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_327.png)

And now these algorithms achieve an error of one， which is much better than two。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_329.png)

嗯。Now， whether the error of here， I mean， we have maybe 0。95 and 。96。

 maybe this is not what in practice really makes a bit difference。

 so hard and soft imp sort of here behave similarly。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_331.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_332.png)

Here on the right hand side， you also have a plot that shows。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_334.png)

The training error versus the test error of the two algorithms and just I think the dashed line。

 this one here is the behavior of the Netflix algorithm。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_336.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_337.png)

So again， what we can see， the soft inputute is slightly better better than the heart inputute。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_339.png)

The hard and essentially is as good， at least for some choices of parameters is as good as。

 as you have it here。 Yeah as you have it for Netflix。 and the other one gets a bit better。



![](img/afd64bdb3310ca35511ef030f3b8e4b3_341.png)

![](img/afd64bdb3310ca35511ef030f3b8e4b3_342.png)