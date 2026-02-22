# 图宾根大学《概率和统计机器学习｜Tubingen Probabilistic and Statistical Machine Learning 2020》中英 p47 -47-Part 44 - Statistical learning theory_ Revisiting Occam and outlook.zh_en -BV1gso5YGE4s_p47-

I want to still give you。

![](img/a3aa905b74a6ef9755763340286a4684_1.png)

A bit of a feeling and come back to what we discussed in the very beginning of this lecture。



![](img/a3aa905b74a6ef9755763340286a4684_3.png)

In the very beginning we had these examples and said well here here's a set of points。

 here are two functions which maybe might be a better function to learn this particular data and we discussed that Ohams Raisor is something that at least many people state is a useful thing to look at and now I want to relate this back to learning theory and want to see whether learning theory in our says we should follow outcomesham's Raor or not。

😊。

![](img/a3aa905b74a6ef9755763340286a4684_5.png)

![](img/a3aa905b74a6ef9755763340286a4684_6.png)

So here's what we did， I think it was the first or second lecture in this term。😊。

We had this couple of data points。 the black ones。 we guessed two different。



![](img/a3aa905b74a6ef9755763340286a4684_8.png)

Ways to fit the data this red line here was guess1 and this red line here is guess2 and the question ask which of the two functionss should be preferred？

😊。

![](img/a3aa905b74a6ef9755763340286a4684_10.png)

![](img/a3aa905b74a6ef9755763340286a4684_11.png)

And then the argument was always well if I don't have any additional prior knowledge maybe the first function might be a bit better it doesn't make so many funny things so the second guess I mean there are all these wiggles in the functions in the function and unless I have a good reason to believe that these wiggles are there why shouldn't I simply use the linear function because it seems to be easier and this principle that you should look for simple functions this is called Ohams razor。

😊。

![](img/a3aa905b74a6ef9755763340286a4684_13.png)

![](img/a3aa905b74a6ef9755763340286a4684_14.png)

![](img/a3aa905b74a6ef9755763340286a4684_15.png)

![](img/a3aa905b74a6ef9755763340286a4684_16.png)

And often also the principle of parsimony， if you like。😊。

And what you read often in textbooks and so on in Wikipedia， wherever you look it up。

 it says something like when you choose from a set of otherwise equivalent models。

 the simpler model should be preferred， you should always use a linear function unless you have a good reason to use a polynomial function with a higher degree。

😊。

![](img/a3aa905b74a6ef9755763340286a4684_18.png)

![](img/a3aa905b74a6ef9755763340286a4684_19.png)

![](img/a3aa905b74a6ef9755763340286a4684_20.png)

And the intuitive argument that you then always read that tries to justify these things is something along the following line。

😊。

![](img/a3aa905b74a6ef9755763340286a4684_22.png)

![](img/a3aa905b74a6ef9755763340286a4684_23.png)

Ocom's Raor helps us to shave off those concepts， variables or constructs that are not really needed to explain the phenomenon by doing that developing the model will become easier and there is less chance of introducing inconsistencies。

 ambiguities and redundancies。

![](img/a3aa905b74a6ef9755763340286a4684_25.png)

![](img/a3aa905b74a6ef9755763340286a4684_26.png)

![](img/a3aa905b74a6ef9755763340286a4684_27.png)

Okay。

![](img/a3aa905b74a6ef9755763340286a4684_29.png)

And all this， of course， makes perfect sense from a high level point of view。

But now I want to come back and ask， well， is this really what learninging theory tells us？😊。



![](img/a3aa905b74a6ef9755763340286a4684_31.png)

![](img/a3aa905b74a6ef9755763340286a4684_32.png)

So in learning theory， the main message was we look at the size of this function space。😊。



![](img/a3aa905b74a6ef9755763340286a4684_34.png)

Nowhere in these generalization bonds。

![](img/a3aa905b74a6ef9755763340286a4684_36.png)

We looked at something like is a function simple or complex or does my space contain simple or complex functions。

 it didn't matter if I have a function space consisting of 10 functions it' is not about whether these functions are simple or not I simply need to count these functions and maybe might need to find out how many different labelings can I realize with these functions。

😊。

![](img/a3aa905b74a6ef9755763340286a4684_38.png)

![](img/a3aa905b74a6ef9755763340286a4684_39.png)

