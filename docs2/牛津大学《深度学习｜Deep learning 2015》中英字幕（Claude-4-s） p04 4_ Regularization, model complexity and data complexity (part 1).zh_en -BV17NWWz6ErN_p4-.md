# 牛津大学《深度学习｜Deep learning 2015》中英字幕（Claude-4-s） p04 4_ Regularization, model complexity and data complexity (part 1).zh_en -BV17NWWz6ErN_p4-

Okay so。In this next lecture we will move on to do more interesting things so so far we've been doing this boring task of fitting a line to point and we've looked at two views of fitting the line。

 the loss view， which is you minimize the loss and the probabilistic view which is exactly the same thing but where we maximize probability so we maximize the likelihood of the data for model parameters and that's the same as minimizing the differences in relative entroies between the two。

 minimizing the。The information of the data produced。

 the difference between the information produced in terms of information of the data produced by the model and the data that comes from the world。

So now what I want to do is move on to talk about one problem that was pointed up in the previous class。

 which is what happens when you have very vertical points and in fact this is going to become even more interesting when we have not lines but we have arbitrary nonlinear functions because then we'll see that maxim likelihood is actually flawed。



![](img/f1beacab783349bf3bffbe6341618ad2_1.png)

![](img/f1beacab783349bf3bffbe6341618ad2_2.png)

In itself and willll introduce the concept of regularization as a way of fixing the flow and regularization by itself is also poorly posed to Npa's problem when you combine all these you get a reasonable answer。



![](img/f1beacab783349bf3bffbe6341618ad2_4.png)

And I'll get into more details about it and what I mean by ill positiveness。

We're going to look at polynomial regression we' not just doing a line。

 but we do quadratics and third order polynoms and so on。

 so we start looking at more interesting data and in fact I will introduce the concept of basis function。

And just to sort of set up the scene here， a neuron in our artificial models of what we call neural networks is nothing but a basis function。

 and when we're constructing these models of images and so on。

 what we're doing is we're using compositional，Basis functions。

 compositional representations of these simple basis functions。

 and you should think of a basis function as a brick。If you know how to build a brick。

 concrete brick， and you have some glueutd stick bricks together， you can build everything。

 you can build a city of London， you can build maybe not with a charm because it has all sorts of different kinds of bricks and on。

 perhaps even not brick， but you can build a lot of things so you have that basic thing。

Basic piece and that piece you will be able is like I guess a better analogy a leg of piece and imagine that you can stretch this leg of piece。

 stretch it with or its height or its depth and so if you have all these degrees of freedom in a break you can then start building all sorts of structures this is how we construct neural networks with these basis functions。

When you do that， we will find that this gets us into trouble because we can come。

We can build arbitrary complex functions。 That means that we could find an explanation for anything。

 but that explanation could be wrong。And so the essential thing now is now we'll become one of when is our model right。

 we've built the structure， it's telling us this is the answer， but is that the answer。

 how do we test that we're getting the right answer and that takes us into cross validation。And。

Related to this as the concept of generalization， if the model does well in this data that I've encountered so far。

 how will it do on the data that I will encounter tomorrow so basically I measure all the stock values up to today。

 I fit this beautiful polynomial with the technique I learned in today's class using torch and then I use it to predict this stock prices tomorrow how do you know your prediction is sensible。



![](img/f1beacab783349bf3bffbe6341618ad2_6.png)

I don't advise you to do that。Just in case so one of the problems that was pointed out is vertical distances are problematic and in fact。

 if you have vertical distances， another way to think about this is when you compute the least qua estimate。

 which is the same as the maximum likelihood estimate。We end up with this issue。

 we have to invert this matrix。That computation is non trivial because if you have。

 so remember that the matrix x is n by D。And so this whole matrix here is D by D and I think in your homework exercise I gave your way。

 which you could do some linear algebra brain， you could rewrite this in terms of a matrix that's n by N because sometimes you have n equal two patients with d equal 20。

000 genes and so it's much easier to invert a 2 by 2 than a 20，000 by 20，000 matrix。



![](img/f1beacab783349bf3bffbe6341618ad2_8.png)

It's a very useful trick， by the away。Coming back to this， even if D is the lowest dimension。

 inverting this D by D matrix is sometimes problematic because quite often this matrix for real data will have very low eenvalues。

 eigenvalues are0， and so this bombs out， your code crashes。嗯。

