# 图宾根大学《概率和统计机器学习｜Tubingen Probabilistic and Statistical Machine Learning 2020》中英 p27 -27-Part 24 - Boosting.zh_en -BV1gso5YGE4s_p27-

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_0.png)

Now we want to look at a learning paradigm that's called boosting。

The background is again sort of more this kind of statistics inspired analysis where we try to have many versions of the same algorithm and hopefully the combination of all this algorithm helps us to improve the result。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_2.png)

However， the philosophy is quite different from random forests in random forests。

 the idea is we combine very often the same algorithm but on randomized instances， for example。

 we randomized the data or the dimension。😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_4.png)

And here the idea is we do not randomize over this data。

 but we have different versions of the algorithm applied to the same data。

 but the way each data point different weights。😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_6.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_7.png)

If you want to know about boosting， there's lots of literature out there it's again one of these classical algorithm that's been around already since 20 years or so it's covered in many textbooks。

 for example， in Sha Schwartz in Benndaavivi understanding machine learning in Hasti Tipshirani and there is also a whole book dedicated to boosting by Shapirian F。

 in fact it is a very wellreadable book I recommend to read this if you're interested in it maybe you don't need to read the whole book but maybe a couple of chapters and of course you can also look at the original chapter you can see by Shapirian F you can see it comes from 1995。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_9.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_10.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_11.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_12.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_13.png)

Now， the big philosophy that is behind boosting is the observation that there exists something like strong learners。

 but also something that is called weak learners。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_15.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_16.png)

The idea is， a strong learner is what we interested in the end。

 We want to have an algorithm that on a finite amount of training data hopefully achieves to learn a classifier that has a very small error。

 It is strong in the sense that the error as the sample size goes to infinity even goes to 0。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_18.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_19.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_20.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_21.png)

So as I've written here on the slide， intuitively a strong learner is a classification algorithm that can approximate the true solution up to a very small error epsilon。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_23.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_24.png)

The other observation is that there are many algorithms out there that might not be strong learners。

 but they can still do better than random guessing。 So for example。

 if you do something like I don't know one nearest neighbor classifier。

 it is definitely not going to be consistent， it might not be a strong learner。

 but still it may be thus better than random guessing。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_26.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_27.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_28.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_29.png)

And now this inspires a definition of a weak learner。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_31.png)

A weak learner is now an algorithm that is just slightly better than random guessing。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_33.png)

For example， if we have a classification problem with balanced classes so there are as many positive examples as negative examples and if you assume we use the 01 loss。

 then the random we learn is a classifier whose accuracy is just a bit better than random guessing。

 so the accuracy is 0。5 which would be random guessing plus some epsilon。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_35.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_36.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_37.png)

And this epsilon doesn't need to be large。😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_39.png)

And the idea is now of question。 The big question at that time was。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_41.png)

Assume you've given such such a weak learner。And of course， with one weak learner。

 you're not going to achieve a consistent learning algorithm because it's just a weak learner by definition。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_43.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_44.png)

But the question is， if you combine many weak learners， can you then。

 out of this combination generate a classifier that is a strong learner。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_46.png)

And the answer is going to be yes， and the algorithm that we are going to use is called posting。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_48.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_49.png)

So here's the outline。So as in our standard scenario we are given end training points x1 so we are in a classification or regression example in supervised learning。

 we have end points， input points， X input labels Yi。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_51.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_52.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_53.png)

And the boosting algorithm is going to be an algorithm that proceeds in T rounds。

 so in each of these rounds we are going to construct one week learner， one week classifier。

 for example， we are going to do this T times where T for time steps or so。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_55.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_56.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_57.png)

And after we've constructed these T algorithms， we do a final combination of all of them and produce a new hypothesis。

 which hopefully is a good strong learn。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_59.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_60.png)

In the beginning so and the key idea is that trading points have weights。

 so each trading point gets assigned a weight in the beginning， each point has the same weight。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_62.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_63.png)

But during the course of the algorithm， the weight of the training point changes。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_65.png)

These weights always going are going to be add up to one。

 So essentially it's a probability distribution over the data point。

 This is going to be important for the analysis later on。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_67.png)

Now in each round， we are given now the training set with a particular choice of weights and the choice of weights is being computed in the previous round。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_69.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_70.png)