but it's not about whether this is a simple function or not。

 whether it's a polynomial function with a small degree or a high degree。😊。



![](img/a3aa905b74a6ef9755763340286a4684_41.png)

![](img/a3aa905b74a6ef9755763340286a4684_42.png)

And now the question is whether theres a contradiction or whether it's sort of。



![](img/a3aa905b74a6ef9755763340286a4684_44.png)

Maybe it's just two different ways to look at the same thing。And that's really the question。



![](img/a3aa905b74a6ef9755763340286a4684_46.png)

And here I would like to ask you and maybe really ask you to lean back and take a couple of minutes and think about it so do you think that what we have proved in learning theory is a contradiction to Ohamsa。

😊。

![](img/a3aa905b74a6ef9755763340286a4684_48.png)

Or is it not a contradiction and no matter what you think。

 try to find a good justification for it and please do it for now and then you switch off the video and then you come back after a couple of minutes。

😊。

![](img/a3aa905b74a6ef9755763340286a4684_50.png)

![](img/a3aa905b74a6ef9755763340286a4684_51.png)

![](img/a3aa905b74a6ef9755763340286a4684_52.png)

![](img/a3aa905b74a6ef9755763340286a4684_53.png)

I want to offer you two explanations。😊，The first point of view that you could come up with is you could say。

 well， it's really not about simplicity。😊。

![](img/a3aa905b74a6ef9755763340286a4684_55.png)

And this is what I essentially already mentioned， so consider an example where you have a function class that contains 10 simple functions and 10 very complicated function。

😊。

![](img/a3aa905b74a6ef9755763340286a4684_57.png)

For the estimation error， it doesn't really make a big difference。



![](img/a3aa905b74a6ef9755763340286a4684_59.png)

嗯。

![](img/a3aa905b74a6ef9755763340286a4684_61.png)

So we don't really need the fact that functions are simple。😊。



![](img/a3aa905b74a6ef9755763340286a4684_63.png)

If we just want to prove， for example， a generalization bond。 So here it seems。



![](img/a3aa905b74a6ef9755763340286a4684_65.png)

That simplicity is maybe not really what we are looking for， right。

 and this is the one point of view。😊。

![](img/a3aa905b74a6ef9755763340286a4684_67.png)

Now， here's the other point of view。This is sort of the part of you that might reconcile these two different approaches。

In fact， it is true that points that consist of many simple functions。

Have typically are smaller than function spaces that consist of many complicated functions。

And I want to illustrate this maybe。😊，Just give the intuition with sequences of like assume we have say in a very simplistic setting we just have 10 data points and our functions just our binary labelings plus 1 minus-1 plus 1 minus-1 so our function our function space in principle consists of  two to the power of n many functions。

😊。

![](img/a3aa905b74a6ef9755763340286a4684_69.png)

![](img/a3aa905b74a6ef9755763340286a4684_70.png)

![](img/a3aa905b74a6ef9755763340286a4684_71.png)

嗯。And now， okay， so， so just a finite function space。



![](img/a3aa905b74a6ef9755763340286a4684_73.png)

And now， when would we call these functions simple and when would we call these functions complex？



![](img/a3aa905b74a6ef9755763340286a4684_75.png)

Typically we would call this function simple if there is an easy to describe pattern by which we can describe how this function looks like。

 for example， you could say all the first couple of points are zero and then the other couple of points are all plus one。

😊。

![](img/a3aa905b74a6ef9755763340286a4684_77.png)

![](img/a3aa905b74a6ef9755763340286a4684_78.png)

Or you have some way to describe the simplicity of a function space。



![](img/a3aa905b74a6ef9755763340286a4684_80.png)

And this is intuitively and then okay sorry the other way around。

 if you have a completely like if you toss some coins and then you assign your function labels according to the to course。

 probably there is no underlying pattern that you could exploit to describe these functions。

 this would be a complex function。😊。

![](img/a3aa905b74a6ef9755763340286a4684_82.png)

![](img/a3aa905b74a6ef9755763340286a4684_83.png)

And now if you know a bit about data compression， this is like this is really the point of data compression that like you could say a sequence of labels is simple if I can describe it in an easy way。

 this means I can compress it， I can instead of just like if a sequence is hard to compress I essentially need to write out what is the function on each particular point。

 but I might compress it and express it much easier。😊。



