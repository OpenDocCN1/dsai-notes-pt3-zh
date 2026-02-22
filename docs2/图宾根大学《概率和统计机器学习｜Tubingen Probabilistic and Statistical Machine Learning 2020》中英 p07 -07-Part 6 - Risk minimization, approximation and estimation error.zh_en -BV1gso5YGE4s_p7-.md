# 图宾根大学《概率和统计机器学习｜Tubingen Probabilistic and Statistical Machine Learning 2020》中英 p07 -07-Part 6 - Risk minimization, approximation and estimation error.zh_en -BV1gso5YGE4s_p7-

So now weve seen what are the optimal forms like the base classifier and also in in regression with the squared loss what is the optimal classifier now we want to turn to two of the most important and basic learning principles at least from a theoretical point of view。

 namely empirical risk minimization and regularized risk minimization and the appbbreviations are ERM for empirical risk minimization in RM regularized risk minimization。



![](img/142b7be90fac2db886fe9be0bf26f232_1.png)

![](img/142b7be90fac2db886fe9be0bf26f232_2.png)

Let us start with empirical risk minimization。

![](img/142b7be90fac2db886fe9be0bf26f232_4.png)

So now finally we are in the situation where we don't know the underlying probability distribution so previously we've always been saying well if we know everything we can have based decision theory we can compute the base class on but now we are in the setting where we don't know the underlying probability distribution and all we have。

😊，Are training points。So assume we have a couple of training points， X I Y I from one to N。

And now what we can do is we can compute the training error。

For a certain function F or the expected empirical risk。As we have seen it before。

 but to recap the empirical risk Rn of this classifier F is simply the average error that we are going to make the average loss。

😊，Where we sum over all the training points from one to end。And this impererisque is， of course。

 a quantity that we can compute just based on the training examples。

 We don't need any underlying probability distribution。 This is just given a function。

 How well does it perform on the training examples。



![](img/142b7be90fac2db886fe9be0bf26f232_6.png)

So the obvious thing that you could do， at least from a theoretical point of view is what is now called empirical risk minimization。

😊，So we consider a certain set of functions that go from x to y。

And we will need to talk in detail about what the set of function is supposed to be。But for now。

 we have Curly F is a set of functions in which we want to search for a solution。

And within these functions， we simply pick this function that has the smallest empirical risk。

So we consider all functions in our class。😊，For each of these functions。

 we compute what is the empirical risk， like how good are they on the given training points？

And then we choose the this function that has the best risk， the smallest risk。

And I've written here fN is the arc min of this function and again I sort of ignore a couple of technical details what if this arc min doesn't really exist。

 if just the inferman exists， then maybe we just would consider a sequence of classifiers that would converge to this functionN and so on。

 but this is not really the point that I want to make here we are not about mathematical sophistication。

 but it's about sort of building up the intuition how we should solve machine learning problems。

The other thing is this function might not even be unique。

 there might be many different functions that have the same empirical risk。😊，And again。

 this is an issue that we ignore and that it also doesn't pose any problems in in practice。



![](img/142b7be90fac2db886fe9be0bf26f232_8.png)

And Ill。

![](img/142b7be90fac2db886fe9be0bf26f232_10.png)

It comes a distinction between two different types of error， and this is really very， very important。

So we are going to talk about the estimation error。And the approximation error。

And to be able to show you what I want to show you about these errors。

 we need to make two definitions。

![](img/142b7be90fac2db886fe9be0bf26f232_12.png)

So by F tilde， I now want to define the best function in the set F。



![](img/142b7be90fac2db886fe9be0bf26f232_14.png)

So assume we have this function set F， all our functions that we want to consider。

And there is one function that is the best function in this class。According to the true error。

 So if we would know the underlying probability distribution。

 we could say what is the best function in this class， say we just look at linear functions。

 what is the best linear functions to describe this underlying phenomenon。



![](img/142b7be90fac2db886fe9be0bf26f232_16.png)

And the error of this in this function is called a tuda。So formally。

 it is the a min for we look at the risk of all functions in our function class F and we take the one where we have the smallest risk。

And now we have two quantities which are called estimation and approximation error。

 and I would like to show it to you in a figure because this is much more intuitive。



