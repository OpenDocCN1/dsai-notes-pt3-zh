# 图宾根大学《概率和统计机器学习｜Tubingen Probabilistic and Statistical Machine Learning 2020》中英 p04 -04-Part 3 - Formal setup, risk, consistency.zh_en -BV1gso5YGE4s_p4-

Good morning。In the last lecture， we have seen the can nearest neighbor classifier as a first example for a machine learning algorithm。

😊。

![](img/137ccb6cd8db126a6ff1d8a31b874929_1.png)

But now we want to take a more formal approach and really define what are the ingredients that we need in supervised machine learning and what are some important concepts like the base classifier and consistency of a learning algorithm。



![](img/137ccb6cd8db126a6ff1d8a31b874929_3.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_4.png)

We first of all need to talk about what is the underlying space in a supervised or sometimes also an unsupervised machine learning problem。



![](img/137ccb6cd8db126a6ff1d8a31b874929_6.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_7.png)

We typically assume that we have an input space which we are always going to denote by curly X。😊。



![](img/137ccb6cd8db126a6ff1d8a31b874929_9.png)

And in super vasts learning， we also have an output space which is denoted by curly Y。



![](img/137ccb6cd8db126a6ff1d8a31b874929_11.png)

Sometimes these spaces have a mathematical structure。

 so for example there might exist a topology in the space we might have a metric space， for example。

 if you want to measure distances for a canous neighbor classifier。

 it might even be a vector space or something even more complex。😊。



![](img/137ccb6cd8db126a6ff1d8a31b874929_13.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_14.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_15.png)

Maachinery exists in many different flavors， all we need to have so far is the space X and sometimes we have this additional structure sometimes we don't have it。

 sometimes we are also going to construct it， but for now we just have the space X and we have the space Y。

Now， the first structure that we need on that space is in the end we want to define a probability distribution on the space。



![](img/137ccb6cd8db126a6ff1d8a31b874929_17.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_18.png)

So we need a sigma algebra for this。Now if you are a computer scientist and we have never heard about Sigma algebras。

 then simply ignore this concept， if you know about Sigma algebras then we need such a sigma algebra to define the probability measure so we assume that there is a sigma algebra on the space X and there is also a sigma algebra on the space Y。

😊。

![](img/137ccb6cd8db126a6ff1d8a31b874929_20.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_21.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_22.png)

In the following， we are not going to discuss this issue of sigma algebras because for practical machine learning。

 it doesn't really make any difference。 There are no ambiguities like non-measurable functions and stuff like that。

 Everything that can be measured in real world is something finite。



![](img/137ccb6cd8db126a6ff1d8a31b874929_24.png)

You have finite many points， you have a finite precision in your computer and so on。

 so measurability is not really the issue we need to take care about。😊。

If you don't know about measurability， don't worry at all。 this is just for the former setup。

So now we have the sigma algebras on the space x and y。

 we now can define a probability measure and now the important thing is we consider the product space x times y and you see it here on this slide with the product sigma algebra。

😊，And the product space means that we have a copy of x and a copy of y。

 and in the end we are going to observe pairs of x and y。As we have seen earlier， X， I， Y， I。

 these come from the product space， X times Y。Now， the key in machine learning is that we do not make any assumptions on what this probability distribution is is like does it come from a particular class of probability distributions。

 Is it a Gaussian distribution or an exponential distribution， We do not make any such assumptions。



![](img/137ccb6cd8db126a6ff1d8a31b874929_26.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_27.png)

And this is really the key difference also between machine learning and statistics。

 because in statistics， you often you consider how far can you get if you make certain assumptions on your data。

 And then if you know that your assumptions are true， you can get very strong results。



![](img/137ccb6cd8db126a6ff1d8a31b874929_29.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_30.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_31.png)

Now， in machine learning， it's really， really hard。

 So what would be an appropriate probability distribution for your distribution of customers in your online shop。

 You don't have a single clue how you could model this with a probability distribution。

There might be applications where you can do that and in such applications you might want to use probabilistic reasoning which is going to be taught in this other machine learning lecture this year。

😊。

![](img/137ccb6cd8db126a6ff1d8a31b874929_33.png)