![](img/a3aa905b74a6ef9755763340286a4684_85.png)

![](img/a3aa905b74a6ef9755763340286a4684_86.png)

![](img/a3aa905b74a6ef9755763340286a4684_87.png)

![](img/a3aa905b74a6ef9755763340286a4684_88.png)

If I could just say the first five points are zero and the next five points or one。



![](img/a3aa905b74a6ef9755763340286a4684_90.png)

And in this sense， it is true that if you have a function class that can be described by by a small number of parameters。

 this function class tends to be sorry， tends to be small。😊。



![](img/a3aa905b74a6ef9755763340286a4684_92.png)

![](img/a3aa905b74a6ef9755763340286a4684_93.png)

So in the other way around， if you have functions that are simple。😊。

In the way that is meant by Ohamesa， say a polynomial of a small degree。

Then the function space associated with the space tends to be small。



![](img/a3aa905b74a6ef9755763340286a4684_95.png)

Because if it would be too complex， we wouldn't be able to describe it in such a simple way。



![](img/a3aa905b74a6ef9755763340286a4684_97.png)

And here is again， one more example in terms of polynomous。

So assume we have polynoms in one variable and we have just a discrete set of coefficients so our functions look like some over aKx to the power of k and say these coefficients are just finite many just for simplicity so if you look at degree 1 we just have 200 such polynomials。

😊。

![](img/a3aa905b74a6ef9755763340286a4684_99.png)

![](img/a3aa905b74a6ef9755763340286a4684_100.png)

Because I mean x like K is1 or D here is1， so we just have it in one power and then we have just we have 1200 choices like this these AK come from a space that is size 200 so we have 200 choices for aK and that's it。

Now if a polynomial has3 degree2， we already have2 to the 200 to the power of2。

 many choices because we will have two parameters to pick。😊。



![](img/a3aa905b74a6ef9755763340286a4684_102.png)

And if the degree increases， we have more and more parameters。😊。

And so we see that the number of functions in our space， at least in this particular example。

 grows quite dramatically。😊。

![](img/a3aa905b74a6ef9755763340286a4684_104.png)

![](img/a3aa905b74a6ef9755763340286a4684_105.png)

With the complexity if you would like， so this the space of polynoms of degree1 linear functions is much smaller than the space say of polynoms of degree 5。



![](img/a3aa905b74a6ef9755763340286a4684_107.png)

And now this is sort of the slide about compression I already made the example but maybe let's look again on the space on this slide。

 a space with few functions can be represented with few pits， so maybe it's just a lookup table。😊。



![](img/a3aa905b74a6ef9755763340286a4684_109.png)

![](img/a3aa905b74a6ef9755763340286a4684_110.png)

![](img/a3aa905b74a6ef9755763340286a4684_111.png)

So if you have five functions， you can just write down and look up here， what does this function do？

😊。

![](img/a3aa905b74a6ef9755763340286a4684_113.png)

Now， if you have a space that has simple functions， you can also represent it with few bits。

 for example， by adjust encoding one parameter。😊。

![](img/a3aa905b74a6ef9755763340286a4684_115.png)

![](img/a3aa905b74a6ef9755763340286a4684_116.png)

And if you have a space of complex functions， the function can do everything on all particular data points like you can have arbitrary labelings of your data points wherever they sit。

 then you cannot compress this function space and you have much， much。

 much more elements in your function space。😊。

![](img/a3aa905b74a6ef9755763340286a4684_118.png)

![](img/a3aa905b74a6ef9755763340286a4684_119.png)

I mean this is of course an intuitive argument but you can of course make this more precise。

 I simply don't want to do it here， but this is just to reconcile Oham's race and learning theory。



![](img/a3aa905b74a6ef9755763340286a4684_121.png)

![](img/a3aa905b74a6ef9755763340286a4684_122.png)

So what we now can say or what is the intuitive conclusion we can draw？



![](img/a3aa905b74a6ef9755763340286a4684_124.png)

Spaces of simple functions are small。

![](img/a3aa905b74a6ef9755763340286a4684_126.png)

Spaces of complex functions tend to be large， of course I can still construct a space consisting of10 functions which are very complex。

 but at least typically you don't just pick five complex functions but you have a full space full of complex functions and then the space tends to be large。