So assume we have these training points and the weights。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_72.png)

Now， what we do is we train our weak classifier。😊，And the weak classifier is going to class like to output a classifier。

 and now we are going at to look at the training error of this particular classifier。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_74.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_75.png)

And now for each point， we can check like each training point。

 did the weak learner in this particular round classify this point correctly or incorrectly？😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_77.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_78.png)

If the point was misclassified， so the weak learner got it wrong。

 then we increase the weight of this particular point。 So in the next round。

 this point will have a higher weight。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_80.png)

And the other way around for a point that got correctly classified。

 we implicitly decreased the weight to have a lower weight。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_82.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_83.png)

And what we achieve by this procedure is that if there is a point that gets wrong in the first round。

 we increase the weight and then maybe it gets again wrong in the second round。

 but eventually it's going to be right because the weight of this point really increased a lot in each round we are going to increase the weights of those points which were classified wrongly so in some sense the algorithm even though it has a very like the individual weak learner isn't really great。

 it can only do like。😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_85.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_86.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_87.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_88.png)

It's a weak learner， so there's only a limited number of things that it can do。

 but at least it can focus。😊，On all of these training points that get wrong and eventually maybe one of these points also gets right。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_90.png)

And the point is if a weight of a data point is very like like if in the N there is one data point that always gets classified wrongly at some point it's going to have a weight that is much larger than 0。

5 in and then the weak learner has to get it right because the weak learner。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_92.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_93.png)

Is supposed to achieve a accuracy better than random guessing。 And if a point is nearly weighted one。

 then this point needs to be classified to correctly。

 otherwise the learner doesn't have a accuracy better than random guessing。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_95.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_96.png)

And so at the very end， the final classifier is a weighted some kind of weighted majority vote of all these wheat learners。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_98.png)

Let me illustrate this with a nice figure that's taken from the Shapirre front book。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_100.png)

So what we always see here is on the left side we see a data set。

 so this is going to be repeated a number of times over the last next couple of slides。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_102.png)

So on the left side we have a dataset set， it's called G1 because it's the first iteration。

 and you see minus and plus minus means it's a negative training point plus means it's a positive training point and the numbers here simply are the numbers like it's the index of the training point。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_104.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_105.png)

The size of these pluses and minuses is going to indicate the weight。

 So in this particular example we start in the first round， every point has the same weight。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_107.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_108.png)

And now we train we classifier and in this particular example we classifiers are simply splits in parallel to the coordinate axis so we could have a split like this or a split like this。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_110.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_111.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_112.png)

And say after the first round， we output a hypothesis which puts plus one like classifies the left side here as plus 1 and the right hand side here is minus1。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_114.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_115.png)

Now， what we see is there are three points that have been classified wrongly。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_117.png)

These are the points that have a circle around them。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_119.png)

We also see that the overall accuracy of this classifier is better than random guessing because there are two points here and five points here that have been classified correctly。

 so seven points have been classified correctly， three points have been classified wrongly。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_121.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_122.png)

So as a final test error， this wouldn't be great， but it's better than random guess。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_124.png)

This was the first round。 And now we are going to adapt the weights。

 So what is going to happen is we， we are going to increase the weights of these three points that have a circle around them because these have been classified wrongly。

 and we decrease the weights of everybody else。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_126.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_127.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_128.png)

And this is now what we can see here。 So now we see the data set as it now enters the second round。

 so it's called node D2。😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_130.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_131.png)

And we see here are these pluses， these were the three points which had been classified wrongly in the last round。

 and then we have the smaller pluses at minuses which are the points that had been classified correctly。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_133.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_134.png)

Now this is the data set。 we now apply our weak classifier。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_136.png)

The weak classifier， for example， spits out the hypothesis H2， which looks like this。

 So everybody here on the right hand side in the dark gray area is classified as plus one and everybody else here is classified as -1。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_138.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_139.png)

So this is now the next week hypothesis again we can see that there are like two。

 seven points that have been classified correctly and three points the three minuses here。

 which have been classified wrongly。😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_141.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_142.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_143.png)

So again， it's better than random guessing。😊，But， not great。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_145.png)

And now what we are going to do is we now update the weights in a formula which I'm going to explain at some point。

 but for now just take it so these minus points which have the circles around them have been classified wrong me so they get a higher weight and everybody else gets a smaller weight。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_147.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_148.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_149.png)