But if you do not make such assumptions， then we are in the statistical setup in my lecture。😊。

And this is really the key distinguishing point between the different branches of machine learning and statistics。

 so this lecture takes place in the branch where we do not make any assumption because we simply think that the process that we might want to model is so complicated that whatever kind of assumption we would make for a probability distribution would really not be true at all and then of course there is nothing we can do about that。

😊。

![](img/137ccb6cd8db126a6ff1d8a31b874929_35.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_36.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_37.png)

The other important comment is that both the input and the output variable are random variables。

 So the input has， I mean， some for the input it's more clear we draw。

 say a random person in our population。

![](img/137ccb6cd8db126a6ff1d8a31b874929_39.png)

But also the output can be a random variable and later on for example。

 we are going to consider an example where we take the height of a person and want to predict the gender of the person。

 whether this person is male or female。😊。

![](img/137ccb6cd8db126a6ff1d8a31b874929_41.png)

And now if there is a person which is 1 mter 70 high， the person could be。😊，Female or male。

 so there is not a deterministic rule that would predict the label from the input。

So the output variable itself is also a random quantity。

 and this is something that you need to keep in mind。



![](img/137ccb6cd8db126a6ff1d8a31b874929_43.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_44.png)

Now， a classifier。😊，Its a function that takes an input and produces an output。

 so it is a function that goes from the input space curly X to the output space curly Y。



![](img/137ccb6cd8db126a6ff1d8a31b874929_46.png)

Now， the goal of machine learning is to construct a function that is good in the sense that we have a load test error。



![](img/137ccb6cd8db126a6ff1d8a31b874929_48.png)

And so now we need to define what all these quantities like training error and test are in our former setup。



![](img/137ccb6cd8db126a6ff1d8a31b874929_50.png)

So， the first notion I want to explain is the difference between classification and regression。

 so if the output space y is discrete。😊，And by discrete I mean it has in the simplest case it's a binary space like0 and1 or it could be 100 digits where we have 10 different digits and in general discrete minds we have a finite number of objects that we might want to predict and in our mind we think it's a small number of objects typically we are not。

😊，At least in the simple setup， we start now， we are not looking at 10000 classes。

 but maybe at 15 classes also。This is what I mean by discrete。

 These kind of problems are called classification。😊，If the output y is the real line。

 so any real number could be the output we talk about regression。

 and we've already mentioned this example you want to predict the income of a certain person or the price of a certain thing that you might want to buy。

But there also exist more complicated output structures， output spaces like， for example。

 in structured prediction where the output might be a whole tree of certain a hierarchy that describes your objects in a certain way。

But for now， we start with classification which has and typically we think about binary classification。

 where why it's just a space zero。😊。

![](img/137ccb6cd8db126a6ff1d8a31b874929_52.png)

Now we need to define a loss function to evaluate how good a classifier is。



![](img/137ccb6cd8db126a6ff1d8a31b874929_54.png)

So a loss is now a function that takes goes from x times y times y to the positive real numbers。

And here I have a couple of examples， so the standard loss function for classification。

 we have already seen it as the 01 loss function。So the 01 loss is defined as follows it is a loss for input x true output y and predict say predicted output y prime。

 you simply check whether y and y prime are the same or not if yes you don't have any loss if no you incur loss of1。

Another example for a loss function is the squared loss function， which you have in regression。😊。

So in regression you need to define like you want to predict the income and say you predict the income is going to be 20。

000 euro and then it's 25，000 euro so what is going to be your loss there are many different ways of loss functions for regression and its not so obvious what is the best of all these loss functions。

😊，The classical choice in statistics has been the squared loss function and we are also going to start with this loss function and the squared loss function simply measures like the difference between your prediction and the true value squared。

😊。

![](img/137ccb6cd8db126a6ff1d8a31b874929_56.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_57.png)

This is sort of the standard kind of loss function that people have have been using a lot in the past。

What is really important is the choice of the loss function is going to heavily influence the inductive bias that your algorithm is going to have and we are going to see examples when we talk about linear regression for example。

 the difference where the loss function really has a big influence in what is the outcome of our result。