![](img/a3aa905b74a6ef9755763340286a4684_128.png)

![](img/a3aa905b74a6ef9755763340286a4684_129.png)

![](img/a3aa905b74a6ef9755763340286a4684_130.png)

Now learning theory tells us that we should prefer small function spaces。

 at least if we want to get the estimation error small。😊。



![](img/a3aa905b74a6ef9755763340286a4684_132.png)

And I think this is sort of the key reason， the key sentence on the slide。

 this often leads to spaces of simple functions。😊。

![](img/a3aa905b74a6ef9755763340286a4684_134.png)

So if you try to look at spaces of functions that would occur in practice like linear functions。

 polynoms， current functions。

![](img/a3aa905b74a6ef9755763340286a4684_136.png)

![](img/a3aa905b74a6ef9755763340286a4684_137.png)

Then these spaces tend to be small if the functions that you're looking at are simple in the other way around。



![](img/a3aa905b74a6ef9755763340286a4684_139.png)

![](img/a3aa905b74a6ef9755763340286a4684_140.png)

And so in this case， somehow outcomesham's Razor and learning theory are nearly the same。😊。



![](img/a3aa905b74a6ef9755763340286a4684_142.png)

So and okay， and you can， if you want there's a whole branch of learning theory that builds on this compression kind of principle and that's the principle of minimum description length。

😊。

![](img/a3aa905b74a6ef9755763340286a4684_144.png)

That was also quite popular maybe 10 years ago， so there's a whole book in this field by Peter Gwd from Amsterdam。

😊。

![](img/a3aa905b74a6ef9755763340286a4684_146.png)

![](img/a3aa905b74a6ef9755763340286a4684_147.png)

And now what is the bottom line， how can we now compare outcomesham's race and learning theory？



![](img/a3aa905b74a6ef9755763340286a4684_149.png)

So I think I mean the quantity that controls generalization is it is not really the simplicity。

 it's not directly the simplicity of a function， is the size of the function space but。😊。



![](img/a3aa905b74a6ef9755763340286a4684_151.png)

![](img/a3aa905b74a6ef9755763340286a4684_152.png)

Spacees of simple functions tend to be small。

![](img/a3aa905b74a6ef9755763340286a4684_154.png)

And then these spaces are good candidates for learning。

So the way I like to summarize this is oh comes race slightly misses the point。

 I mean it nearly got it right it said well we need to look at spaces of simple functions。😊。



![](img/a3aa905b74a6ef9755763340286a4684_156.png)

And learning theory says yes， yes， that's fine， but the reason is not that the functions are simple and that you shave off all these concepts that maybe are unnecessary and so on。

😊。

![](img/a3aa905b74a6ef9755763340286a4684_158.png)

But the reason is more hidden in these statistical principles here。😊。

And these spaces of simple functions are also function that learning theory would consider good。



![](img/a3aa905b74a6ef9755763340286a4684_160.png)

So in this sense Oham's razor is maybe not the principle that makes it correct。

 but when Oham's razor is true or when spaces of functions are simple then they tend to generalize good so in this sense Oham's razor is maybe。

😊。

![](img/a3aa905b74a6ef9755763340286a4684_162.png)

![](img/a3aa905b74a6ef9755763340286a4684_163.png)

Like a first approximation of what is really the ground truth and I mean you need to remember or come I think he was a monk in 1200 or so so this is already nearly 1 thousand00 years ago well maybe I'm wrong in fact I don't know maybe it was also 400 years later don't pin me down here but I mean this has definitely been stated much before anything about statistics or scientific principle it has been known so I think it is a very good first proxy but from a learning theory point of view。

😊。

![](img/a3aa905b74a6ef9755763340286a4684_165.png)

![](img/a3aa905b74a6ef9755763340286a4684_166.png)

![](img/a3aa905b74a6ef9755763340286a4684_167.png)

It is just not the right thing， but very close to the correct thing。



![](img/a3aa905b74a6ef9755763340286a4684_169.png)

Now this is sort of the end of the learning theory chapter maybe let's briefly talk about the outlook so obviously we have only scratched the surface I mean you could have whole lectures on learning theory there are conferences on learning theory and we just looked at the very classic regime binary classification for some of the algorithms like support vector machines or so that are out there。

