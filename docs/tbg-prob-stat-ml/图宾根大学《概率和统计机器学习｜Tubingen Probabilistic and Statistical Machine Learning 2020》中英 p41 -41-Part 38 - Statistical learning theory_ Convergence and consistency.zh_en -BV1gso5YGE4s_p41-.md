# 图宾根大学《概率和统计机器学习｜Tubingen Probabilistic and Statistical Machine Learning 2020》中英 p41 -41-Part 38 - Statistical learning theory_ Convergence and consistency.zh_en -BV1gso5YGE4s_p41-

Now we are going to start with a new chapter in our lecture。

 namely with a chapter on Statistic Learning theory。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_1.png)

Of course there are lots and lots of results in learning theory。

 there are whole conferences like the conference on Learning theory called。

 which is dedicated to all kinds of papers on all kinds of questions in Sta learning theory。😊。

But in this particular part， we are just going to look at two or three different lectures that give an introduction to what are the standard results in classic learning theory for binary classification。

😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_3.png)

So let us start。So on a very high level， what is learning theory about or in particular statistical learning theory？

😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_5.png)

So you might remember instead standard computer science。

 there are some very fundamental results about computability。

 so there are results like which functions can you compute。

 Are there functions that you cannot compute at all。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_7.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_8.png)

The answer is yes。Can we always compute efficiently。

 Are there problems that have different difficult kinds of complexities。

 And there's a whole range of papers in this sort of traditional field。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_10.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_11.png)

Of， of。Of theory， of algorithms and theory of computer science。

 if you want of of compability and so on。 And we ask very similar questions like this one in learning theory as well。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_13.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_14.png)

So which kind of learning tasks in principle could be solved by a computer？



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_16.png)

And there may be tasks that cannot be solved at all by a learning algorithm。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_18.png)

Which kind of assumptions do we need to make， Are there may be problems that are harder to solve or can we somehow characterize which kind of solutions of certain problems are more efficient from either computational point of view。

 but in particular， also from a statistical point of view。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_20.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_21.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_22.png)

So what are the key properties that a learning algorithm needs to have？😊。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_24.png)

In order to be successful。To learn the truth， to do it efficiently， to maybe be easy to interact。

 So how can we quantify these kind of things， What What are the the fundamental statements that we can make。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_26.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_27.png)

And in particular， which kind of performance guarantees can we give on algorithms that are used in machine learning？



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_29.png)

Just consider you want to apply machine learning in a context of some critical systems where it's really important that you don't make a wrong decision in a medical context。

 for example， or you want to drive a plane or something like that using certain aspects of machine learning。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_31.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_32.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_33.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_34.png)

Then of course machine learning always has this kind of statistical component we learn from random data。

 we learn a function， there is a certain probability that what we learn is wrong。

 at least on particular test examples， but we would like to quantify。

 well how likely is it that something goes wrong？😊。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_36.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_37.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_38.png)

And in this sense it's a bit like in statistics， in Stan statistics we have a very strong field both in traditional frequent statistics and also based in statistics that try to give us guarantees。

 confidence statements and so on that a certain finding that has been deduced from random data is correct。

😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_40.png)

And we would like to do something similar for machine learning algorithms。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_42.png)

The challenge is going to be that the results that we get will typically not be as strong as the ones that we could derive in statistics and the main reason is that many of the strong results in statistics require very strong assumptions。

😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_44.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_45.png)

So if I assume my data is normally distributed and I want to test whether a mean has like two means of of normal distributions are the same or not。

 I know exactly how to do that。 I can use a T test。 I can compute confidence intervals。

 and they give very strong。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_47.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_48.png)

Confidence limits on a finite amount of sample points。

 And they would say me for 100 data points we are very confident that I don't know these two means are different from each other and you can really trust these numbers in machine learning the story is much。

 much more complicated because we want to make much less assumptions and the fewer assumptions you make the more kind of instances and weird cases you need to consider and the lesser our guarantees are going to be So in the end many of the guarantees we are going to look at are rather consistency statements in the form。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_50.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_51.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_52.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_53.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_54.png)

Like as the number of sample points n goes to infinity。

 we are going to converge to the correct result。 we might maybe make a statement about the speed of convergence and say with a certain algorithm。

 we achieve a faster speed of convergence than with another algorithm。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_56.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_57.png)