Now， what we see here is now here in its now the third iteration D3， that is it 3。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_151.png)

We have the three minuses here which are the points that called classified wrongly in the previous round。

 then we have these tiny pluses and minuses。 These are the points that have already been classified correctly twice so they have a very small weight and then here these classeses have a moderate weight because in the round before the previous round they had been classified wrongly so their weight had been increased once and now be dequisite again。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_153.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_154.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_155.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_156.png)

Okay， so that's our new data set。😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_158.png)

We train our weak classifier。 it produces this hypothesis。 So everybody on the top here。

 like in the darker area is plus everybody below is classified as minus and now we can continue like this。

 but assume we stop there。 So capital T is 3， we wanted to train for three rounds。

 Now we need to have a combination to to generate our final hypothesises。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_160.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_161.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_162.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_163.png)

And in this case， there is a nice illustration。 So what we do is we now essentially do a weighted combination of the three classifiers。

 So these three boxes here indicate the three classifiers that we've seen in the first round and the second round and in the third round。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_165.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_166.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_167.png)

And here are the weights。 And for now， you can't really know， sorry。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_169.png)

Here， for example， we have 0。42 and you for now you don't know where this weight comes from。

 it comes out of the algorithm and we are going to see how this works。

 but for now simply take it as effect fact we add some weight。

 It is something like an estimate of the training or of the training error here。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_171.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_172.png)

But with some weights。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_174.png)

嗯。And then we get a final classifier， which is the linear combination of the three。

 So and this is how it would look like it would put these dark areas are always being classified as plus one。

 the light areas would be classified as -1。 And you can see that in this toy example at least the final classifier。

 which is this linear combination。😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_176.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_177.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_178.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_179.png)

It gets every point correctly。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_181.png)

And this， I think， is the figure that you should have in mind if you。

 if you want to think about what boosting is。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_183.png)

Now， let's look at a couple of remarks。Here are some remarks that compare boosting to the Re forest。

 And as I said in the beginning。As opposed to like in random forests。

 we generate this randomness through the subseling of the data points or the subseling of the dimension。

 or for example， if youre in comparison based random forests by the subseling of the pivot points，😊。

In this particular case of boosting， we never change the training set。

 It's always going to be the same set。 but what we do is we have weights on each training point and the weights are going to to be changed from round to round。

And the intuition is， as I said， by reweighting points。

 the algorithm can focus on those examples that it find difficult。

Or maybe an aspect that have been overlooked so far。

 like if you want to be a bit more in the interpretation kind of side。

And the idea is now by the definition of a weak classifier once a point has accumulated weight or probability mass is larger than 0。

5， the weak algorithm will get it right at least on average。😊。

Because otherwise it it cannot have this average classification error a bit better than random guessing。

But now the point is， of course， like， it's clear that by reweight by reweighting data points。

 eventually， there's this one guy that always gets wrong。😊。

And it gets no such a high weight that in the next round， it might be classified correctly。😊。

But of course， there are like maybe 1000 data points。

 And now I can't train 1000 classifier and then hope that the weighted linear combination is going in the end to get everything right。

 So， of course， I can can construct a classifier that gets this one particular data point correctly。

😊，But now the question is really， why does this combination of all these individual classifiers and why this linear combination I take in the end。

 why does it again， Why does it really work。Why do I get a strong classifier。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_185.png)

Before I'm going to go into a couple of theoretical results。

 and let's now really look at the the pseudocode of the algorithm。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_187.png)

So this pseudo code is taken from the book Understanding machine learninging。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_189.png)

So this， oh， by the way， I forgot to tell you the algorithm we are now going to look at。

 It's called other boost。 There exists many， many， many different variants of boosting algorithm and other boost is sort of the baseline algorithm。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_191.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_192.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_193.png)

That has all the ingredients you need。 And then you can sort of start on tweaking it and changing different aspects and so on。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_195.png)

So the input of our algorithm is a training set called S consisting of points x 1 y1 to xM， YM。

 so M in the pseudocode is the number of sample points。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_197.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_198.png)

We have a function that is a weak learner。 later we can call this function。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_200.png)

WL， weak learner。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_202.png)

And we have the parameter， which is the number of rounds that we want to train our algorithm。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_204.png)