😊，Now the one big thing that this part of learning theory cannot describe is why deep networks about work this has been or has been and is still puzzling for many people in learning theory so I mean it was around 2012。

 13， 1415 when it became apparent how good neural networks really are。

And also that the standard learning theory cannot be applied to these types of algorithms。

And I have a couple of reasons on this slide and again I mean I just have two slides on this topic。

 you can fill another lecture on what's going on in this field currently but I just want to give you some outlook。

😊，So what you can prove is that the function class that is induced by a deep network。😊。

Has a very high capacity。 So if you try to compute a shattering coefficient of a deep network。

 it's always going to be true to the power of n。You can trainre saying it the other way around。

 you can train a neural network in such a way given say some images。

 you assign random labels to your images and you can train the neural network to perfectly fit these random images。

😊，And this has in fact also been done， I think in 2017 or so there was this paper I believe by Joshua Benjo and some other authors really showed that and it was called like we need new tools and learning theory because look deep neural networks they can fit all labelings that I will put on a data set so this was the empirical proof。

😊，For something that has also proved has been proved theoretically that the capacity of the function class that is behind a neural network is so large that all the standard learning3 rebounds do not tell us it a trivial。

 so they are not going to converge to zero。😊，In particular， the digital networks。😊。

Also in practice are trained to overfit the data completely so it's not like like what you would do in early days of machine learning you might even really stop your algorithm I mean even if your algorithm has already or the training label is correct you might still continue to train your algorithm。

😊，And apparently performance still increases， so we fit like from the learning theory point of view。

 we completely do the wrong thing we overfit particularly on this one particular data set。😊。

But still， these deep neural networks are really good and in many， many cases。

 they do generalize very well。😊，So the question is really what goes on here。

The one remark I want to make is it does not mean that the standard learning series is wrong。

It just means that the tools that we have for standard learning theory are not the right tools to explain why deep networks work if you try to apply the tools of learning theory to deep networks they get trivial bounds so if you have this kind of generalization bounds the bound is never going to go to zero。

😊，However， it's not going to tell you that it can't be through the neural network work。

 you just need to have a different toolbox。😊，And now， I mean since the last five or so years。

 many people in learning theory are working in this field， it's a very widely open field。😊。



![](img/a3aa905b74a6ef9755763340286a4684_171.png)

How can you prove from a theoretical point of view。

 what is the learning theory that you need to prove why or to understand why did neural networks work？



![](img/a3aa905b74a6ef9755763340286a4684_173.png)

And this is really， I think it's not so much because people like so much proving theorems。

 there is a very fundamental question here。😊，And understanding the principles that lead neural networks to learn to learn。

Might have many positive impacts it might show us first of all， in which cases do they learn。

 maybe in which cases do they not learn， maybe we can simplify neural networks again once we know what is really the key criterion that makes these things learn。

 maybe we don't need this very complicated architecture， maybe something else。



![](img/a3aa905b74a6ef9755763340286a4684_175.png)

![](img/a3aa905b74a6ef9755763340286a4684_176.png)

Follow a similar principle but would be much simpler to implement and so on。So many。

 many people try to understand that。

![](img/a3aa905b74a6ef9755763340286a4684_178.png)

And I think the consensus is in many of these， I mean there is no solution yet。

 so this is really a field of research that is widely open。

 at least in this year 2020 might be that someone finds breaksthrough the next year。

 but right now it's still open。😊。

![](img/a3aa905b74a6ef9755763340286a4684_180.png)

![](img/a3aa905b74a6ef9755763340286a4684_181.png)

I think one of the key。Beliefs that are out there in the field is that there needs to be that the way we optimize these algorithms like this stochastic gradient decent。

 for example， has a big aspect in the fact。😊。

![](img/a3aa905b74a6ef9755763340286a4684_183.png)

Why neural networks work or don't work There are many interesting results out there。 for example。

 there are lots of results that say under certain circumstances maybe there are not even so many local optima each local optimum is already a global optimum so that might explain why neural networks。

😊。

![](img/a3aa905b74a6ef9755763340286a4684_185.png)

![](img/a3aa905b74a6ef9755763340286a4684_186.png)

![](img/a3aa905b74a6ef9755763340286a4684_187.png)