And so one of the solutions that folks came up with was to add the proper way to do this is usually one of the proper ways to deal with this is to replace X by the SVD as you did in your homework and then to truncate it only up to the rank of the matrix and then you use the SVD to invert。

 that's one way to do it and packages will automatically do this for you behind the scene sometimes but it's important that you're aware of this。



![](img/f1beacab783349bf3bffbe6341618ad2_10.png)

Another way that folks figured out around this is let's just add a diagonal。

 so this is the identity matrix here。So the matrix that has ones in the diagonal。

 so in 2D would be like that。And so I multiply each element of the diagonal by this variable delta and I've squared it to emphasize that it's positive to keep it positive。

 so I add a positive number to the diagonal and that solved the problem。And then folks figure out。

 oh wait， we're getting better answers for if we pay attention to how we set Delta。

 we actually get better answers， not only how we fix the computational problem。

 but actually the statistical problem is now better behaved。😊，And this was like in the 7s。

 this was like a mystery。And so a lot of statisticians studied this and this actually led to several papers and things called a spine effect and so on。

 but we're not going to go into that。But we're going to analyze why it could be better。

So the first thing is we can reverse engineer this and I will claim that this is the loss function that what we did is we took the quadratic loss and we added to it a penalty。



![](img/f1beacab783349bf3bffbe6341618ad2_12.png)

Okay， so now this is telling us fit the line。

![](img/f1beacab783349bf3bffbe6341618ad2_14.png)

This and for the line， by the way， we I didn't make that in detail here because I wanted to keep the notation simple。

 but typically we will not penalize the height of the line。

We will only penalize the thetaus that correspond to the slope。

 so I will only put the thetaus that so I don't penalize this factor here usually wouldn't involve the first theta。

 but even if you throw in the first theta probably。



![](img/f1beacab783349bf3bffbe6341618ad2_16.png)

![](img/f1beacab783349bf3bffbe6341618ad2_17.png)

And practice would be okay。 One of the things we often do as well is when we get data。

 the first thing we do is we。Subtract the mean of the data。

 so we shift the points all to have zero mean， and then you can apply this to all the the because there's no longer a mean to learn。

You have to be a bit careful when you do that， but that's one way of doing this。

 and we call that process widening。嗯。Now。What this is saying is。Don't go for lines that are vertical。

RightBecause they say keep the slope small， keep theta small， if theta is large you pay a large cost。

 so keep the theta not vertical because as was pointed out earlier。

 that can be problematic because then your likelihood is， well then you minimize the loss。

 in fact you get a likelihood of infinity， the probability collapses。



![](img/f1beacab783349bf3bffbe6341618ad2_19.png)

And having infinity likelihood is not a good thing。



![](img/f1beacab783349bf3bffbe6341618ad2_21.png)

And so maximal likelihood is poorly postd sometimes because it leads to these solutions that are catastrophic。



![](img/f1beacab783349bf3bffbe6341618ad2_23.png)

To verify that， I'm not going to go over to math。 I'm going to skip the math， because it's。

It's sort of tedious to go over in the classroom， you can watch the video， you'll have the slide。

 you can verify the math in your own time， but we do just like what we did last week。

 we differentiate with respect to theta， we equate to zero and that's how we get how we go from the loss to the solution so its just like least squares except now you're going to have this extra term。



![](img/f1beacab783349bf3bffbe6341618ad2_25.png)

![](img/f1beacab783349bf3bffbe6341618ad2_26.png)

More interestingly， is to get a good geometric interpretation of what we're doing here。

 So one way to think of this loss is to think of。

![](img/f1beacab783349bf3bffbe6341618ad2_28.png)

I'm going to use colors。 It to think of。

![](img/f1beacab783349bf3bffbe6341618ad2_30.png)

There is this penalty， which is a ball we described it last week。

 the quadratic loss is a ball and it's essentially if you cut it at equal height points。

 you get these level curves which are ellipses， ellipsoids as you go down。



![](img/f1beacab783349bf3bffbe6341618ad2_32.png)

And that's what we're trying to minimize。 And so one way to do this is to formulate it as make the loss small。

And make。呃。This term that we call the regular rise as small。

And another way of rewriting an optimization problem is I will say， minimize that。



![](img/f1beacab783349bf3bffbe6341618ad2_34.png)