![](img/142b7be90fac2db886fe9be0bf26f232_18.png)

![](img/142b7be90fac2db886fe9be0bf26f232_19.png)

So what you can see on this figure is in the big circle， we have the set of all possible。

Measurable functions。 So no like all functions that you could ever imagine live in this big ball F。

 the the large one here。And then in this inner smaller ball， we have the set f tilde sorry。

 the the the set F capital F。 So this is the set of functions that our algorithm is supposed to look at。

 say all linear functions。Now in this set we consider two functions， there is f tilde。

 which is the best function that exists in this set F。And then there is a function F N。

 This is the function that our algorithm picks， and typically the algorithm， of course。

 doesn't pick the best function in our set。 It picks a function。

 but it might not be the best function。And then there's another function， F star。

If star is to base classifier。And often the base classifier does not live in the set functions that you' are currently looking at。

 so if you say I want to use linear functions for classifying my data。

 maybe the true underlying best function is not a linear function。

 so it lives in the space of all functions but not in the smaller space of the functions that you are currently considering。

And now there are the two types of errors that we can look at， the estimation error。

Is now the distance in the risk between the classifier FN that you have chosen with your algorithm。

And the best function in your class。And then theres the approximation error。

 which is the difference in risk between the best in your class。😊，And the best that exists at all。

These are two different types of errors， and now we want to look at how these types of error depend on the size of this function class。

Again， I want to go back one slide。

![](img/142b7be90fac2db886fe9be0bf26f232_21.png)

So here's the formal definition。 The estimation error is the difference between what is best in the class and the thing that I have chosen。

And this is a random variable that depends on the random sample because the classifier that I pick is going to depend on the random sample FN。

 I use my random training sample to pick this classifier。😊，And so this estimation error。😊。

It's a random variable。 It's a random quantity。The other quantity？

The risk of F2 are minus the risk of a star。This is called the approximation error。

 and this is a deterministic quantity。 It does not depend on the data set I use to train the data。

It depends on the choice of this function class F。 and if I choose different function classes。

 I get a different approximation error， but this one is not a random quantity if at least if I don't consider my space as a random space。



![](img/142b7be90fac2db886fe9be0bf26f232_23.png)

Now， here's one important sketch。

![](img/142b7be90fac2db886fe9be0bf26f232_25.png)

On the X axis I want to this is sort of a symbolic sketch。

 I have the size of the function class so if you imagine in this previous plot we have like the small function class and then we can increase it more and more towards until it really fills out the whole space of all possible functions。

😊，So and just imagine intuitively the size of the function class growing。

 and this is what happens on the x axis。😊，And now I have two curves here in my plot。

 the green curve and the red curve。And one curve shows the approximation error。

And one shows the estimation error。And it shows how these errors depend on the size of the function class。

And I would now like to ask you to pause your video for a minute and think about yourself which of the two functions shows the estimation error and which shows the approximation error and please really do it because I think this is really。

 really important to understand。

![](img/142b7be90fac2db886fe9be0bf26f232_27.png)

Okay， Im not going to give you the answer， I hope you have figured out a solution if you really can't get the gist and maybe you want to discuss it in the tutorial sessions。

😊，The next question I would like to ask you now， you know which of the two functions is the estimation error and the approximation error。

I would like to ask you， what do you think， How does the true risk of a classifier look like if you。

 if I would ask you， plot the risk of a classifier in this particular plot， How would it look like。

Maybe to help you thinking about this question is I would like I would advise you to start with the extreme ends。

 a very small function class or a very large function class。

 think about over and underfitting and think about how the true risk of the function might look like and then what it has to do with this approximation and estimation error。

😊，And again， I suggest that you pause your video and take a couple of minutes to figure out what you think。

 how the risk， the true risk of a classifier。😊，Would behave under the assumption that we use empirical risk minimization。

 that is we have a fixed function class and we always pick the best function according to our knowledge in the class。

😊。

![](img/142b7be90fac2db886fe9be0bf26f232_29.png)

![](img/142b7be90fac2db886fe9be0bf26f232_30.png)

Here are some partial answers regarding overfitting and underfitting。

If the function class F that we are going to use to predict or in which we are going to search for the best function if it' is too small。

Then we are going to have underfitting。 We have a very， very small function class。

 and this function class doesn't contain anything useful to describe our data。