But typically we cannot hope to achieve these kind of guarantees that say with 95% probability。

 I'm sure that this finding on this data point is correct。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_59.png)

Still， learning theory is really， really important because it gives us important insights into what are the building principles of machine learning algorithms and what makes an algorithm work and what are maybe the aspects that will break an algorithm or the performance or the guarantees。

😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_61.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_62.png)

Okay， this was a long introductory speech。 You see that somehow Sta learning theory is a field that I really like a lot because it's my home field。

 This is where I do most of my research in。😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_64.png)

Now let's simply get started。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_66.png)

So the bottom line on this slide is we are going to focus on a very simple case in this lecture。

 binary classification in sort of what I would call the traditional regime like support Victor machinesch Cane to neighbor。

😊，WhatAll these algorithms that we have discussed in this lecture so far， not deep learning。

 which is another story。😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_68.png)

Let us recap the framework we did this at the very beginning of our lecture。

 but now it's important to sort of make us aware again what are all our assumptions and ingredients。

😊，So the assumption in the standard field of Stat learning theory is that we have training data and in the easiest case。

 they are an IID sample from some underlying unknown probability distribution P on our data space。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_70.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_71.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_72.png)

The goal is we want to learn a function， a deterministic function that takes input points and predicts the correct label plus minus1 because we're in binary classification。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_74.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_75.png)

And the way by which we measure our success is a loss function。

 So we have a loss function that tells us how， how。😊。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_77.png)

How we punish certain mistakes we make？

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_79.png)

And then we look at the expected loss， so over the whole space of examples in expectation。

 what is the loss that you're going to incur？And we want to find a function that has a small like the expected loss or the risk of this function should be as small as possible。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_81.png)

In classification the traditional loss function we look at is the 01 loss function。

 at least in theory， in practice one we have seen that we often optimize different loss functions like the hinge loss or the logistic loss or whatever in theory and also in applications in the end what were interested in is the 01 loss did we classify this example correctly or not。

😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_83.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_84.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_85.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_86.png)

Let us again talk about the assumptions。It'sThe very first and most important assumption in my feeling。

 at least。Is that we do not make any assumption on the underlying distribution that generates the data。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_88.png)

And this is sort of， in contrast to many of the results in standard statistics where we do make assumptions on the distribution。

 Something is normally distributed or exponentially distributed or or distributed， whatever。

 So we assume we know something we put our prior knowledge in this assumption on the distribution。

 and then we can make strong statements。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_90.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_91.png)

In machine learning this is not the point because you don't have any clue like if you have a database of customers what distribution these data look like。

 I mean you simply don't know it would be too complicated or pixels in an image。

 I mean what is the distribution of pixels in an image it's definitely not a normal distribution。😊。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_93.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_94.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_95.png)

And the problem is if we would make such assumptions， but the assumptions are wrong。

 then of course our guarantees are wrong as well。 and the philosophy in learning theory is rather we do not make strong assumptions in particular not on the underlying distribution。

😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_97.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_98.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_99.png)

Then we prove guarantees， but at least then these guarantees apply to all kinds of cases that would occur in practice。

The next thing that's important is the labels of our training data not necessarily are a deterministic function of the input data。

 consider again this very simple example you want to classify whether someone is male or female depending on the body height。

 there might be a person who is 1 meter 70 which is female or male so there is not a deterministic function that in the ground truth would tell us everybody who is 1 meter 70 has to be male。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_101.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_102.png)

Of course， the function that we want to learn is going to be a deterministic function。

 We simply would say， I mean， maybe we might want to attach some some uncertainty about a certain statement。

 but it wouldn't help us。OrThere might be， there might be also applications where we do not maybe might want to say we are not really sure what this is。

 but in all the other cases， like in the standard setup that we have in supervised learning for given input。

 we simply find out what is the best prediction we could make we could make。

 given the current circumstances。 And then this is at at aministic prediction。

 So we do not have any randomness in our prediction。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_104.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_105.png)

嗯。The next important assumption is that we assume that the data points。

 the training points and also the test points come IID from the underlying distribution。

 This means they all follow the same distribution。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_107.png)

And it doesn't matter in which order they occur。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_109.png)

This is， of course， a very strong assumption。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_111.png)