And keep this below some function of delta。 T is an arbitrary function。 I don't know what it is。

 but there exists some function for which if I were to keep the product of theta times theta small。

 that these two problems are in optimization are equivalent。

This is on the left is what optimization people call a grand form on the right is a constraint optimization and if you do a course in optimization。

 constraint optimization， then it's very easy to actually prove the equivalence between these two I。

Provide this intuitive explanation for it to avoid getting too much into the math。

But I do advise you to。

![](img/f1beacab783349bf3bffbe6341618ad2_36.png)

Optimization is one of those core things of our approach to machine learning。

 finding features we will always find about by optimizing。

 so knowing having a good grasp of optimization is something that I really recommend you to and there's a lot of good tutorials on the web。



![](img/f1beacab783349bf3bffbe6341618ad2_38.png)

Okay， let's come back to this and let's think of an example where theta has two components。 Okay。

 so Theta 1 and Theta2。And so I'm going to draw the contour plots。 So if we were cutting the ball。

This is going to be theta 1， this is going to be theta 2。

 so this is like a top view on these balls that we're trying to minimize。



![](img/f1beacab783349bf3bffbe6341618ad2_40.png)

And I can plot and so let's look at this function here， theta transpose theta。First。In this case。

 this is equal to the vector。And she let me define this to be like this， so let's back to Theta 1。

 The2。Times theta1， theta 2。And you can rewrite this as theta 1 squared plus theta2 squared。

 that's a dot product。Okay。And now if I want。That's a ball， and if I equate。

 in order to get the height of the ball， the constant level curved。I will equate this to a constant。

 an arbitrary constant。 Now， if I have that equation， what's that the equation of？A circle okay。

 so we're going to draw a circle， where is that circle centered at？



![](img/f1beacab783349bf3bffbe6341618ad2_42.png)

That zero at the origin。So that corresponds to the blue curve。For a constant。

 I draw it and it's a circle center at the origin， I can pick another constant and I draw it again。

And I can pick another constant and I draw it again。And so on， you get the picture。

Imagine that it's a circle。And。I'm going to do it for the blue， I'm not going to do it for the red。

 but it's the same thing if you substitute some Y variables there and Theta 1， Theta 2。

 you convince yourself that these are ellipses。Okay。

The center of these ellipses is what we call the maximum likelihood estimate。



![](img/f1beacab783349bf3bffbe6341618ad2_44.png)

Okay， because that's how it's on maximum likelihood。

 we minimized the function of theta and from the center of the ball。

 and that was the maximum likelihood。

![](img/f1beacab783349bf3bffbe6341618ad2_46.png)

Now， if we vary Delta。My claim is that what we're going to get is。

We get a range of solutions for different values of deelta。To get the solution。

 Dlta has to be equal to。Z， right because if you make delta equal to zero。

 you're just basically getting rid of this term， the blue term and you be back to maximum likelihood。

If Delta goes to infinity， it becomes very large。Then the only way you can minimize this loss is by making feet to zero。

Okay so this over here is what happens as delta squared goes to infinitefin so then as you vary delta you get points in this curve。

 so all your solutions will be solutions along this curve。

And it will be precisely at the point at which the two intersect。

 and you can do some reasoning about this。 If you were to move along this curve。

Suppose you move along this curve here， your likelihood hasn't changed because you're at a constant height curve。

But you've moved outside the blue circle， so your blue has increased so you're doing worse and likewise if you move to the other direction。

 the same thing is happening， it likely hasn't changed。

 but your blue thing has gone up so the optimal thing then is to be at that point at which they intersect and you could do the same argument by following the contours of the blue curve。

And so at the points of intersection， those will be your solutions and there's infinite solutions。

Okay， because that's a perfectly continuous curve。So the question is， what's the optimal delta？

And we'll try to answer that question， we'll come up with a method that answers that question in this class。

 what's the optimal delta for a particular data set？Okay。

 a nice thing about this is if you have a model where you have。

 so keep in mind that what we have is many access。

![](img/f1beacab783349bf3bffbe6341618ad2_48.png)

Perhaps D of them， where D could be， say， 20，000 gene。Expressions， and you're multiplying。

 So the neural model that we had for linear regression was something like this。

 where you have this linear neuro。That essentially sums each input multiplied by a parameter。



![](img/f1beacab783349bf3bffbe6341618ad2_50.png)