In terms of stochastic gradient descent don't end up in a local optimum。

 but in a very good potentially global optimum。

![](img/a3aa905b74a6ef9755763340286a4684_189.png)

There are also points of view more from a statistical side and I just want to give you one teaser out of one paper that I like and this is the paper by Michel Bekin and some other co authorss in PNS last year and where they talk about the double descent curve。

😊，And I briefly want to explain some the key idea of this paper so I have the figure here so on the left side here you see a figure that like the ones we had in the beginning of the lecture on the x axis you have the capacity of your function space so how large is your function class。

😊。

![](img/a3aa905b74a6ef9755763340286a4684_191.png)

And on the Y axis， you have the true error， the risk， the true underlying test error。

And then typically what we said also in the beginning of our lecture。

 I mean it's exactly this kind of plot， you have this kind of U shaped curve where you say well in the beginning if the function space is too small you severely underfi because your function class doesn't even have the potential to fit your data。

😊。

![](img/a3aa905b74a6ef9755763340286a4684_193.png)

![](img/a3aa905b74a6ef9755763340286a4684_194.png)

like then if you increase the size of your function class it gets better because you can have a smaller approximation error and then eventually it's going to increase again because your estimation error gets larger。

😊。

![](img/a3aa905b74a6ef9755763340286a4684_196.png)

Because you have the potential to overfit your data so strongly that in the end you're not going to generalize。

😊。

![](img/a3aa905b74a6ef9755763340286a4684_198.png)

So this is the traditional view。Of。Well， of machine learning theory。



![](img/a3aa905b74a6ef9755763340286a4684_200.png)

And maybe also here the dash line is the training risk like if you train a classifier。

 of course you can train more and more and you get a smaller training error and it gets smaller and smaller the higher my function classes and the trick is somehow you can train until you have training error zero because then you are already in this regime where you're overfitting so you need to stop at some point before and sort of the secret is always what is a good point to stop。

😊。

![](img/a3aa905b74a6ef9755763340286a4684_202.png)

![](img/a3aa905b74a6ef9755763340286a4684_203.png)

![](img/a3aa905b74a6ef9755763340286a4684_204.png)

![](img/a3aa905b74a6ef9755763340286a4684_205.png)

![](img/a3aa905b74a6ef9755763340286a4684_206.png)

So this is a traditional point of view， and here is now the new point of view。So now what happens is。

On the left part of this plot， we have exactly the sample plot as before。😊。

But now we see what continues if we if we keep on training our network。

 if we keep on increasing the function class。

![](img/a3aa905b74a6ef9755763340286a4684_208.png)

![](img/a3aa905b74a6ef9755763340286a4684_209.png)

And then the observation is， and this is， first of all an empirical observation that what happens is。

 I mean we first have this u shape， but then there is a certain point。😊。

Where if you keep on training your networks like and this is， for example， true in neural networks。

 if you keep on training。You overfit more and more。嗯。And then all of a sudden。

 the test error goes down again。And this is the thing that is really completely unexpected。

 like in learning through you would have said， well。

 this simply increases monotonically as long as you want to draw your X axis。😊。



![](img/a3aa905b74a6ef9755763340286a4684_211.png)

![](img/a3aa905b74a6ef9755763340286a4684_212.png)

What you observe in practice is now， well it's not true this and this is now called a double descent curve。



![](img/a3aa905b74a6ef9755763340286a4684_214.png)

![](img/a3aa905b74a6ef9755763340286a4684_215.png)

That has also been described in a couple of paperss。

 but in particular and the one that I'm citing here。😊，So you first have the first descent here。

 but then comes the second， the double descent。And what is happening here is this is what Misha Bakin always calls the interpolation regime because you have a function class that really interpolates your data and meaning you have training error0 so interpolation is if you try to find a function that exactly goes through the data points that you're given。

😊。

![](img/a3aa905b74a6ef9755763340286a4684_217.png)

![](img/a3aa905b74a6ef9755763340286a4684_218.png)

![](img/a3aa905b74a6ef9755763340286a4684_219.png)

SoAnd this is what happens in neural networks。😊，And then you can observe in practice that for some algorithms。

 you have this W decent。

![](img/a3aa905b74a6ef9755763340286a4684_221.png)