So in many processes that you would observe in practice， data points are not IID。

 so if you have shops in an online， you have customers in an online shop。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_113.png)

It might be very different customers， the ones that shop in the morning and the ones that you see in the afternoon or in the evening。

 so they definitely do not come from the same kind of distribution。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_115.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_116.png)

Similarly， the distribution might also change over time if you have some machine learning problem that has also some kind of time component like in spam classification。

 of course， like once a certain new spam email is out and the anti spam programs know how to detect the spaMs are going to change their kind of their strategies so it is going to change over time。

 so definitely if I look at what are the spam emails in one month。

 it's not going to be the same emails or at least there might be many ones which are not the same ones as the ones that I've seen last year。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_118.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_119.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_120.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_121.png)

So this IID is a really strong assumption。😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_123.png)

But at least in the vanilla version of learning theory， as I'm going to present it。

 this is simply the assumption we make。😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_125.png)

And the way I see this is maybe also。😊，As I said， we are not going to get very。

 very strong guarantees on one particular outcome of a particular learning algorithm on a particular data set。

 What we might want to do is a more。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_127.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_128.png)

Sort of fundamental kind of distinction between things that might work in principle and things that might not work so if we find a problem that wouldn't even work in this IID setting then where we probably can also forget about it in a setting where we don't even have IID data。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_130.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_131.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_132.png)

So in this sense。This kind of learning theory gives you a baseline of what I would say unnecessary assumptions that we would need to make in order to get good results in the end。

😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_134.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_135.png)

Even though maybe this IID assumption in the end might not be completely satisfied and now you might still see cases where your algorithm doesn't work because the IID。

 the fact that it's not IID is going to break it。😊。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_137.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_138.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_139.png)

Okay， and then the last thing that is obvious but still lets try to remember it the distribution P of course is not known at the time of learning。

 this is the whole point of machine learning， we need to know or we want to learn what is the underlying distribution to minimize the loss so the distribution is not known。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_141.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_142.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_143.png)

The best classifier， if you remember， is the best classifier that we could define on a given learning problem。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_145.png)

So given the data space and the distribution that generates the data。

 you can compute what is the classifier that achieves the minimum expected risk and this is called the base classifier。

😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_147.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_148.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_149.png)

We have already seen how to compute it in the beginning of the lecture。😊。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_151.png)

And now， of course。The challenge that we have is that we don't know the space classifier。

 and this is why all of learning has to be necessary because otherwise you could stop at this particular point。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_153.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_154.png)

So the formal notation which we are going to need during the next couple of slides is as follows。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_156.png)

So n is always the number of data points drawn from the distribution P。

 we have a function class F from which we are going to pick our function in particular we are going to do it by empirical risk minimization at least in the first part of this lecture。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_158.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_159.png)

F star is going to be the base classifier corresponding to this distribution， we don't know it。

 but it is the reference we want to compare to we want to get as close as possible to the base classifier。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_161.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_162.png)

Then we have this classifier， which we call F subscript capital F。

 which is the best classifier in the function class that we are currently looking at。😊。

So because we are going to use empirical risk minimization or in fact。

 not because our goal is to minimize the true risk of a function and so we can check if we are given a certain function space F。

 what would be the best result that we could get in principle？😊。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_164.png)

If we ignore all the aspects that come into the play because we just have a finite sample。

 so given the distribution P， assume we know it， what is the best classifier that we can achieve with this particular function class。

 that is FF。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_166.png)

And then by fn， I am always going to denote the function that has been chosen by a particular algorithm on seeing n data points that have been sampled from this particular underlying distribution and typically fN is going to be picked from this data space cur F in some way。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_168.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_169.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_170.png)

We are going to look again at consistency of learning algorithms and let me recap the definitions。

We say a learning algorithm is consistent with respect to function class F and probability distribution P。

If the risk， the true risk of the function that has been picked。

From F from Fn based on n data points， converges in probability。

To the risk of the best function that we could pick from F。嗯。Period。So in a mathematical notation。

 this means for all epsilon。😊，The probability that the true risk of the function we constructed on our asemble。

Devates from the risk of the true best function in the class by more than epsilon。Converges to0。S。

 the sample size goes to infinity。This is stated here in terms of convergence and probability。

 one can also do all this in converence in almost true convergence。

 which I'm not going to discuss because I'm aware that some people in my audience don't really know what the difference is。

 but this is not the main point in the lecture here。