😊。

![](img/137ccb6cd8db126a6ff1d8a31b874929_59.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_60.png)

Now you might wonder why the loss function is let's go back to the previous slide。😊。



![](img/137ccb6cd8db126a6ff1d8a31b874929_62.png)

The two loss functions that are on this slide do not depend on x at all。

 so the input argument x doesn't really occur on the right hand side so these two examples only depend on the predicted value and the true value but there are examples where it is important that the loss function also depends on x on the particular input value。



![](img/137ccb6cd8db126a6ff1d8a31b874929_64.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_65.png)

And I'd like you to ask you to take a minute and think about whether you can come up with an example where the loss。

😊。

![](img/137ccb6cd8db126a6ff1d8a31b874929_67.png)

Should also depend on the input of on the x value of your， of of your classifier。



![](img/137ccb6cd8db126a6ff1d8a31b874929_69.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_70.png)

Okay， I hope you came up with a couple of examples。

 I want to mention one in a medical context for example。😊。



![](img/137ccb6cd8db126a6ff1d8a31b874929_72.png)

There might be cases where it is not so important to what the predicted outcome is or whether you make a mistake。

 but other cases where it's really crucial。😊。

![](img/137ccb6cd8db126a6ff1d8a31b874929_74.png)

So say there is a certain virus and it doesn't really affect people， say below 40 or so very much。

So you might want to classify whether a certain person has this virus or not， but in the end。

 it doesn't really matter so much。

![](img/137ccb6cd8db126a6ff1d8a31b874929_76.png)

So here maybe you don't occur any big loss if you make a wrong prediction。

 but now assume that this virus affects people。 I don't know。 elderly women in a particular way。

 And now you have this elderly woman who is 85 years old。



![](img/137ccb6cd8db126a6ff1d8a31b874929_78.png)

And for this woman， it's not really important that you get a classification correct。😊。

And now if you design a machine learning system and you know in advance that it's really。

 really important to get it correct for elderly women rather than for the whole population。

 then you would define a loss function such that if your classifier makes a mistake on this critical population on the elderly women。

😊，Then the loss would count much， much more。 so what would then happen is that in the anticlassifier might concentrate on this very important part of your space much more。

😊，And maybe put not so much effort in the space where it's not so important。

 So this is an example where it might be important that the loss function really depends on the input point itself。

 This is not always the case， but there are such applications。



![](img/137ccb6cd8db126a6ff1d8a31b874929_80.png)

Another thing that can happen is that in application， it is important which type of error you make。

 and this is in the definition of the loss function， this is the order of the two arguments。

 Y and y prime。

![](img/137ccb6cd8db126a6ff1d8a31b874929_82.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_83.png)

So depending on whether y is the true label and y prime is a predicted label or whether you consider the other way around。

 your loss function might behave differently。😊。

![](img/137ccb6cd8db126a6ff1d8a31b874929_85.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_86.png)

And again， I'd like you to ask you to take a minute and think about whether you find an example where the type of error。

😊，Is important。Okay， maybe you found one example。 I want to mention a very obvious one spm detection in spm detection。



![](img/137ccb6cd8db126a6ff1d8a31b874929_88.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_89.png)

If there is a spam email and the email ends up in your inbox， not much harm has been done。

 you delete it and that's it。 it's annoying， but it doesn't really cost a lot。



![](img/137ccb6cd8db126a6ff1d8a31b874929_91.png)

However， if there's this very important email， say you had this job application and there's this email of the company that wants to employ you and this email ends up in your spam folder and you never get to see it。

 this can really make a lot of harm。😊。

![](img/137ccb6cd8db126a6ff1d8a31b874929_93.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_94.png)

So in the example of spam detection， the type of errors are not symmetric。

 So if I misclassify a normal email as spam， it's not a big problem。But if I misclassify as hang on。

No， it's the other way around if I misclassify a normal email as spam this can be a big problem。

 this is the normal email that comes from your employee and ends up in the spm folder。😊。

Whereas if you have a spam email and it gets misclassified as normal email。

 it's not really a big big deal。

![](img/137ccb6cd8db126a6ff1d8a31b874929_96.png)