So we can pick the best function in this class， but maybe it doesn't really help us。

 This is underfitting。If F is too large， like essentially， it's all functions。

Then this capacity of the function space is so high that we can essentially model any tiny little aspect of the noise in our data。

😊，And then overfitting is going to happen。 We will adapt to tiny pieces of our data that are not really important at an noise and then the test area is not going to be so great。

 So if the function glass is too high we are going to have overfitting。



![](img/142b7be90fac2db886fe9be0bf26f232_32.png)

So this is what we have at the two extreme ends at one。

 and we have underfitting at the one and we have overfitting。



![](img/142b7be90fac2db886fe9be0bf26f232_34.png)

![](img/142b7be90fac2db886fe9be0bf26f232_35.png)

Sometimes instead of talking about the bias variance instead of talking about approximation error and estimation error。

 there is another decomposition that is used which is the bias variance straight off and in particular this comes from the field of regression with the squared loss。

😊，AndIn this particular case， I want to show it to you simply because sometimes I use this term sort of independently of each other and I you simply should know what this is。



![](img/142b7be90fac2db886fe9be0bf26f232_37.png)

Assume that FN is the function constructed on endpoint in a regression example。

If star is the best function， the regression function that you could choose。



![](img/142b7be90fac2db886fe9be0bf26f232_39.png)

And now for the L2 era for the least square loss。

![](img/142b7be90fac2db886fe9be0bf26f232_41.png)

We can decompose the error in two terms， the expected loss with respect to the least squares loss function of the classifier Fn minus regression function。



![](img/142b7be90fac2db886fe9be0bf26f232_43.png)

Consists of two terms。And one is called the variance term and the other the biased term and the variance term is this one it is the expected value of the difference between your predicted function and the expected value of your predicted function。

😊。

![](img/142b7be90fac2db886fe9be0bf26f232_45.png)

And observe， this is the variance。 This is， by definition， this is the variance of this。



![](img/142b7be90fac2db886fe9be0bf26f232_47.png)

Of F and of x。

![](img/142b7be90fac2db886fe9be0bf26f232_49.png)

And then we have a second term， which is the expected value of n of x minus f star of x。

 and this is again this is the pious term of your algorithm。😊。



![](img/142b7be90fac2db886fe9be0bf26f232_51.png)

It essentially measures how much you deviate so the first term measures how much are you going to weigh on your result depending on the fact that you only see a finite amount of data。



![](img/142b7be90fac2db886fe9be0bf26f232_53.png)

And the second term measures， if we ignore the weakling and just look at the expected value。

 how much is this expected value going to be far away from the base classifier？😊。

And sort of the second term has the flavor of the approximation error。Its not exactly the same。

 but it has a similar flavor， and the variance term has a similar flavor as the estimation error。

 because this is the term that depends on the data and measures the variance。

Depending on what particular sample we have chosen or have we got to train our classifiers。



![](img/142b7be90fac2db886fe9be0bf26f232_55.png)

Or maybe another comment here， so again deriving this this statement here with an inequality sign would be easier。

😊。

![](img/142b7be90fac2db886fe9be0bf26f232_57.png)

![](img/142b7be90fac2db886fe9be0bf26f232_58.png)

The point is for squared for the squared loss function。 you can derive it with an equality sign here。

 And this is sort of the stronger side。

![](img/142b7be90fac2db886fe9be0bf26f232_60.png)

Again， the proof is not really complicated， it's on the first couple of pages of this regression book。

 but it's again a bit more technically and I don't want to spend so much time if you want you can look at the book and see what the proof is。

😊。

![](img/142b7be90fac2db886fe9be0bf26f232_62.png)

![](img/142b7be90fac2db886fe9be0bf26f232_63.png)

![](img/142b7be90fac2db886fe9be0bf26f232_64.png)

This I already mentioned， the variance term is sort of has the same kind of intuition as the estimation error。

 the bias term has the same intuition as the approximation error。



![](img/142b7be90fac2db886fe9be0bf26f232_66.png)

![](img/142b7be90fac2db886fe9be0bf26f232_67.png)

So again here is sort of a similar plot as the one we've seen before on the x axis we have model complexity。

 which you could again translate as sort of size of the function class。