The next thing we say an algorithm is space consistent with respect to some underlying probability distribution。

If the risk of the classifier that the algorithm picked。

Converges not only to the best risk in the function class。

 but to the best risk that we could achieve overall to the risk of the base classifier。Again。

 with the same kind of statement as we had before， the probability that the risk on the empirical data deviates from the risk of the base classifier by more than epsilon goes to0 as n goes to infinity。

😊，And then finally， the Holyly grarail， what we interested in。😊。

An algorithm is called universally consistent， either with respect to F or even universally pay consistent。

😊，If this consistency ocean。Does not only hold for this fixed probability distribution。

 but for all probability distributions that are out there on this particular data that we have。

And this is of course what we are after because as I've said already。

 we don't know what the underlying distribution is。

 so we need to make sure that for all kinds of distributions that would occur， the algorithm。

 at least eventually as it sees enough data points and to infinity is going to discover a function that comes as close as possible to the ground truth that we are after。

😊，Again， there's one comment I want to make once more this consistency with respect to a fixed function class。

 which is sort of the main notion that is being considered in。In a large pile of learning theory。

Only concerns the estimation error and not the approximation error。So the estimation error。

 if you remember again， just says how much。😊，How bad is the effect that we only see a finite sample as opposed to seeing infinitely many samples or seeing the whole data distribution。

😊，And this is the effect that we have by seeing just a finite sample。

 this is what we call the estimation error。 Sometimes we also call it the variance in regression。

The approximation error is a deterministic quantity that says。

 even assume that you could find the best function in your class。

 how far would this function be from the base classifier？😊。

This is a property of your function space how how like is the true function contained in your function space if not or not。

 and if no how far is it away。😊，This has nothing to do with the finite sampling error。

 this is just the property of your function space。And the typical kind of statistical learning theory paper。

 at least in the kind of series of resultss that I'm going to present here。

 typically considers the first case， the estimation error and not so much the approximation error。😊。

Okay。The algorithm that traditional or many results in learning through are concerned with is empirical risk minimization just to recap the true risk of the function。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_172.png)

Is the expected loss of a function or is the loss function the empirical risk is the loss that we can compute if we just look at our training points。

😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_174.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_175.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_176.png)

And then risk minimization is the algorithm that simply once if you're given a data set like training points with training labels。

😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_178.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_179.png)

In the function class， we pick the function in the class that minimizes the expected risk like the training loss on this particular sample。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_181.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_182.png)

And what we have seen earlier in the beginning of the lecture when we argued about when would empirical risk minimization maybe work and when wouldn't it work。

 we argued that it is probably not going to work if this function class is too large。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_184.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_185.png)

And this is now what we want to make precise in this field of statistical learning theory。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_187.png)

The tool by which we are going to make this notion precise is the tool of generalization bonds。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_189.png)

When we are going to talk about generalization bounds。

 there is a number of tools from probability theory involved in all the proofs。😊。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_191.png)

And we now want to look at all these kind of tools and inequalities that we need to prove these results。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_193.png)

The first effect that we need， and I think most of you would know it is the law of large numbers。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_195.png)

So I have here a very simple version of the law of large numbers so essentially intuitively the law of large numbers says if I take an empirical mean and I increased asem size。

😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_197.png)

Then the empirical mean is going to convert to the true underlying sample mean。

If I want to know what is the mean height of a person in Germany？

I can take a symbol of 10 people of 100 people of 1000 people and always estimate what is the mean in this population and this value is going to converge eventually to the ground truth value of the mean height of a person in Germany。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_199.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_200.png)

Formerally， it works as follows。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_202.png)

Lets see eye。I index from one to as large as you would like in the natural numbers that be a sequence of independent random variables。

😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_204.png)

That have been drawn according to some probability distribution P。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_206.png)

In the easiest case， you would assume IID here， like independent and always drawn according to the same distribution。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_208.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_209.png)

Do you know what the expectation is expectation of seeing？



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_211.png)

Then under my assumptions， the empirical sample mean is going to converge to the expectation of the random variable。

In one of the ways that are typically stated in probability theory。

 you can make this almost truly or imp probability， whatever， that's not so important。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_213.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_214.png)