Capacity。Then we are going to have weights and these weights are called D in the pseudocode。

 so data 1， data 2， data 3 and so on， or distribution 1 distribution 2 distribution n。

 I don't know what the letter D， Y it has been chosen， D， maybe its distribution。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_206.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_207.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_208.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_209.png)

And in the beginning， every point， So you have like M numbers， you have M points。

 and each point gets the same weight， one over M in the initialization phase。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_211.png)

These weights are always going to add up to one。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_213.png)

Now we have a four loop that runs for T steps because this is the number of rounds that we want to do。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_215.png)

And in eachron， we do the same。 So we are now given the training set with the current weight vector。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_217.png)

D so and then we call the weak learner on the data set with these weights。

 so here we have the weak learner applied to the training set S with the weights Dt。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_219.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_220.png)

And the weak learner outputs a hypothesis or a function， if you like， that is called HT。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_222.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_223.png)

What is important here， and I made this is a hand notation to the code that the weak learner。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_225.png)

It gets the weights for， for the sample points。 So it should better be a weak learner that also takes into account weights。

 So if you have a can nearest neighbor classifier， for example。

 then maybe when you compute the sum like the， I don't know。

 the majority board of your can nearest neighbor， you might want to take into account the weights of your data points。

 for example。 So if you completely ignore these weights。

 then probably this algorithm is not going to work。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_227.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_228.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_229.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_230.png)

So we have a weak learner that takes into account training points and weights and spits out a hypothesis H。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_232.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_233.png)

Now what we do is we compute some error called Epsilon T and this is essentially the weight to 001 loss so here the characteristic function simply checks for each data point training point whether the current hypothesis HT got the correct prediction or not。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_235.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_236.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_237.png)

So it's a 01 loss and we have these weights in the sum of the 01 loss so we compute the weighted error where the weight of each point is the contribution to the error。

 So if there is a point that has a very high weight。

 then this point like if we get this point correctly it's fine but if we get it wrong we already get punished by a high amount of error。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_239.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_240.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_241.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_242.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_243.png)

Now we compute a factor W2， which is going to be used to update our weights in the end。

 so W2 is just a number。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_245.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_246.png)

Which is been defined in this way， it's sort of you don't really see right now why why it has been chosen this way。

 this is simply what comes out the math。 If you do the calculus and the math， how you。

 how you should derive this iron。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_248.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_249.png)

So it's1 half lock1 over Epsilon t minus1。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_251.png)

This is the update factor which we are now going to use in the next line because in the next line we' are going to update the weights of each data point。

 so each data point I now gets a weight t plus 1， so this is the iteration counter now gets updated so we look at the weight in the next round。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_253.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_254.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_255.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_256.png)

And essentially， if you look， it's， it's a fraction and on on the。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_258.png)

唉。Enummerator， we have the old weight times a factor e to the minus。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_260.png)

And then Y I H T of X I is plus 1 or -1， depending on whether you get your your classification result is correct or not。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_262.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_263.png)

And then you have this WT， which is the weight， the update weight。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_265.png)

And then you need to normalize this in the denominator。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_267.png)

So if， if you look at these weights， what you can see is if the point gets classified wrongly。

 these weights are being。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_269.png)

Are beinging increased because then Y I times H T of X I is going to be negative。 So。

 but I have this minus sign here in in the front of this as well。

 So then the whole thing is going to be something positive。 So I take E to the something positive。

 So this is going to increase。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_271.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_272.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_273.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_274.png)

And then here well and and maybe the other way around if if a point gets classified correctly。

 I mean， first of all， then this term is going to be really really small。

 and in the end theyre auto normalize such that the the whole weight of the like all weights add up to one。

 So if I increase the weight for the examples that have been misclassified implicitly I need to decrease the weights for the points that have been correctly classified because otherwise it can't add up to one anymore。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_276.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_277.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_278.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_279.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_280.png)

Okay， so this is now the new weights and now。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_282.png)

And that's sort of the end of the for loop。 So this is what we do T times。

 So in each in each round we get the weights， we get the trading points， we train or we classifier。

 we check which points have been classified correctly and not or not， and then we update the weights。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_284.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_285.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_286.png)

And we keep on doing this until we have finished two rounds。

 and then we output the final hypothesisthe。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_288.png)