And then you have the variance term that increases with model complexity because the more function we have in our class。

 the more possibility we have to really adapt the function to tiny bits of noises。

 so the variance is going to increase because if we change a bit and the data the function is going to change a lot。

😊，Just think about the fact we want to fit a polynomial of degree n to end data points if you change one data point。

 the polynomial might look completely different。Various device decreases with model complexity。😊。

And then the test is going to be some kind of compromise。

 It's going to be high on the left and right sides of the plot because we already said we have under and overfitting at the two extreme ends。

 And hopefully it's a bit smaller in the middle。 And this is sort of the sweet spot that we want to find。



![](img/142b7be90fac2db886fe9be0bf26f232_69.png)

![](img/142b7be90fac2db886fe9be0bf26f232_70.png)

So from lets make a couple of remarks about empirical risk minimization。

 so the first one is that from a theoretical point of view empirical risk minimization is really a straightforward kind of learning principle。

 we want to say we want to minimize the test error。😊。

It is essentially like to estimate the tester error we use the training error。

And this is sort of an estimate， and we simply say we choose the classifier that has the best training error and hope that this is also going to have a lower test error。

Now， whether empirical risk minimization is going to work or to fail。

 that is really going to depend on the size of this function class。

 we have already seen that if it's too large or too small， we are going to underfi or overfit。

 so the crucial criteria for real machine learning system is going to be how to choose the size of this function class。

😊，And in Stat learning theory a bit later in this lecture。

 we are going to see at least some guiding principles for how to do that。

From a computational site empirical pergri risk minimization is typically at least with a 01 loss is typically not what we are going to use。

 The 01 loss is a discrete function， and trying to optimize a discrete function is often NPr。

 So for most machine learning problems。We would not try to optimize the 01 loss function directly。

 but we might want to do is we might want to find a surrogate loss function that is sort of a continuous version of the binary loss and then try to optimize this function instead。



![](img/142b7be90fac2db886fe9be0bf26f232_72.png)

And we are going to see later how this works。

![](img/142b7be90fac2db886fe9be0bf26f232_74.png)

NowI' have told you already that the key problem or key factor of success of empirical risk minimization is that we need to choose appropriately this function class F。

😊，Now， there's one approach that is used in practice a lot。

That tries to avoid the fact that you have to choose this function class for yourself。

And this approach is called regularizedqui scization。And this works as follows。

 So we now assume that F is really a very large space of functions。 say the set of all polynomials。

And now we want to pick a function。

![](img/142b7be90fac2db886fe9be0bf26f232_76.png)

Yeah， stupid fly。

![](img/142b7be90fac2db886fe9be0bf26f232_78.png)

Now we want to pick a function from the class that fits the training data well。

 but also that is not too weak and that is not too complicated。😊。

And instead of saying well we restrict our function class and only allow functions up to a certain amount of weakss or complicatedness。

 as it is done in empiricaler risk immization， we say well。

 we do not really restrict the size of the function space directly but we punish functions that are too weakly or too complicated。

😊，And this is done by a regularization term。

![](img/142b7be90fac2db886fe9be0bf26f232_80.png)

So this is how it works。We have a function class， which is now a really large space of functions。

 say all polynomials。And we now define what is called a regularisor。

Which for each function in my space measures how complicated this function is or how complex it is。

And just as some examples for if your space F is the set of all polynomials。😊。



![](img/142b7be90fac2db886fe9be0bf26f232_82.png)

You could say the measure of how complicated a polynomial is is the degree of the polynomial。

 so atic quadratic function is not as complicated as a polynomial of degree 50。😊，So this number。

 the degree of your polynomial is going to be the measure of complexity。In practice。

 this is not really used a lot because first of all。

 we don't use polynomials and then this is again a discrete quantity which would be annoying to optimize。



![](img/142b7be90fac2db886fe9be0bf26f232_84.png)

But what happens a lot in practice is F is some kind of some space of differentiable functions。😊。

And then the complexity of your function is the maximal slope this kind of function is allowed to have and if you think about it like if you have a function which has a very low slope it can sort of vary smoothly between different results。

 whereas if your slope is allowed to be very steep。

 you can have a function that does very wild things and and gets much more complicated functions in the end and also of course has the potential to fit more noise in your data。