Okay， so x1 times theta 1 plus x2 times theta 2 is how you compute the linear prediction。

 That's essentially what this neuron does。 It just takes each input multiplies it by what。

People loosely call the synaptic weight theta， and then you add all up and that's the output。



![](img/f1beacab783349bf3bffbe6341618ad2_52.png)

U。Now， the nice thing about this estimator is that this curve know that it。If you look at this curve。

 theta 2 becomes zero much quickker than theta 1。So a nice thing about this is that sometimes some of these variables for particular choices of delta。

 a lot of these variables go to zero， so in other words you're able to automatically screen out the xs that are irrelevant to your prediction and you only keep the relevant ones。

 so it's a way of finding which are the genes。

![](img/f1beacab783349bf3bffbe6341618ad2_54.png)

That actually are responsible or correlated with a particular prediction。

Not the genes that cause causality imp production， not the same thing。

 these are the things that are correlated with the outcome。



![](img/f1beacab783349bf3bffbe6341618ad2_56.png)

And that's very useful， you might want to see what genes are correlated with a particular phenotype。

 and then you can do some experiment where you try to find some causal leak by actually looking at those genes。

And so here is an example that comes from the book of Ha T Sha and Friedman。

 which is available for free on the web called the El of Statistical Learning。

Ignore the green curve for now on the left is essentially what happens when you look at a data set where you're doing linear regression just like we did。

 and this is for prostate cancer and I forget what you're trying to predict。I apologize。

 I forgot predict， but it essentially you take several measurements of a patient like age and on different variables that have some medical meaning and you try to predict something else that is helpful to do diagnosis。

And then as you vary delta in this curve， then you can see that by increasing here you have delta going to infinity。

 you start at delta squared equals0， and as you increase delta。

 the theta shrink to zero and some shrink at a faster rate than others。And when you use the data。

 you find some optimal set of the deltas。 in that book。

 what you'll also find is something called the last soup。

I'm not going to cover it in the course because that requires introducing a little bit more mathematics。

 sub gradientds， and on。Because these guys are non defiable at these corners。嗯。

But it's a simple concept。 I do have lectures online for this。 so you can find it online。

 So the basic idea of the last two is instead of using theta transpose theta， which is also known as。

The L2 normal theta squared。We will instead for this， we will use the L1 normal theta。

And that's the sum of absolute values。 So if theta is two dimensional， that would be theta 1。

So wait let me write it like this or some of observed values of theta I。

 and for the two dimensional case， you would get theta 1 minus sorry plus theta 2。

And so you have two absolute values， so you have to consider the cases plus plus plus minus。

 minus plus and minus minus， each of those four cases gives you one of these lines。

And so when that happens， the intersection points happen at corners， and at the corner。

 theta 2 is exactly0。So the last two is a much more aggressive regular riser because it actually zeros out the variable。

 it's not nearly zero but it really zeros out and you actually figure out which variables are responsive。

Time permitting we will bring in some of these regular iss into the course。

 but be aware that I think torch has these L1 regular iss are very nice when you want to find which are the variables that should be on you're just using L1 regular I。

 it's much more aggressive。Method， and then the only thing why I'm not doing the derivatives of this is because when you do the it's in the textbook。

 if you do the derivatives。You need to worry about how do you differentiate an absolute value and how do you define the derivative at the cusp and so we use a concept called subdifferential。

 which is basically a set of derivatives that blah， blah， blah。

 I'm not going go into that it's in the textbook but remember the intuition you intersecting two sets of contours in this case because you have these pipes you will hit the corner with high probability so you get very sparse solutions and this is very much related to if you do engineering to the concept of something that folks use called compressensing trying to sort of do is just a few the signals are sparse just a few sets of measurements allow you to reconstruct the signal in it。



![](img/f1beacab783349bf3bffbe6341618ad2_58.png)

Absol splendunder。

![](img/f1beacab783349bf3bffbe6341618ad2_60.png)

Okay， let's move on from lines。And move on to arbitrary functions， polynomials。

 and will students still do exactly what we did before， linear regression？



![](img/f1beacab783349bf3bffbe6341618ad2_62.png)

![](img/f1beacab783349bf3bffbe6341618ad2_63.png)

We'll only do a following trick。 Let's look at the curve first， so we still have x， we still have Y。



