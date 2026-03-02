# Vizuara【中英⚡机器学习：实践教学｜Machine Learning： Teach by Doing】 p09 P9 ML Teach by Doing Lecture 9： Running the Random Linear Classifier Algorithm i [BV1RusDz1EXd_p9]

Hello， everyone。Welcome to the day8 of the machine learning Tea by Doing project。

This is the part two in the part1， we learned about Jupiter notebooks。

We learned how to install Jupyter notebook and how to integrate it with ES code。In part one。

 we also learned about three powerful Python libraries， Numpir， Psyit Learn and Matt Plootlib。

And we install them in our VS code editor。So if you have not gone through part one。

 please go through it because。We will be needing all of these libraries which we have installed when we run the code in today's particular lecture。

So in this lecture， what we will be doing is that we'll actually be running the random linear classifier algorithm in Python。

And well be seeing the results for ourselves。So in the two lectures before the previous one。

 we looked at linear classifiers in theory， right？

![](img/5b40390d8fa60299e360fe8523fa1db6_1.png)

![](img/5b40390d8fa60299e360fe8523fa1db6_2.png)

We looked at。This particular random linear classifier algorithm。



![](img/5b40390d8fa60299e360fe8523fa1db6_4.png)

We also looked at the hypothesis class， we looked at the s function which exists。



![](img/5b40390d8fa60299e360fe8523fa1db6_6.png)

This sign function and essentially we made all these notes about the theory towards the end we looked at cross validation error and we saw the difference between training error。

 validation and test error。

![](img/5b40390d8fa60299e360fe8523fa1db6_8.png)

![](img/5b40390d8fa60299e360fe8523fa1db6_9.png)

![](img/5b40390d8fa60299e360fe8523fa1db6_10.png)

Today we will be actually diving into code， so we will be employing all of our learnings into code。

If you have not been through those two theory lectures。

 I highly recommend you to go through those so that you will appreciate。Today's lecture， much。

 much more。So let's get started in which in this lecture you will implement the random linear classifier algorithm in Python and I also show you the best tricks to get started with Python if you are a beginner。

 even if you are a complete beginner in Python， I have designed this video so that you will be able to follow and understand。

So let's get started。

![](img/5b40390d8fa60299e360fe8523fa1db6_12.png)

So， in this。This is the day8。Of the ML teach by doing。And our aim in this lecture。😊。

Our aim in this lecture。Is to code。Random。Linear classifier。I'll avoid them。



![](img/5b40390d8fa60299e360fe8523fa1db6_14.png)

Inbit them。

![](img/5b40390d8fa60299e360fe8523fa1db6_16.png)

Let's see the tools which you will need for this coding。The tools which you will need is。

You need by ten。To be installed。We will need。V scored。To be installed。



![](img/5b40390d8fa60299e360fe8523fa1db6_18.png)

We will need。Jupiter notebook。To be installed。

![](img/5b40390d8fa60299e360fe8523fa1db6_20.png)

And we will also need psychic learn。Not just this will need psychic learn。We need nu。

And Matt plotloot Li， which is the plotting library。To be installed。

So psychic Learn is the library for ML。

![](img/5b40390d8fa60299e360fe8523fa1db6_22.png)

In Python Nai is the library for scientificific computing and MatplotLi is the plotting library well need all of these three installed and we have done this in the previous lectures。



![](img/5b40390d8fa60299e360fe8523fa1db6_24.png)

![](img/5b40390d8fa60299e360fe8523fa1db6_25.png)

These two have been covered in lecture five of this speech by doing course。

 so please go to this lecture to see how how to install those。



![](img/5b40390d8fa60299e360fe8523fa1db6_27.png)

All of these have been installed in the previous lecture。

 the part one of the the practical implementation of the random linear classifier algorithm。

 so in the just in the preceding lecture we have installed Jupyter notebook we have installedsyitler Nai and Matt Plib and we have even configured them with VS code。

So all of the tools are in place。

![](img/5b40390d8fa60299e360fe8523fa1db6_29.png)

TheThe next thing which we need is the problem itself。

 so if someone is seeing this lecture for the first time。



![](img/5b40390d8fa60299e360fe8523fa1db6_31.png)

![](img/5b40390d8fa60299e360fe8523fa1db6_32.png)

And if you have not been through the linear classifiers previous lecture。

 so here is the problem again。

![](img/5b40390d8fa60299e360fe8523fa1db6_34.png)

As a refresher。

![](img/5b40390d8fa60299e360fe8523fa1db6_36.png)