So this is why we have in this last function the three arguments and also the order of the arguments matters。

😊。

![](img/137ccb6cd8db126a6ff1d8a31b874929_98.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_99.png)

嗯。Now we need to define the risk of a classifier。

![](img/137ccb6cd8db126a6ff1d8a31b874929_101.png)

So the true risk， or sometimes we also say the true expected loss。



![](img/137ccb6cd8db126a6ff1d8a31b874929_103.png)

Of a classifier or in general， any prediction function F。With respect to any given loss function L。

Is the expected loss of this classifier。 So the risk of F。



![](img/137ccb6cd8db126a6ff1d8a31b874929_105.png)

Is the expected value。Of the loss。Of x， y， and F of x。

Where the expectation is now over the random draw of these points， x and Y。So X and Y remember。

 come from this product space。Clearlyly x times cur Y。 So you draw a random pair X， Y。



![](img/137ccb6cd8db126a6ff1d8a31b874929_107.png)

You evaluate the function on the input you compute the loss function。

 whether the function predicted the right or wrong thing。

 and then you take the expected value over all such points that you can draw。

And this is the risk of a classifier F。So this is now。

I think for all these quantities it' is always very important to figure out which quantities depend on the data and not in this case F is just a fixed function for now it does so in the setup I've described here f is just a given function we first give x and we first give f and then we want to evaluate its risk by taking the expected value over the product space of x and Y。

😊，And the goal of machine learning is to use the training data that we might get to construct a function whose risk is as small as possible。

 So the quantity that we're interested in is this true risk。



![](img/137ccb6cd8db126a6ff1d8a31b874929_109.png)

And not the training error or anything else。 This is the thing we want to get small。

 as small as possible。

![](img/137ccb6cd8db126a6ff1d8a31b874929_111.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_112.png)

Now， what is now the best classifier you might be able to think of？



![](img/137ccb6cd8db126a6ff1d8a31b874929_114.png)

To be able to define this classifier， I introduce one more term， it is called the base risk。

So the pace risk。Please look at the slide is defined as the infumum of all risks。😊。

Of all functions that you could potentially observe。



![](img/137ccb6cd8db126a6ff1d8a31b874929_116.png)

This is now in my words。 So what is formal written here is we consider all functions that go from x to y。

 which are measurable。😊，And again， if you have never heard about measurability to simply ignore this term measurable。

 simply think of all functions that exist。😊，So intuitively， we take all functions。

 all possible functions that might ever occur going from x to y。😊。



![](img/137ccb6cd8db126a6ff1d8a31b874929_118.png)

We look at all their risks and the best like the one with the smallest risk。

 this is what we call the base risk。😊。

![](img/137ccb6cd8db126a6ff1d8a31b874929_120.png)

And we take the in because we might not know whether the minimum exists。

 so we need to talk about the infinm。

![](img/137ccb6cd8db126a6ff1d8a31b874929_122.png)

And the quantity that we get is called R star。 So in optimization。

 the star often indicates what is the optimal solution。 So the optimal solution。

 the best classifier with the best true risk is。Has the risk our star in this case。

And if they exist such a classifier that really attains this minimum。😊。

We call this classifier the base classifier， and we denot it by F star。



![](img/137ccb6cd8db126a6ff1d8a31b874929_124.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_125.png)

Now， in machine learning， we need the training data。



![](img/137ccb6cd8db126a6ff1d8a31b874929_127.png)

So now we have。We have our underlying space， we have a probability distribution on the space and now what we are going to do for machine learning is we draw endpoints from this underlying space IID。

😊，And IidD means independently and identically distributed。



![](img/137ccb6cd8db126a6ff1d8a31b874929_129.png)

This means whenever we draw a new point， it' is independent from our previous data points whenever we draw we take a new independent draw。



![](img/137ccb6cd8db126a6ff1d8a31b874929_131.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_132.png)

And all of them have the same distribution， namely they come from this product space X Y with this particular probability distribution that lives on that space。

😊。

![](img/137ccb6cd8db126a6ff1d8a31b874929_134.png)