![](img/f1beacab783349bf3bffbe6341618ad2_65.png)

So the idea is still for we have some data。And your data is x， Y， and you observe， I don't know， 2。

21。Maybe56。3 and you observe 2。6 and so on。

![](img/f1beacab783349bf3bffbe6341618ad2_67.png)

So we have a table of data。And we tried to fit a curve to it。

 but now we have reason to believe that a quadratic will be a better fit than a line。If you do that。

 what you do is you take each x， each individual X I， I is an index over the xs。

 and for each of these points X I，We feed them through a quadratic function。

And then we create this vector that I'm calling phi， sorry。And phi just dependsend these Xs， one。

 because we always need to shift things up and down， Xi itself and Xi squared。Okay。

And now I need three parameters for this 1D model， I need a coefficient for one。

A coefficient for Xi Theta 1 and a coefficient for Xi squared， which is theta 2。

 and I can learn those too。 Now assume that my true model was did not have a quadratic term。



![](img/f1beacab783349bf3bffbe6341618ad2_69.png)

![](img/f1beacab783349bf3bffbe6341618ad2_70.png)

So。

![](img/f1beacab783349bf3bffbe6341618ad2_72.png)

What kind of regular isa would I use？To discover that。



![](img/f1beacab783349bf3bffbe6341618ad2_74.png)

。the L1 D L1 right if I just put an L1 regular eyesr it will automatically make theta to go to zero and I fit the line so if I don't if I if I think。

If I want to give myself freedom， I will construct a model that has a large complexity and then I will use regularizers to automatically bring the complexity down to fit the data nicely。

And that's one of the intuitions on how we design models。

 create very complex models and then think carefully about the regular I and introduce techniques that allow us to estimate exact complexity。

So once you do this you form this vector and now you can just think of this as the x matrix again okay so it has d columns in this case three。

 it will have three columns and it will have n rows where n is the number of data points and then it's just linear regression again so nothing so we play the same game as before。



![](img/f1beacab783349bf3bffbe6341618ad2_76.png)

![](img/f1beacab783349bf3bffbe6341618ad2_77.png)

And then we could do this in 2D， we could start including cross terms。

 X1 x2 or just keep the quadratic terms， depends on how many degrees of freedom。

 you want your polynomial to have the price to pay here is if you have a very arbitrary function。

 all the polynomials that you have， are combinatorial objects you would have you essentially have out you have a tensor product。

 you would have x1 cube as you go to power3 and then you have x1 square with x and so on。

So that explanation so the number of terms grow up exponential and you get yourself into trouble because。



![](img/f1beacab783349bf3bffbe6341618ad2_79.png)

You're trying to describe a world that is finite， with finite resources。

 you don't want your size of the model to grow up explanation。

 it's not going to fit in your head if it grows exponential， so that's a problem with polynomous。



![](img/f1beacab783349bf3bffbe6341618ad2_81.png)

But。

![](img/f1beacab783349bf3bffbe6341618ad2_83.png)

Proceeding where we just fit the polynomials using linear regression。

 then the real challenge is picking the order of the polynomials。

 And the first thing to understand is what is the effect of the number of data。



![](img/f1beacab783349bf3bffbe6341618ad2_85.png)

![](img/f1beacab783349bf3bffbe6341618ad2_86.png)

On this。 So let's assume that my data is produced by。A quadractic。

So there is some process in the world。So that is the true distribution of the world。

 and that's a quadratic。so the universe for this case is behaving as a quadratic。

And let's assume that I have these。These are the data that are coming from this quadratic function。

Okay， there are these blue points， so I'm going to refer to these guys as the train data。And again。

 the x axis， thist a 1D problem， I have x and y， so we're just doing 1D regression。

 and then we're using quadratic model。Now， let's assume now that I use a model。Now I choose a model。

 so the world was a quadratic that had and essentially what I do is I draw random variables according to that Gaussian distribution。

 just like I explained in the previous class， sample from a uniform to the transformation of the CDF and then I add them to this。

 and I picked this mean。

![](img/f1beacab783349bf3bffbe6341618ad2_88.png)

And so。U。So now I'm going to choose the model to be also。

And here I add this because in the true model， I do know the values of theta node。

 theta 1 or theta 2， so by true model is there is a particular setting of theta node1 and2。

 which is the true mechanism from which I've sampled the date。And then I have my model。

 which the heart。Whoops。Xi。