Of course， this is not true for whatever kind of algorithm you could come up with。

 there are a lot of algorithms for which this curve keeps on increasing。

 but there are algorithms out there and among them deep deep networks where you can observe this phenomenon。



![](img/a3aa905b74a6ef9755763340286a4684_223.png)

![](img/a3aa905b74a6ef9755763340286a4684_224.png)

![](img/a3aa905b74a6ef9755763340286a4684_225.png)

AndNow the idea is so what is going on here so here we are in this regime where the size of the function class is exponential so learning theory would tell you you cant like if you just do empirical risk minimization in this particular mode in this particular regime of your space of your function space and just pick any function that has approximation a like has estimate trainingarrow0 then you are going to overfi。

😊。

![](img/a3aa905b74a6ef9755763340286a4684_227.png)

And this statement is still true。

![](img/a3aa905b74a6ef9755763340286a4684_229.png)

But now what happens is， I mean， of course， like a function like a deep network doesn't go out and look at the function space and do empiricalist minimization in the sense that it just picks any function that has training error 0。

😊。

![](img/a3aa905b74a6ef9755763340286a4684_231.png)

![](img/a3aa905b74a6ef9755763340286a4684_232.png)

There are many， many， many functions that have training error0 because the capacity is so large and what happens now a steep network use a particular optimization algorithm in stochastic gradient descent with lots of heuristics and so on。

😊。

![](img/a3aa905b74a6ef9755763340286a4684_234.png)

To pick their function。And the conjecture that is currently out there is that the way in which this optimization works by some magic achieves that the function。

😊。

![](img/a3aa905b74a6ef9755763340286a4684_236.png)

![](img/a3aa905b74a6ef9755763340286a4684_237.png)

That is being picked by the deep network is a function that still generalizes。



![](img/a3aa905b74a6ef9755763340286a4684_239.png)

And so this is not a contradiction to learning theory。

 learning theory just says I mean there are many functions out there which would be really bad if you pick any function which has a zero training error most of them would be really really bad and we don't have generalization and the statement is now yes that's true。

😊。

![](img/a3aa905b74a6ef9755763340286a4684_241.png)

But the successful algorithms have some particular way of picking a function。

 and it is pretty much unclear still what this way is。 But for some secret hidden hidden secret。

 and they manage to pick a function。😊。

![](img/a3aa905b74a6ef9755763340286a4684_243.png)

![](img/a3aa905b74a6ef9755763340286a4684_244.png)

![](img/a3aa905b74a6ef9755763340286a4684_245.png)

That has your training error， and is good。

![](img/a3aa905b74a6ef9755763340286a4684_247.png)

And so looking at it from a capacity point of view。

 it says even though the space has a huge capacity。😊。



![](img/a3aa905b74a6ef9755763340286a4684_249.png)

The actual capacity of the space of function that the algorithm is actively considering is much。

 much， much smaller because by stochastic like intuitively by stochastic gradient descent you wouldn't be able to achieve many of these functions。

 it's just a small subset of space of functions in your space that could potentially be picked。

 say by stochastic gradient descent。😊。

![](img/a3aa905b74a6ef9755763340286a4684_251.png)

![](img/a3aa905b74a6ef9755763340286a4684_252.png)

![](img/a3aa905b74a6ef9755763340286a4684_253.png)

And this is why it might still work again。And some first results have been proved in also about certain function spaces and optimization algorithms。

 at least in simplistic regimes， we can prove that this is really the case。 And now， of course。

 the question is， can you prove it for deep networks or for which deep networks and so on and what are the kind of quantities that really control it。

 Is it really the key that we use schastic gradient descendcent or what is what are really the key ingredients。

 something like in learning like in the statistic regime for support vector machine like one of the key things is a margin of a kernels。

 there are certain like if you have a universal kernel that's very important。😊。



![](img/a3aa905b74a6ef9755763340286a4684_255.png)

![](img/a3aa905b74a6ef9755763340286a4684_256.png)

![](img/a3aa905b74a6ef9755763340286a4684_257.png)

So what are sort of the kind of quantities that are really the key thing that we need to make these two networks successful？

😊。

![](img/a3aa905b74a6ef9755763340286a4684_259.png)

So this is a really， really interesting area of research and it it's still widely open。😊。



![](img/a3aa905b74a6ef9755763340286a4684_261.png)