So as I said the intuion is the empirical mean is going to converge to the true mean and the Ro undermine assumptions。

 there are millions of versions of the law of large numbers with less or strong assumptions。😊。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_216.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_217.png)

Let us just say that in learning theory， as long as we have independence。

 they tend to be satisfied if you go beyond independence it gets a bit more tricky。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_219.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_220.png)

Sorry maybe one more thing why are we interested in this law of large numbers consider the variable Z here P just the loss on one particular data point then e of c is the expected loss of the underlying random variable so essentially we have a situation where we want to talk about the convergence of an empirically mean to a true underlying mean and this is why the law of large numbers might be important。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_222.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_223.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_224.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_225.png)

Now， the law of large numbers simply states that the thing is going to converge。

 but it doesn't state how fast。😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_227.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_228.png)

Now there are very， very many and strong theorems about how fast this convergence is going to take place。

And these often take the form of concentration inequalities。

 And here is one that is particular simple， but also really important in the field of learning theory。

 the concentration in equality by hefting。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_230.png)

AndSometimes it's also called Cha of Pos， there are many many different ways how this is called in the literature。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_232.png)

And the serum now states， again， assume that we have these independent random variables。😊。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_234.png)

Now for simplicity we assume that the values of these random variabless are in a bounded interval。

 which for loss function you can often assume so in particular the 0 to 1 loss function is of course in the interval 01。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_236.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_237.png)

And the statement now says， consider the deviation of the empirical mean from the true mean。😊。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_239.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_240.png)

And consider the probability that this deviation is larger than epsilon。😊。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_242.png)

So the probability that your mean deviates by more than a certain threshold that you're willing to give。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_244.png)

This probability is bounded。From above by essentially 2 e to the minus2 and epsilon squared。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_246.png)

And now consider this expression in particular n is sort of the interesting number here because n is the number of sample points。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_248.png)

So what you can see is this probability converts exponentially fast in the number of sample points。

 so adding a couple of sample points really increases your probability that the empirical mean is close to the true mean increases by a lot。

😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_250.png)

And this is one of the main tools that we need to prove the simple generalization bound that we're going to look at at this lecture。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_252.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_253.png)

Now let's turn to binary classification。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_255.png)

So now the first proposition I want to make is consider a fixed function in your function class F。😊。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_257.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_258.png)

Then what we have is for this particular fixed function。

The empirical risk of this function converts to the true risk of the function， almost truly。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_260.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_261.png)

Now I would ask you to take a minute to go back in the slides and really see why this statement is true。

 why is it true that the empirical mean or the empirical risk converts to the true risk for this particular function？

😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_263.png)

You can maybe stop the video and then resume later。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_265.png)

Okay， I hope you have sort of come up with a couple of ideas why this might be true。

 here' is the true proof。😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_267.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_268.png)

We could simply apply the hefting inequality to bound the variables now CI the question is what is C I think I already hinted it earlier theI is going to be the loss。

😊，Of the function。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_270.png)

The fixed function that we given at data point X， I and Yi， so F is a fixed function。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_272.png)

For a fixed function， this is a quantity that only depends on XI and Yi and nothing I， nothing else。

 so this is a random variable that lives on the same or is like at the right random variable from the original ones XI and YI。

😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_274.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_275.png)

And this is a random variable like if X I and Y， IIT。😊，Then she。I's also IID。

And in particular this loss function is always between0 and 1。

 and so we can apply hefting serum and you get the conversionvers and probability。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_277.png)

If you want to， I mean just for those who know probability theory。

 if you want to get almost true conversiongs you need to do one extra step here。

 I mean there are many ways to do that but the one that is typically used in learning theory is you use the Brell Canli Lemon。

And for this you need to bound this infinite sum of all these deviation quantities and show that this is finite and then you get almost true convergence so if you know about probability theory you might do this as an exercise。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_279.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_280.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_281.png)

Now somehow you might think well we are already here so what else do we need to do。

 we know the empirical risk converts to the true risk are we done yet？So now the point is。

What we did in the previous statement is we said F0 is a particular fixed function。

And then once we fix that function， the empirical risk is going to converge to the true risk。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_283.png)

However， this is not what we are going to look at in a particular learning algorithm if you have some learning algorithm。

 we have a function FN。😊，That depends on the data。On which we also compute empirical mean。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_285.png)