![](img/142b7be90fac2db886fe9be0bf26f232_86.png)

now what we do is we define what is called the regularized risk。And this is now called of an R wreck。

N of F， so the regularized risk。Which consists of two terms， the empirical risk。

 this is the one that we have seen before many times already now。😊。



![](img/142b7be90fac2db886fe9be0bf26f232_88.png)

And now we have the regularization term omega of F together with a trade of constant。

In the trade of Constant Lada it's a constant that we have to choose。

 it's called the regularization constant， it tells us sort of what is the trait of how important is it for us that we get to empirical risk right this term here。

Or how important is it that we get the small complexity of our result。

 Because what we are going to do， the principle of regularized risk minimization is we now in the large space of functions that we have。

 we choose this function that has the smallest regularized risk。 So for all functions。

 we evaluate this quantity and pick the one that has the smallest touch quantity。



![](img/142b7be90fac2db886fe9be0bf26f232_90.png)

![](img/142b7be90fac2db886fe9be0bf26f232_91.png)

And now this means that this quantity needs to be small， the empirical risk。😊。



![](img/142b7be90fac2db886fe9be0bf26f232_93.png)

And this other quantity， the regularization term also needs to be small。

And this parameter Lata controls the trade of so how more important is it for us that the empirical risk is small versus that we find a simple function。

😊。

![](img/142b7be90fac2db886fe9be0bf26f232_95.png)

This is a parameter that we need to choose when we apply regularized risk minimization。

And it's not I mean， there are standard ways by which you can choose it。

 but from a theoretical point of view， it's not always clear which one is the best choice。

But the intuition why we use regularized risk minimization is we want to avoid this problem of selecting the size of the function class。

😊，And what is going to happen is， at least if it works。

That if we can fit our data well with a reasonably simple function。

 then this is what we are going to do。 So this means if there is a simple function that has a low term omega of f。



![](img/142b7be90fac2db886fe9be0bf26f232_97.png)

![](img/142b7be90fac2db886fe9be0bf26f232_98.png)

And it fits the data well in the sense that the empirical risk is small。😊。

Then this is a function that the algorithm would pick。Now。

 if there does not exist a simple function that can fit the data well。

 so for example if when I look at all these functions that fit the data well。

 but they are really really complex in the sense that they fit overfit。😊。

It might happen that I' am not going to choose this very complicated function now because of this regularization term。

 so I not only look at this empiricaler risk， but I also say well。

 if the function gets too complicated then maybe I choose a function that is a bit simpler here。

 gets a better regularization term， but then also has a。😊，嗯。

It might have a slightly higher risk than the best sort of function I could come up with。

 but it's not as weak and in the end， I hope that it doest overfi so much。



![](img/142b7be90fac2db886fe9be0bf26f232_100.png)

So if simple functions lead to a very high empirical risk。

 then I would rather choose a more complex function。



![](img/142b7be90fac2db886fe9be0bf26f232_102.png)

Now again， I would like to ask you a question。😊。

![](img/142b7be90fac2db886fe9be0bf26f232_104.png)

And it is the influence of this parametermeter lambda。😊，On the output of your classifier。Again。

 I would like to ask you， what do you think is going to happen if Lada is really small in the extreme case。

 I can make lambda equal to 0。 What is going to happen then。😊，In the other extreme case。

 I can make La very， very large10 to the power of 10 or something like that。

And what do you think is going to happen if I change this parameter from very small to very high。

And I'd like to ask you to think about how。In which of the situations might I occur underfitting and overfitting。

What can we say about the approximation and estimation error and maybe the relationship of regularized risk minimization to empirical risk minimization and how are these two things related？

So this is a big set of questions again， I'd like to ask you to pause your video and think about the solutions of this question。



![](img/142b7be90fac2db886fe9be0bf26f232_106.png)

![](img/142b7be90fac2db886fe9be0bf26f232_107.png)

Thank you for taking the time to come up with solutions。

I'm not going to provide you all the answers in the lecture if you think you haven't understood it yet。

 I urge you to either discuss it in our flipped classroom or to discuss it in the tutorial sessions with your teaching assistant。

😊。

![](img/142b7be90fac2db886fe9be0bf26f232_109.png)