This IID is a very convenient mathematical assumption from the practically practical point of view。

 IID is a very strong assumption， in fact， so we assume that there is not any structure in our in our data and all these all these data points have been generated independently。

😊。

![](img/137ccb6cd8db126a6ff1d8a31b874929_136.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_137.png)

And this is not very realistic。 so if you have some online shop and you want to predict your customer's behavior。

 it might make a big difference on whether you record the customer behavior in the morning or in the evening because you have completely different populations there and and so theres lots of structure in this data。

😊。

![](img/137ccb6cd8db126a6ff1d8a31b874929_139.png)

Which we assume that it doesn't exist。

![](img/137ccb6cd8db126a6ff1d8a31b874929_141.png)

Also， we assume that the probability， at least in this setup that the probability distribution is once fixed forever。

😊，There are also many applications， as I already said。

 like in spam detection where the probability distribution of the points is going to change because for example。

 the opponents change the way they designedm filter their spam image。

We are currently looking at this batch setting where the probability distribution is fixed。

 there exists many extensions of machine learning to the online setting and also to other scenarios where the train and pet test population might be different and we are simply this can be treated。

 we simply don't treat it right now。😊。

![](img/137ccb6cd8db126a6ff1d8a31b874929_143.png)

So in this space setup update that weve now defined。

 the goal of machine learning is to take the training data that has been generated IID from the underlying probability distribution。

😊。

![](img/137ccb6cd8db126a6ff1d8a31b874929_145.png)

Construct a classifier FN。 It's typically called fN because it depends on the N training points。

And this classifier is supposed to have a risk that is as close to the base risk as possible。

Remember， the base risk is the best risk that we can attain。

 and we now want the risk of the classifier R of Fn。Is approximately the risk of the base classifier。

This is what we want to achieve in machine learning。



![](img/137ccb6cd8db126a6ff1d8a31b874929_147.png)

Now， I want to talk about consistency because in statistics， consistency is sort of the holy grail。

 This is the thing that you would like to achieve that will tell you that ultimately your algorithm is going to do the correct thing。



![](img/137ccb6cd8db126a6ff1d8a31b874929_149.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_150.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_151.png)

So we now consider an infinite sequence of data points， so X IY， I from 1，2，1，2，3，45。

 and it keeps on going。So we want to say something like if we record infinitely many training data points in the end the classifier in the limit for n going to infinity。

😊，The classifier is going to do the right thing。So we have the sequence of data points that have been drawn IID from the underlying probability distribution。

And now we fix a set of endpoints， the first endpoints and construct a classifier fN。



![](img/137ccb6cd8db126a6ff1d8a31b874929_153.png)

And this is the classifier that has been constructed by our algorithm on the first end training points。



![](img/137ccb6cd8db126a6ff1d8a31b874929_155.png)

And now we say this algorithm is consistent。For the given probability distribution P。



![](img/137ccb6cd8db126a6ff1d8a31b874929_157.png)

If they risk the true risk R of Fn。

![](img/137ccb6cd8db126a6ff1d8a31b874929_159.png)

So the true risk of the classifier that has been constructed on end training points。



![](img/137ccb6cd8db126a6ff1d8a31b874929_161.png)

Converges to the base risk。And let's look at the formula it says， for all epsilon larger than  zero。

😊，If we take the limit of end to infinity。

![](img/137ccb6cd8db126a6ff1d8a31b874929_163.png)

Then the probability that the risk of the classifier F N that we constructed on our training data。

Deviate from the true base risk by more than epsilon。This limit is 0。



![](img/137ccb6cd8db126a6ff1d8a31b874929_165.png)

And this formula needs a bit of time for to digest it。

 I mean the first comment I want to make is if you have seen probability theory before what I've written here is convergence in probability。

 there also exist other notions of convergs like almost true convergence。

 but for now let's stick to convergence and probability。



![](img/137ccb6cd8db126a6ff1d8a31b874929_167.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_168.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_169.png)

So the important factor is this R of Fn is a random quantity。



![](img/137ccb6cd8db126a6ff1d8a31b874929_171.png)

Because F N depends on our data。 So we have N training points。

 We have this algorithm in the background that spits out a function F N。