And the question is now。And this is a question I would like you to think about。

Whether it is true that the law of large number implies that the risk of the function that we picked on the training data。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_287.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_288.png)

Converges like the empirical risk， converts to the true risk。嗯。

Or maybe stated in a slightly more convenient way because these functions change over time。

 whether the difference between the empirical risk and the true converges to zero。😊。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_290.png)

And my suggestion is please stop the video for a moment and try to figure out whether you think it's true。

 if yes， try to justify why it's true， if no， try to justify why it's not true。😊。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_292.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_293.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_294.png)

So the strong and very important answer to this question is no。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_296.png)

It is not true that the law of large number already implies the result that we want to have and here is a very simple counter example。

😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_298.png)

Consider you have a data space just a one dimensional space between points between0 and 1。

The labels are deterministic。😊，Every point that is below 0。5 has label minus1。

 every point that is above 0。5 is labeled plus1。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_300.png)

Sort of the simplest of all learning problems。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_302.png)

We draw N training points from this save from the Unii distribution here。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_304.png)

Now we define a classifier， it's an empirical risk minimizing classifier。😊。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_306.png)

For all points in the training sample， we simply predict the training label。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_308.png)

I mean， we simply I mean we do a lookup table， our training examples。

 we copy the training examples into a lookup table and say whenever the test example is one that we've seen before。

 we output the same result as our training data suggests。😊。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_310.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_311.png)

And for everybody else， we simply predict minus1。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_313.png)

And now you can look at what happens， what is the risk in the empirical risk so the empirical risk of our function of n is of course0。

 so in particular the function does minimize the empirical risk it can't be below  zero so it is an optimal function from this point of view。

😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_315.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_316.png)

But of course the true risk of this function is 0。5 for all and because we essentially get half of the data points wrong because everybody who is in the upper half of like between 0。

5 and1 should get labeled plus1， but our classifier gives minus1。😊。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_318.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_319.png)

So， all these points are going to be classified wrongly。

 and this is the case for all n independently of n。😊。

And so definitely this term Rn of FN does not convertverge to R of FN。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_321.png)

The counterex shows us that something must be wrong with the at least if we would try if we would hope that this law of large numbers is going to prove our results it simply does work so either the law of large numbers is wrong or we do something wrong in applying it。

😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_323.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_324.png)

And of course， it's the second point。To see this， let us maybe go back to this particular statement。

😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_326.png)

So what we stated here is for a fixed function F 0。😊。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_328.png)

The law of large number implies that the empirical risk converts to the true risk。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_330.png)

The point is here， if we now look at not a fixed function。

 but a function that also depends on our data point。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_332.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_333.png)

Then there's sort of it's more involved because the function of n depends on the data and the empirical risk depends on the same data。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_335.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_336.png)

And then it somehow cant be true that if we look at like this independence breaks because the function like if we define this random variable。

 this one here， Z I， the loss of f0 of Xi and Yi， I earlier said that if f is a deterministic function and Xi and Y are independent then of course these random vers are independent as well。

😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_338.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_339.png)

However， if F0 is a function that depends on the data points。

 X I Yi as well and it depends on all data points， not just on point X。😊。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_341.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_342.png)

Then this independence breaks， and then we cannot apply the hefting bond anymore on the low of large number or any of these bonds。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_344.png)

This is the mathematically explanation for why it goes wrong。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_346.png)

Now the question is how can we cure it or is there any way in which we can now solve the problem and the answer is of course yes。

 and the answer is going to be to look at uniform convergence。😊。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_348.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_349.png)

So what do you want to have？We want to find a condition。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_351.png)

That is sufficient for the convergence of the empirical mean to the true mean for the data dependent function Fn。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_353.png)

And now the problem is we don't really know we have this function space F N。

 we know we are going to pick one of these functions。

 but we don't know in advance which functions we are going to pick。

Now we do something that sounds like a very crude approximation but that does the trick。

 we now simply say we want that for all functions that live in this function space。😊。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_355.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_356.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_357.png)

Uniformly， at the same time， when we compute the empirical risk of the function。

 it converts to the true risk of the function。And this should hold uniformly over all functions at the same time。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_359.png)