Hypothses， sorry the the last one， which is now we take simply a weighted linear combination of all the hypothesisses we've generated before。

 So H lowercase t is the hypothesis that has been generated in round t and with some of all these hypotheses。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_290.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_291.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_292.png)

And each hypothesis is included with the weight as it's being computed here in this update factor。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_294.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_295.png)

And in the end， we simply check is like this final sum， has it a positive or a negative sign。

 and this is now what we use as the output of our final hypothesis， it's again plus 40 -1。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_297.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_298.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_299.png)

So as you can see， this is really a simple algorithm。😊。

And I think the sort of whole mystery lies in why does it really work now and why did we choose these update rules and on exactly the way it has been chosen here？

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_301.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_302.png)

And this is something that comes out of the mass in the end。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_304.png)

That and were not going to see a bit of that， at least。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_306.png)

Maybe before we go into the math， let's look a bit at the intusion。

 so why is it plausible that it works？😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_308.png)

So assume that the final classifier HS makes an error on some training point。

 so what we want is that there are only few points on which the final hypothesis is going to make an error the final classifier is going to make an error。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_310.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_311.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_312.png)

And now I am just going to talk about the training error for this intuitive slide。

 So assume there is a point for which it makes an error。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_314.png)

We know that this fan classifier is a weighted majority votes over all the tea classifiers that we've seen before。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_316.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_317.png)

If the final hypothesis put spits out an error here or generates an error。

 this means that many of these intermediate like of these weak classifiers have to need to be wrong as well because like in the end I predict something like a weighted majority vote。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_319.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_320.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_321.png)

So if I want that this we majority vote is wrong， then many of these individual we classifiers need to be wrong as well on this particular point。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_323.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_324.png)

So intuitively， this final classifier get can get x wrong only if most of the weak classifiers also got it wrong。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_326.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_327.png)

Now， but this means by the mechanism of this algorithm， there are many， many。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_329.png)

Iterations for which the weight of this particular data point got increased because whenever we classifier gets it wrong in the next round。

 the weight is being increased。😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_331.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_332.png)

So this means that the weight of this training point that got classified wrong in the end。

 also in the end of the algorithm and terminates， probably is pretty large because it didn't happen that it always got decreased because there were so many step where it also got increased。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_334.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_335.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_336.png)

So this particular point， x must have a large weight after the final training round。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_338.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_339.png)

But now the point is all these weights add up to one。

And it can't be that everybody has a large weight because in the end they need to add up to one。

 so there can be only few points which have a large weight， otherwise the weight would go beyond one。

 so there can only be few points which have a large weight。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_341.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_342.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_343.png)

This again， means that there can only be few points on which the algorithm really made a mistake and after the final round。

 because otherwise the solar mechanism would break。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_345.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_346.png)

Okay， so this is the intuition for at least why the training error should be small on most of the data points and the final classifier should get most of the training points correctly。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_348.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_349.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_350.png)

Now of course we can also prove that theoretically and on this in the next slide I want to discuss the result on the training error because it is surprisingly simple and surprisingly elegant。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_352.png)

So let's look at this particular heorem， which is again taken from this book understandingstanding machinechine learning。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_354.png)

So S is our training set。And now suppose that at each iteration of other boost。

 the weak learner returns a hypothesis for which the error of this hypothesis at round T。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_356.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_357.png)

Is smaller than one half minus gamma， so we are now not talking about the accuracy。

 but about the error。 so a weak learner needs to produce a hypothesis whose error is smaller than when guess。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_359.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_360.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_361.png)

And we， we consider a balanced design。 So random guessing would be one half。

 So the error is a bit better than one half。 and the amount by which it is better is called gamma。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_363.png)

And now observe you the statement， this is the training error and it is not something like on average the algorithm produces a hypothesis that has these kind of characteristics。

 but it says now this is a theorem that really says assume，😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_365.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_366.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_367.png)

Like we run the algorithm and we observe that at each iteration。

 it really achieved this training error that is better than by by gama than random guessing。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_369.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_370.png)

And the statement is， if that has happened， then the training error of the output hypothesis。

 so the final hypothesis of error boost。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_372.png)

I is most this expression here？

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_374.png)

So this is sort of the training error of hypothesis like LS here in this mutation is the training loss on the training sample of this final hypothesis HAs。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_376.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_377.png)