![](img/f1beacab783349bf3bffbe6341618ad2_90.png)

And then my goal is to come up with theta nor theta 1 and theta2 so in this case my model matches reality reality says that the process that generates the data is a quadratic polynom and the model says I'm going to guess that the data comes from a quadratic so I've guess the model right。

 and if you guess the model right then the samples from the model。



![](img/f1beacab783349bf3bffbe6341618ad2_92.png)

![](img/f1beacab783349bf3bffbe6341618ad2_93.png)

You know upload my model， it's the same quadratic function and has the same mean so I'm plotting it on top。

And so my data。From the model。Or in fact， I'm going to call this test data。



![](img/f1beacab783349bf3bffbe6341618ad2_95.png)

And I'm going to make a distinction here。 Think of training data as the data that I have up today。

That I used to fit my model and let's use test data will be the data that someone will give me。

 and I will make predictions according to that test date。

 So if I make predictions according to my test data， I get that session of points in the。



![](img/f1beacab783349bf3bffbe6341618ad2_97.png)

In the green， in the red curve。 And I find that my model fits reality。 Everything is nicely。

 So if you know the model。You can fit things perfectly up to the noise level。

 I will always make errors。There is a error that's governed by the variance of these points。

 and I will always incur that error。So this error is unavoidable。That's the noise error。

You can't do better than the noise because you can't possibly go through the point。

 so you'll always be a bit uncertain， you'll always play these spring values。

The minimum amount of error so if you're doing better than the noise。

 if your error is below the noise， you have a problem like here。

 here the model when I use the train so this I want to make sure it's clear。

 let me repeat this again the train date is what I used to fit the model。

 the test date is what I used to evaluate the model。

So what's happening here is if I have just a few points。

 I can fit past the model through all the points very easily， maybe when I have three points。

 I can always fit a quadratic to go nicely through these three points。AndAnd then I think oh。

 I have a great model， but no， you don't。 You're doing better than the minimum error。

 but that's because you're overfitting。 The danger there is that when you get new data。

 you might find that another curve would have given you better results。Okay。

 but that's still not bad。 I mean， both the test error。

 the train error that converge to the noise level error， so everything is nice。



![](img/f1beacab783349bf3bffbe6341618ad2_99.png)

Now， what happens when my data？Comes from。A quadratic still。But I use a model。

That is of the form theta n plus X I theta 1。

![](img/f1beacab783349bf3bffbe6341618ad2_101.png)

![](img/f1beacab783349bf3bffbe6341618ad2_102.png)

And by the way， the curveva forgot to say this is with I equal 1 to n。

 and this is as n goes increases。

![](img/f1beacab783349bf3bffbe6341618ad2_104.png)

So n is the number of taking。So here as I increase the number of data， the quadratic error。

 the mean square error goes to the right level to the noise level， now if I use a line。

 I mean this is very intuitive if I try to fit a line with quadratic data with a line。



![](img/f1beacab783349bf3bffbe6341618ad2_106.png)

No matter how much data I get。I will not get a good fit。



![](img/f1beacab783349bf3bffbe6341618ad2_108.png)

嗯。These days， you've probably heard of this term called big data。Who's heard of Peate？

This is big data， lots of data。And trust me， I could be drawing this data to make it as big as you wish it would never work。

I would never do well。Big data is pointless if you have the wrong model。U。

No matter how much state is， you can drive the wrong conclusions if your hypothesis is incorrect。

Here， my hypothesis， my model is too simple， and so both the train and the test error will be large。

Bike。There is a bias in a sense that I will never be able to fit。Now。

 there is a case for big data though。

![](img/f1beacab783349bf3bffbe6341618ad2_110.png)

And that happens when I use a very large polynomial。



![](img/f1beacab783349bf3bffbe6341618ad2_112.png)

So let's assume that I'm going to use theta n plus Xi theta 1 plus a bunch of more terms all the way up to Xi to the。

 I think 25。Times theta。

![](img/f1beacab783349bf3bffbe6341618ad2_114.png)

25。Okay， so I use now a very large degree polynomial。



![](img/f1beacab783349bf3bffbe6341618ad2_116.png)

Let's see what happens。If you have only a few points。Let's look at this case first。

If you have only a few points， when you draw your polynomial。Your polynomial has very high degree。

 it will do this。