So if you write this down formally， it means what we want is we look at the empirical risk of a function minus the two risk。

 that' is fine。😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_361.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_362.png)

But we take the supreum over all functions in our class。😊。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_364.png)

And we want to ensure that for all functions in this class uniformly。

 this expression is smaller than epsilon。😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_366.png)

And if this is true， then we can of course say well。

 no matter which function or algorithm is going to pick。

 all of them are going to be close to the empirical risk。

 so the same is going to be true in particular for our function f n。😊。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_368.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_369.png)

And what this then would mean is it would mean so this statement does not mean that all these functions are great classifiers。

 it just means that the risk that I compute based on the training sample is close to the true risk and so if I would select a function based on the empirical risk the empirical risk is a really good indicator for the true risk so if a pick a function that has a small empirical risk then it is very likely that also the true risk is going to be small。

😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_371.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_372.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_373.png)

And the reason is because we have this uniform conversions。

 we we don't really need to care about which function exactly or algorithm picks。

 it is going to hold no matter which function or algorithm is going to pick。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_375.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_376.png)

And now we need to think about like if you covered up with such an idea to fix a problem that you had in an earlier example or application。

 you might want to see well， would this kind of notion fix the problem that we had earlier？😊。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_378.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_379.png)

嗯。And so what we would need is so what we are aiming for obviously is we want to try to prove that if we have a quantity that looks like this。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_381.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_382.png)

Then everything is going to work out and the true risk of the classifier that we picked is going to be close to the empirical risk。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_384.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_385.png)

Now the question is somehow this must not work for the example that we have seen earlier because otherwise this approach would also be doed。

 so something needs to break if you try to prove this kind of result it should not be possible to prove it for this example with this constant function where we just pick different points on training and test different labels on training and test samples。

😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_387.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_388.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_389.png)

So I would ask you， maybe as an exercise。Look at the counter example we had earlier。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_391.png)

And try to see whether you believe that this uniform conversionvert statement about the supre is true in this particular case or not。

I hope you find out that it's true。😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_393.png)

Because this is what we are going to hope for。😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_395.png)

嗯。Please try it on a piece of paper。 If you don't find it。

 then you need to talk to your teaching assistant， maybe because in fact， this is true。 I mean。

 this this example， okay， but is true。 The counter example does not satisfy uniform convergence as we have defined it earlier。

So this gives us hope。That this framework of uniform convergence might do what we need here。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_397.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_398.png)

Okay， and now how do we invoke this uniform congence， we now make a definition。😊。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_400.png)

We say。That the law of large numbers holds uniformly over a function class F。If for all epsilon。

 we have that the supreum of the risk， the tourist minus the empirical risk。

The probability that the supreme is larger than epsilon goes to 0 as n to infinity。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_402.png)

And the important aspect here is also at least for now that the supreum is inside the probability。😊。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_404.png)

Because otherwise you could have very different speeds of conversions for different functions。

 and then it could be that while one function has already conged for the other function。

 we are still miles away and then again we couldn't really rely on the result。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_406.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_407.png)

At least for now， the Supremepremon was inside。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_409.png)

Okay， now the first statement that we are going to look at is the following uniform convergence is sufficient for consistency。

😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_411.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_412.png)

Let's look at the statement。Let Fn be the function that minimizes the empirical risk in some function class F under the same scenario as we had before our probability distribution data upon sample IID and so on。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_414.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_415.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_416.png)

Then what we have is the probability。That the risk of this function that we picked。

Diates from the risk of the best function in the class。

The probability that this is large so that we're in the bad case。This is bounded。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_418.png)

By the probability of the supre thing， just that here we have now a term epsilon half and here we have Epsilon。

 but this is nothing that really bothers us。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_420.png)

And now observe this first term here。 This is the one we're really interested in。

 We have this function F N that we pick from our algorithm。 We want to know。😊。

How bad is it that we only see a finite sample instead of the whole distribution， So we want to know。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_422.png)

What isBecause we have only a finite sample to pick up this or to identify this function FN。Now。

 what were interested in in ultimately is the true risk of this function。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_424.png)

Because this is going to be our test error， essentially。

And this would be close to the true risk of the best thing that we could have done if we had I don't know if we had all the knowledge about our data and about our function class。

😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_426.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_427.png)