Is and this is now measured。 I mean， it's made explicit here。 This is simply the01 loss。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_379.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_380.png)

Off the final classifier on the training set。And this is found that this is not the key term by e to the minus 2 gamma square t。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_382.png)

And no is this something good or something bad， What you see here is， I mean。

2 is a constant gamma is a constant that sort of says something about the accuracy of this algorithm and T is the number of round。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_384.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_385.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_386.png)

So what you can see is if you increase the number of rounds。😊。

Then this error decreases exponentially fast。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_388.png)

And this is really cool， right， it says at least if I manage that my weak classifier in each round produces a classifier that is a bit better than random I'm guessing。

 then after capital T rounds， the overall accuracy of my final hypothesis is really， really good。

 So this looks like a strong learner because in the end of T， I mean， if T is a large number。

 I can drive this error as small as I want。😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_390.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_391.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_392.png)

Of course， I mean， contemplating this statement a bit further。

 this only talks about the training error。😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_394.png)

It doesn't say anything about the test error。This is a different kind of result that we would need here。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_396.png)

And it also only holds if really in each iteration we manage to have a hypothesis that is better than random guessing it wouldn't the theorem wouldn't hold if there is one iteration in between where maybe for some weird reason the we learn achieved only a hypothesis that is worse than random guessing or exactly 0。

5 so we need to have this algorithm that at least on is a bit better than random guessing in each individual round of our training algorithm。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_398.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_399.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_400.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_401.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_402.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_403.png)

Okay， so now thats the statement and it looks like this should be something that is really complicated to prove。

 but in fact， the proof is surprisingly simple and surprisingly elegant。

 so I want to present it here。😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_405.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_406.png)

The proof proceeds in a number of steps and if you want。

 you can also read it up in the book by Sha Shah Svatz and Sha B Davidavid。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_408.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_409.png)

Understanding machine learning， I just sort of rewro it a bit to make it a bit more accessible。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_411.png)

So I， I converted the proof into a number of steps。

 The first step is we now look at this global function that has been learned after step T。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_413.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_414.png)

And we define a convenient retina problem。 So let's look at this。

 So we now define the function at point T。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_416.png)

So after lowercase t rounds， we define this function FT。

 which is just the weight that like the majority word of the existing hypothe where w is this weight that we have in the other boost I。

 right？😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_418.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_419.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_420.png)

So the output of the final algorithm is F capital T。 So we stop after capital T rounds。

 and this so this is the the hypothesis that is being output after capital T rounds。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_422.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_423.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_424.png)

Now we define a random variable， CTt。Which is defined as this quantity。

 So it's a sum of our drilling points。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_426.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_427.png)

Of e to the minus Y， I F T of X I。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_429.png)

And for now， you don't see why we define this random variable we define it this way because this is where we want to end up at the end。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_431.png)

Im observedserv here Y IFT of Xi。The sign of this of this term already tells you whether the point。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_433.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_434.png)

X I has been classified correctly or not by function F T。And so。

 so sort of this is something like a term that measures the loss of class of the function F T on。

 on all the training data from one to M。 So this is called Z T。 It's just not a01 loss。

 It's a slightly different loss function。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_436.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_437.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_438.png)

And now why did they choose this loss function？😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_440.png)

Here's the justification。 Now， what we're really interested in is the 01 loss function， but now。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_442.png)

We can compare the01 loss function to this other loss function that they use here。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_444.png)

So here we have the 0，1 dose function， which is simply 0 if it's correct and one。

 if it's not correct。 And now'll observe this function here。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_446.png)

Y times h of x， if this is plus 1， then the result is 0。3。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_448.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_449.png)

So， if， sorry。If y times edge of x is  -1。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_451.png)

No if y and the h of x have the same sign。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_453.png)

Then the guy has been classified correctly。Then the term here is plus1。

 but we have a minus in front of it， so it's minus1， so we have e to the minus1， which is 1 over E。

 which is about 。3。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_455.png)

And if the function classified at this point incorrectly， then y has a different sign than h of x。

 So this term here is negative and so y times h of x is negative。

 So minus y times h of x is positive。 So this is a number that is positive plus1 E to the plus 1 and this is e and that's about 2。