Essentially， the problem of this。Linear classifier looks like this on the x axis we have whisker length。

Which is excellent。And on the y axis， we have the ear flapiness index。Which is x2。

And then this is the data which we have。

![](img/5b40390d8fa60299e360fe8523fa1db6_38.png)

For dos， which is the first class， this is the data。



![](img/5b40390d8fa60299e360fe8523fa1db6_40.png)

And for cats。This is the data cats generally have a higher whisker length and lower ear flapiness index than dogs。

 that is why the data looks like this。

![](img/5b40390d8fa60299e360fe8523fa1db6_42.png)

And the aim is to find the。

![](img/5b40390d8fa60299e360fe8523fa1db6_44.png)

That straight line or that linear classifier， which best separates the two sets of data。



![](img/5b40390d8fa60299e360fe8523fa1db6_46.png)

And mathematically， this is also given as。

![](img/5b40390d8fa60299e360fe8523fa1db6_48.png)

Theta 0 plus theta 1 x1。Plus theta 2 x2 equal to 0。



![](img/5b40390d8fa60299e360fe8523fa1db6_50.png)

To understand the code which we are about to write。

 we will first need to understand the random linear classifier algorithm itself。



![](img/5b40390d8fa60299e360fe8523fa1db6_52.png)

So we have already covered this in the previous lectures but let me introduce it here for reference so that it is there in front of your eyes when we code in case you have forgotten it。

 the only way to understand the code is to first understand the algorithm。



![](img/5b40390d8fa60299e360fe8523fa1db6_54.png)

![](img/5b40390d8fa60299e360fe8523fa1db6_55.png)

![](img/5b40390d8fa60299e360fe8523fa1db6_56.png)

So the algorithm is called as a random linear classifier。



![](img/5b40390d8fa60299e360fe8523fa1db6_58.png)

Random linear classifier。

![](img/5b40390d8fa60299e360fe8523fa1db6_60.png)

And the aim of this algorithm。

![](img/5b40390d8fa60299e360fe8523fa1db6_62.png)

The aim of this algorithm is to find the best。Or find the optimal values of。Theta 0。

 theta 1 or n theta 2。

![](img/5b40390d8fa60299e360fe8523fa1db6_64.png)

So basically if Im the optimal straight line here， because if theta 0 theta and theta are fixed。

 this straight line is fixed。

![](img/5b40390d8fa60299e360fe8523fa1db6_66.png)

![](img/5b40390d8fa60299e360fe8523fa1db6_67.png)

So we essentially stop saw that there are three steps to execute this algorithm step number one is。

Try K random choices。Step number one is Pra a random choices of。Theta 0， Theta1 and Theta 2。



![](img/5b40390d8fa60299e360fe8523fa1db6_69.png)

And we actually chose this K to be 100。

![](img/5b40390d8fa60299e360fe8523fa1db6_71.png)

Step number two is。Compute。The training error。

![](img/5b40390d8fa60299e360fe8523fa1db6_73.png)

For each of the K hypothesistheses。For each of the K hypothesisses。



![](img/5b40390d8fa60299e360fe8523fa1db6_75.png)

And the final step， which is step three。Is choose the hypothesis。

Choose the hypothesis with the lowest error。

![](img/5b40390d8fa60299e360fe8523fa1db6_77.png)

So these are the three steps of the random linear classifier algorithm visually this algorithm is really very simple what it tells us to do is that。



![](img/5b40390d8fa60299e360fe8523fa1db6_79.png)

![](img/5b40390d8fa60299e360fe8523fa1db6_80.png)

Take let's say 100 different k is equal to 200 try 100 different straight lines。

 the first straight line might be this the second straight line might be this the third straight line might might be this the first straight line might be this 100 difference rate lines and choose the straight line which gives you the lowest possible training error that is the algorithm。

 It's as simple as that。

![](img/5b40390d8fa60299e360fe8523fa1db6_82.png)

![](img/5b40390d8fa60299e360fe8523fa1db6_83.png)

![](img/5b40390d8fa60299e360fe8523fa1db6_84.png)

![](img/5b40390d8fa60299e360fe8523fa1db6_85.png)

![](img/5b40390d8fa60299e360fe8523fa1db6_86.png)

Now， the way the training error is obtained is that。



![](img/5b40390d8fa60299e360fe8523fa1db6_88.png)

呃。So this is how the training error is obtained。

![](img/5b40390d8fa60299e360fe8523fa1db6_90.png)

Let's say the hypothesis which is chosenism。