And the statement is now this term that were interested in is bounded by the probability that states the uniform convergence property。

 so if this probability goes to zero，😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_429.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_430.png)

Which is what uniform conversion states then here the probability of the term bere really interested in also goes to 0。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_432.png)

And the proof of this particular statement is really easy。

 essentially it follows nearly from the definitions by the triangle inequality more or less。😊。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_434.png)

So this is the term were interested in the one on the left hand side。😊。

Absolute value of the risk of F n minus the risk of the best in the class。

And now observe that we can drop the absolute value because we know。

 I mean this is the true risk in both cases and we know that the risk ofF the best in the class because it is the best has to be smaller or equal to this risk here。

So we can simply drop the absolute value。 We know that this term is always positive or not negative。

 at least。Now what we do is so now we're here。😊，We now introduce a couple of terms that are like that by introducing them don't make any difference but later on are going to make a difference。

 so we introduce the term minus Rn of fn plus Rn of fN so this is0 so we can introduce it。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_436.png)

And we also introduced the term。Mineus Rn of FF plus Rn of FF。

 so essentially we introduce the empirical quantities of the two terms that we are currently interested in or the two functions that were interested in。

Now we observe that one particular aspect we can again drop this guy here。

We know that because we look at empirical risk minimization。

 Fn has the smallest empirical risk RN in the class。

 so this term here is definitely larger or equal to this term here。

Because it might be that on this finite sample， F F does not have the best of all risks。

So we know that this expression。😊，The way it is stated here so this first risk is smaller than the last risk。

 so this expression is smaller than 0， but this is by the definition of fF fn。

 so we can drop it so we are left with this expression in our observe we have twice a similar statement we have R of fN minus Rn of fN。

And here we have essentially the same just with FF。So we can bound this by saying， I mean。

 both terms would definitely be bounded by the supreum over the distance between the twin and empirical empirical risk of all functions in the class。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_438.png)

And we have a factor of two because we have two such terms。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_440.png)

And this is the statement that we want to have。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_442.png)

So observe the important fact that we are aiming here for is thats maybe not so obvious here we have a statement that is in both terms in terms of the true risk because that's what we're interested in but what we achieved now is we have a term that is once looks at the true risk and once at the empirical risk and this is what we are going to exploit in the future。

😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_444.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_445.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_446.png)

Okay， so we have seen that uniform convergence is sufficient to learn。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_448.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_449.png)

Now the question is， of course， is it also necessary？And the answer is yes， and that's a very。

 very deep result that has been proved， I think for the first time by Abpni and Chavoin is in 1971。😊。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_451.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_452.png)

Oberve Lalaveabpnik is the person we have seen before。

 he is the one who also invented support vector machines or at least had a large contribution here。

 and he is the one who came up with this theory like essentially 20 years earlier in Russia at this time he was still in Russia so this was a purely mathematical result。

😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_454.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_455.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_456.png)

嗯。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_458.png)

That also wasn't connected in any way to learning。 It is about uniform consistent or uniform convergence of empirical quantities in。

 in statistics， in fact， or probabilityba theory。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_460.png)

So， the theorem says let f be any function class， then empirical risk minimization is uniformly convergent with respect to F。

 so the thing they will be interested in，😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_462.png)

If and only if uniform convergence holds。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_464.png)

And we have seen one direction earlier。The other direction that is necessary is really a deeper result and we cannot prove it in this lecture。

😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_466.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_467.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_468.png)

So this is nice， but now the big question is of course， now if you have a certain function class。

 how would you know whether you have uniform form the uniform consistency in your particular function class F。

 so say you use a support vectoror machine with a Gaussian kernel does this lead to uniform consistency or not。

😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_470.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_471.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_472.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_473.png)

It sounds like， I mean if you look at the theorem it sounds like we moved from one complicated expression to another complicated expression。

 I mean definitely this expression looks really complicated from a mathematically point of view and the question is now are there any tools that would help us to bound this expression？

😊。

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_475.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_476.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_477.png)

And then at a second step， sort of bounding this or giving us consistency。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_479.png)

And the answer is yes， and the answer is going to be capacity measures for function classes。

 and we' are going to treat them in the next lecture。



![](img/e60b3392cbc3c452c7b4a8aa7f46186b_481.png)

![](img/e60b3392cbc3c452c7b4a8aa7f46186b_482.png)