7。 And if you now compare 0 is smaller than 03 and1 is smaller than 072。7。

 So this function that we have on the right hand side is a point was upper bound to the loss that we have on the left hand side。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_457.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_458.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_459.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_460.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_461.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_462.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_463.png)

So what we can conclude from this is that the training error of the final function F capital t。

 the 01 loss。😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_465.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_466.png)

It can be up bounded by this variable Z Z capital。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_468.png)

Okay， so this is why we introduced this variable which we now managed to bound the loss function，0。

01 loss function by this exponential loss function here。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_470.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_471.png)

And then we can bound the 01 loss of the final function by z capital T。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_473.png)

Okay。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_475.png)

Now the question is what we now want to do is the theorem wants to make a statement about the training error。

 so if we manage to bound the variable ZT by something else and this something else is what we have in the theorem then we are done so now we need to bound as ZT。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_477.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_478.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_479.png)

This happens now on this slide。 So now the trick is we use some kind of telescope on。

 So we want to bound the random variable Z T。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_481.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_482.png)

It should be maybe a capital T here。And the trick is as follows。

 so we start with the random variable CT。😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_484.png)

We observed that CTt can be also written as CTt over z0 because in iteration 0 we simply define this random variable 1。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_486.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_487.png)

Now you can write a telescope somewhere where Zt over 0 and you always introduce this terms Zt minus1 here and here。

 and then Zt minus2 and so on until the very end， C1 over z0。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_489.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_490.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_491.png)

So you simply express the simple term CT by a telescope sum by these manufacturer factorss。

 which always just decrease the index by one。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_493.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_494.png)

Now the idea is that while it is difficult to bound the first term like just Zt over z0。

 it is now easier to bound each of these consecutive terms， Zt plus 1 over Zt。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_496.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_497.png)

And what we want to show is that each of these factors is smaller or equal than e of the minus2 gamma squared and then observe we have t such factors and it's a product so then we get this factor t in here and this is what we need to have in the theorem。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_499.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_500.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_501.png)

Okay， so now we want to show this particular bound that Zt plus 1 over Zt is smaller equal than e to the minus2 gamma squared。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_503.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_504.png)

嗯。And this happens now in step 3。 And it's here on the next slide。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_506.png)

And this can be proved by induction。 And here this is the only place on the slides where I by very shortened of it。

 theres there's more computations in the book if you want to read it up in the understanding machine learning book。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_508.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_509.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_510.png)

And this will be proof by induction so what you can prove is now you need to look at these weights。

 the I at the iteration T plus 1， they have this particular form。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_512.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_513.png)

This is the formula that we have in the pseudo code of other boost。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_515.png)

And now exploiting this particular weight， you can now look what happens to Zt plus 1 over ZT。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_517.png)

嗯。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_519.png)

And what you can prove in a couple of elementary computations that's what I wrote on this slide is that each of these factors is smaller than two times squared of and then comes epsilon t plus 1 times 1 minus epsilon t plus1。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_521.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_522.png)

Where Epsilon T plus1 are these arrows that we also have in the other boost。

 Like it's the formula this weight that we that we compute in the in the other boost algorithm。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_524.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_525.png)

In these couple of elementary computations， of course。

 sometimes it's not too easy to find them if you don't know what these are， but you can。

 if you're really interested in reading it in the books， it's really simple。

 This is really elementary computations and it's just a few steps。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_527.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_528.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_529.png)

I just didn't want to put all of them on the slide。

And now the last step is that you can observe that this particular expression can now be bounded by what we are interested in namely by e to the 2 minus gamma squared。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_531.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_532.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_533.png)

And this essentially happens， I mean， you to a bit of you exploit that epsilon T plus1 is smaller than1 half minus commmma。

 This is the assumption that we have。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_535.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_536.png)

Because we have a weak learner。And then sort of you can plug this in here， do a bit of mass。

 end up with the square root term， and this can now be bounded by e to the minus2 gamma squared。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_538.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_539.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_540.png)

And then you're there。Okay， so again， this is just。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_542.png)

This is just。elementleementary computations。 And then we are there because now oh here， step 4。

 we have it combining everything。 We know that the training error。 So from now we start from。

 from the very beginning of the proof。 The training error of F T is bounded by this variable Z T。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_544.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_545.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_546.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_547.png)

We expanded this variable of Zt in the telescope sum by this product of Ct plus 1 over Zt。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_549.png)