![](img/137ccb6cd8db126a6ff1d8a31b874929_173.png)

So this function F N depends on the data。But now we have the risk。

 the expected risk of this function。And this expectation is taken over all possible test points。

So still this risk is a random quantity because it depends on the finite set of n training points。

 but the risk is evaluated on the infinite set of all test points， just is sort of the mindset。

So it's a true risk of this function computed on the end training points。

 and this is supposed to convertverge to the base risk。



![](img/137ccb6cd8db126a6ff1d8a31b874929_175.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_176.png)

And the particular way it's written down here is called conversionverence and probability。



![](img/137ccb6cd8db126a6ff1d8a31b874929_178.png)

Observve that in this particular definition。

![](img/137ccb6cd8db126a6ff1d8a31b874929_180.png)

The definition depends on P on the underlying probability distribution。

 So we say if we fix P and we draw our training points from P and we evaluate our expected value of the risk much according to P。

 then this whole thing is going to converge。

![](img/137ccb6cd8db126a6ff1d8a31b874929_182.png)

It could be that for some algorithm this convertverges for some probability distribution P。

 but maybe it does not converge for some other probability distribution P。 For example。

 it might be that it only converges if P is a nice density very smooth and if you have a fractal kind of probability distribution or a counter distribution or something really weird then maybe it doesn't convertver。

 So for now。

![](img/137ccb6cd8db126a6ff1d8a31b874929_184.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_185.png)

The definition just， the algorithm is consistent for this particular probability distribution。



![](img/137ccb6cd8db126a6ff1d8a31b874929_187.png)

Now， of course this is a bit annoying because we don't know what the probability distribution is in our particular application and we want to say something like no matter what the underlying probability distribution is。

 I want this algorithm to be consistent。😊。

![](img/137ccb6cd8db126a6ff1d8a31b874929_189.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_190.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_191.png)

And this is now what is called universally consistent so we say that an algorithm is universally consistent if it is consistent for all possible probability distributions P over the probability space xy。

 and again I ignore the issue of measurability and sigma algebrasia。😊。

And so the ultimate goal of machine learning is to find learning algorithms that are universally consistent。

 So no matter what the underlying probability distribution is。



![](img/137ccb6cd8db126a6ff1d8a31b874929_193.png)

When we see enough data points for n going to infinity。Eventually。

The risk of our classifier is going to convertverge to the best possible risk that you could ever achieve namely to the base risk。

And this is from a formal point of view， the goal of machine learning。



![](img/137ccb6cd8db126a6ff1d8a31b874929_195.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_196.png)

And note this is really somewhat a high goal because this for all probability distribution really contains all the weirdest probability distributions that you can come up with and if youre a mathematician and you have seen probability or at least advanced probability there exist really very weird probability distributions out there。

 but we want that it still convert as if we've seen enough data at least it shouldn't really matter any more of it how complicated our probability distribution is we want the algorithm to discover the ground tools。

😊。

![](img/137ccb6cd8db126a6ff1d8a31b874929_198.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_199.png)

And there was a long time in which it was really unknown whether universally consistent learning algorithms can exist at all。

 and the first pre as far as I know， was in 1997 when the theorem of stone has been proven。

 this is the theorem that really says that a canous neighbor algorithm is universally consistent。😊。



![](img/137ccb6cd8db126a6ff1d8a31b874929_201.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_202.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_203.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_204.png)

So this was the first result， but now since then there have been many。

 many other algorithms that have been proved to be universally consistent like support vector machines boosting random forests like many of the classical machine learning algorithms have been proven to be universally consistent。

 at least under certain assumptions on how you construct these algorithms。😊。



![](img/137ccb6cd8db126a6ff1d8a31b874929_206.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_207.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_208.png)

![](img/137ccb6cd8db126a6ff1d8a31b874929_209.png)

And the， the。Big aspect of machine learning theory is to really understand how can we prove that a certain machine learning algorithm is consistent or maybe when is it consistent or what assumptions do we need to make So such that it can be consistent and under which assumptions it's impossible that it's consistent。



![](img/137ccb6cd8db126a6ff1d8a31b874929_211.png)