![](img/f1beacab783349bf3bffbe6341618ad2_118.png)

You will get zero training error because it can go through all the points nicely。



![](img/f1beacab783349bf3bffbe6341618ad2_120.png)

For the test points， this is problematic。Because maybe my test point， because it was a quadratic。

 this was my test point。And so now my errors are huge。Okay， my springs are。Very large， in fact。

Absurdly large in some cases， so my errors in the test data very large。

 I did well with my training data fit my model， I have zero errors so I often have the students come to me and say this model just kills it。

 goes it gives me zero error in the data。Moles like give zero error very dangerous。



![](img/f1beacab783349bf3bffbe6341618ad2_122.png)

But what you can do。Is you can keep increasing the number of data。

And imagine now I have a very large training data set， hugely large。

 so I have now trillions of points。From my training set。

Now when I fit the polynomial to these points。The polynomial will have， it will still lose the leg。

 but it will be kind of caught by these points。

![](img/f1beacab783349bf3bffbe6341618ad2_124.png)

It's constrained by the date， it keeps being pulled back。

 so even though it has all these degrees of freedom。

 so now I have a reasonable fit I have something that also starts behaving like a quadractic and so as the date increases I start getting this。

😊。

![](img/f1beacab783349bf3bffbe6341618ad2_126.png)

So if you have very large data sets， use massive of。

And this is very important in the context of deep learning。

 we tried to use models for images for a long time， for a long time we were working in this regime。

 our models were too simple， but also we had too few data points so we were kind of working in this domain this is pretty much the 80s and 90s this is where we were we went underfitting。



![](img/f1beacab783349bf3bffbe6341618ad2_128.png)

![](img/f1beacab783349bf3bffbe6341618ad2_129.png)

What's happened recently is。I don't know exactly where we are in this curve。

 that is one of the big mysteries， but we've just scaled the models to be much larger because we have the data now and we have computer science has given us the tools to process that data。

 store the data， manage the data， a lot the data to memory。

 do computations across many CPUUs and GPUs and so now we can do this calculation we can build really big models and we're able to do this。



![](img/f1beacab783349bf3bffbe6341618ad2_131.png)

![](img/f1beacab783349bf3bffbe6341618ad2_132.png)

![](img/f1beacab783349bf3bffbe6341618ad2_133.png)

![](img/f1beacab783349bf3bffbe6341618ad2_134.png)

嗯。It may be that we're yeah， I don't know exactly where we are in this curve。

 but certainly we're doing much better by increasing our model complexity。

 so neural nets now that have billions of parameters start providing reasonable models for images and sounds and so on。

 and speech recognition and image recognition have never been this good。



![](img/f1beacab783349bf3bffbe6341618ad2_136.png)

So that's basically it， if you make your model， if your data increases。

 you need to make your model large， there's another way to control complexity。



![](img/f1beacab783349bf3bffbe6341618ad2_138.png)

And that's I'm going to wrap up with this slide here。

 The other way to control mono complexity is to vary delta。

Right because you have a very high degree polynomial。

 but you can make many of those thetaters go to zero by having a particular choice of deelta。

And so if Delta is very small， the polynomial will still tend to go over all the points。

 But as you increase Delta。

![](img/f1beacab783349bf3bffbe6341618ad2_140.png)

You start getting rid of the oscillations in the polynomial。

 So Delta gives us another way of controlling complexity。

 So now we have two ways of controlling complexity。

 The number of data and Delta in the following lecture we run a bit behind， so I'm going to。



![](img/f1beacab783349bf3bffbe6341618ad2_142.png)

I think move the lectures by one because I want to spend time in these concepts and we're going to introduce yet another way of doing fitting data called kernels and they will have yet more parameters that will control complexity and they willll discuss cross validation which is a way of computing delta when you have supervised labels and that will solve this problem that will tell us how to control the complexity how to fit the models and then the only thing that left for us to do is to do optimization to compute thes and then all the work。

 the cleverness is coming up a good rises and setting up these coefficients these deltas to make sure that our predictions are reasonable thank you。



![](img/f1beacab783349bf3bffbe6341618ad2_144.png)

![](img/f1beacab783349bf3bffbe6341618ad2_145.png)

![](img/f1beacab783349bf3bffbe6341618ad2_146.png)

Yeah。OhYeah， yeah。