We proved that each of these factors is bounded by e to the minus2 gamma squared。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_551.png)

And because we have T such factors， we get a power of T so we can take the T inside the exponential function。

 and then we're done。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_553.png)

Okay。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_555.png)

So this is the proof。And what I find cooler about this proof is it's really elementary。

 There's nothing that is really secret。 Of course， the proof only works because we chose these update weights。

 and so on exactly in such a way that all this works out。

 So to find this in the first place is really not obvious。 But once someone tells you this is。

 this is what we are doing， then the result just uses elementary mask。 So it's really， I like it。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_557.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_558.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_559.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_560.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_561.png)

Okay so what we have seen now this was a result for the training error。

 it just said if you really managed to have a hypothesis that in each individual step of your iterations produces a function that is a bit better than random guessing。

 then your final thing is going to be a strong classifier， at least intuitively。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_563.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_564.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_565.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_566.png)

Now， of course， this only talks about the training error。

 The interesting thing is really what happens to the test error。 And again。

 this is not obvious at this particular point in time that when the training error decreases that the test error also decreases。

 it might just be that this smooth thing does something very weird adaptive to the training points。

 but it doesn't really generalize to any new test points。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_568.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_569.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_570.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_571.png)

The the point is now you can of course prove all these results and this like 20 years ago this was a very active area of learning theory to prove a number of generalization bounds for boosting and the techniques that are being used are some of the standard techniques that are also used in like from statistical learning theory。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_573.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_574.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_575.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_576.png)

And using these standard techniques， for example， margin based bounds also like looking at function classes。

 looking at typically concepts， uniform conversions， and so on。

 you can prove generalization bounds for these type of algorithms。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_578.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_579.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_580.png)

Now I don't want to present this in the lecture because I consider boosting just as sort of an excursion to the lecture。

 but if you're interested in check out the book by Shapir in front，😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_582.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_583.png)

This is really as I said， it's well written。 you can read that with the background you have and it contains many of the results like from the learning theory point of view on the generalization error of posting。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_585.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_586.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_587.png)

Now， of course， the question in practice is， which are the weak learners that you tend to use in practice and now。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_589.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_590.png)

And the other question is， does it really work in practice， I mean。

 it sounds very nice from a theoretical point of view。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_592.png)

But there are some algorithms that really sound nice from a theoretical point of view。

 but yet in practice don't work so great。😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_594.png)

This is one of the class of algorithms that tends to work great。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_596.png)

As weak learners people often use what is called decision stampumps。

 so you just have a decision tree of level which essentially just has height one。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_598.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_599.png)

So for example， you could use something like these excess parallel splits as we had them on the very very first slide。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_601.png)

We you just say you try to find a split either vertically or horizontally or in along any other of your dimensions of your dataspace。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_603.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_604.png)

You try to find such a split。 And this is what you use as your weak learner。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_606.png)

The idea is， of course that these weak learners need to be algorithms that are considerably simple。

 so it doesn't really make sense so much to train a support vector machine for each of these weak learning problems。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_608.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_609.png)

Because the idea is we want to exploit the fact， I mean， also from a computation point of view。

 we need to do this often we need to have T rounds and T can be large。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_611.png)

So each of these individuals things should be relatively easy。

 and then we do a linear combination in the end， which is also easy。😊。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_613.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_614.png)

As I said， there are many， many variants of posting or there I just showed you the very basic vanilla algorithm if you're interested in check out the literature。

😊。

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_616.png)

And sort of the bottom line is boosting is really well understood from both from theory and from practice and it tends to work well in practice。

 so this might be an algorithm that you simply could consider if you have learning problems maybe not for image recognition。

 but for other problems you also have interpretability in the end， for example。

 if you use decision stamps， each of the weak classifiers is reasonably easy to understand what it does and then you can also try to。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_618.png)

Genral write explanations for what the linear combination of these simple algorithms do。

 So in this sense， it's also an algorithm that is really good to have Its a baseline algorithm and use it in your toolbox whenever you have a machine learning problem to solve。

 consider looking at boosting ones， try it out。 And then if it works。

 at least you have some kind of baseline and on which you can build。



![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_620.png)

![](img/7ca3c724f7ebf876f7ea9bb88f3154bc_621.png)