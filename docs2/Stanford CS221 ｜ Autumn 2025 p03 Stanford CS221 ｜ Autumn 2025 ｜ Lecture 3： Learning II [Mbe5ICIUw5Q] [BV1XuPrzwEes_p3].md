# Stanford CS221 ｜ Autumn 2025 p03 Stanford CS221 ｜ Autumn 2025 ｜ Lecture 3： Learning II [Mbe5ICIUw5Q] [BV1XuPrzwEes_p3]

![](img/f92022e820477c26e0a94cb171efe655_0.png)

![](img/f92022e820477c26e0a94cb171efe655_1.png)

Okay， so today's lecture is going to continue our journey in machine learning。

 We're going to talk about linear classification。So last time we talked about linear regression。

And there the prediction task is of regression is you're given some sort of input and you're trying to predict an output。

 which is a real number。So think about this as a price or some sort of score。

And because it's linear regression， that means the hypothesis class are linear functions。

So today we're going to talk about linear classification。

 so classification means the prediction task is taking some input and producing an output which is no longer a number。

 a real value number， but a discrete choice， so other no wise known as a class or a label。

 and it's usually one of k things where k is might be two or5 or even 1000。

And because it's linear classification， the hypothesis class is going to be linear functions。

 but as we'll see later， it's not quite linear， it's almost linear because you have to do something at the end。

So let's go through the motions， remember what we did for a linear regression and see if that applies to linear classification。

So let's start with a prediction task。So an example of a classification task might be image classification。

 you're given an image， for example， this image， and you're supposed to output a label。

 which is what kind of object this is， in this case， it's a cat， I think。

Another task might be sentiment classification。 you're given an input， a text document。

 and you're trying to output the sentiment of that the document is conveyed。

 either positive or negative。Okay， so what is， what is actually the input here。 So in an image。

 last time， remember， we talked about images as essentially tensors。

 which are width by height by the number of channels， RGB。 So there's three channels。

That's fairly straightforward， a text， well it's a string， so it a string is not a tensor。

 we're going to come back and revisit this。But for now。

 let's just assume that our input is a vector or tensor。So what is the output so for classification。

 the output is always one of K choices， so when k is 2， that's called binary classification。

 usually the output space is denoted as minus1 for the negative class and plus one for the positive class sometimes you also see zero and1。

 but in this class we're going to use minus1 and plus one as a convention。Later。

 we'll also see multiclass classification。Where the output is one of K choices。

 usually in code it would be 0 through k minus1 in math， you might see 1 through K。

But the ideas are the same。So a predictor is a function that takes an input and produces a prediction。

 a predicted output。So for binary classification， it might look like this， so you have an input。

 let's say， Xa。Which is the vector of 1，2。And。I'm going to send it through the simple binary classifier。

And what this will do is。This is just an example， it I take the first component and subtract the second component of -1。

 so 1 minus-2 minus-1 is -2， and then I'm going to look at if this is greater than 0 then I'm predict predicting1 otherwise I'm going to predict -1。

 so in this case I'm predicting -1。Okay and here's another example， XB2，0。

 I send it through the predictor， I get a logic of1， so2 minus0 minus1 is1。 and in this case。

 I predict one。so the first example is labeled minus or negative。

 and the second example is labeled plus。So you can visualize this here， so the first example is here。

1，2， and the second one is 20， so each data point is two dimensional so I can just plot all the input points。

And one thing that's a useful concept is this idea of the decision boundary。 So the this。

 the decision boundary are points where it， it sort of could be either way。 It's as's a toss up。

So if you look at what this predictor is doing， x0 minus x1 minus-1， if this is0。

 it's sort of like at the boundary of plus n minus okay。

 so if I plot the decision boundary of x 0 minus x1 minus-1 is0， then I get this boundary here。

And the decision boundary in the input space separates all the points which are classified negative on this side。

 from all the points which are classified positive on this side。And in this case。

 I've broken tie sort of arbitrarily by saying if logicit is0， that's still a minus1。

 but you could have put a greater equal to if you want to。Okay。

 so I've shown you an example of a particular predictor and given this it happens to be linear and given this predictor。

 I can show you what it does on inputs。 it classifies inputs either to plus1 or minus1 and we can visualize it on in this input space。

So there's no machine learning yet， because the key question is。Now， how do we get this predictor？

 So far， I just wrote down by hand， a particular predictor。 But of course。

 when we're doing machine learning， we're not interested in writing predictors down by hand。

 we want to learn them。So remember from last time， just a bit of terminology。

 the training data is a set of examples that demonstrates the task in particular。

 each example is an input output pair where the input is usually denoted X。

 and the output is denoted y， which is the target， what we want an ideal predictor to produce。

So in classification， the training data might be1， two is the input and the target is minus1。

 two zero is an input， I want the output to be1， 00 I want to be minus1。Okay。

 so those are three examples in my training data。And I can put it up here， and。

I can visualize it as well， points are easy to visualize in 2D， so I have a minus1 here， sorry。

 that is a positive point here and two negative points here。

Us you would do more of machine learning with way more points。

 but this is just an illustrative example。Okay， so that's the train data。

 and a learning algorithm is going to take this trainee data and produce a predictor。

 And remember what is a predictor。 It's a function that maps input to output。

 If for classification represented as a decision boundary。 So effectively。

 I want to figure out a predictor or a decision equivalently。

 a decision boundary that cuts up the space into positives and negatives。

 So intuitively in classification， if I see a bunch of minus points here and plus points here。

 I probably want to draw the decision boundary somewhere along here。

And that corresponds to also equivalently a function that takes any input point and produces a label plus 1 or minus1。

Okay， so that's the learning problem。And now the key questions to actually concretize this are threefold。

What are the possible predictors。That's the question of a hypothesis class。

How good is a predictor to determine that we define a loss function。

 And then how do we compute the optimal predictor or the best predictor。

 And that's going to be within the realm of the optimization algorithm。Okay。

 so we did this for linear regression。 Now we're going to go through the three steps for classification and we'll see how far we can get。

Okay， so so far I talked about the prediction task and what a learning algorithm is meant to do data to predictor。

Okay， so let's move on now to the first question， which is， what predictors are we going to consider？

I've sort of foreshadowed this already， so this part shouldn't be too surprising as before we want to parameterize our predictors。

 which means that we want to define a set of parameters。For each predictor。

So in the case of linear classifiers， the parameters include a wave vector and a scalar bias terms。

 so in this case， we might have a wave vector which is1 minus1 and a bias， which is 1。Okay。

And I might have an input 11， which is a two dimensional point。And。I'm going to define the predictor。

 which takes these parameters and an input and makes a prediction。

So what this binary classifier is going to do is it takes parameters and an input。

 so parameters and input， and it's going to compute what is called a logic。

So it just takes the do product between the wave vector and the input vector and adds the bias。

 So in this case， I have one times 1 plus -1 times1 that gives me 0 add the bias。 and I get -1。

 And that's the logic。So and you know， as before with a fixed predictor。

 I can look at whether the logic is greater than zero or not and use that to make a prediction in this case the logic is negative so I predict minus1。

Okay， so。So I've drawn again the decision boundary of this particular predictor。

And this particular point， it gets classified as minus1。Again， I can look at another predictor。

 so this one has the same weight vector but a different bias。

 I feed in the same x and let's see what happens here。

 so I compute logic it this time the dot product is still zero and add the bias which is1 and therefore I predict1。

So now the point is still in the same place and the decision boundary has shifted up。

 and now the point is lying on the positive side of the decision boundary。Okay。

 so I've shown you two predictor in general， you can use imagination。

 there are an infinite number of predictors， which are corresponds to all the different ways you can cut up the two dimensional space with a straight cut。

Okay， so the hypothesis class is a set of all predictors you can get by choosing weight and bias in any way you want。

 and all these essentialion boundaries are straight line cuts。

 so no curves allowed because this is linear classification。

So the question is most of the time linear， so most of the time the actual task is probably not linear。

 linear already is a very fragile and special notion but people often use linear classifier because as you'll see they're fairly simple and there are few number of parameters so you don't overfit as much。

 there's a bunch of nice properties they're conveed and so on。Once so you might think， okay， well。

 well， that's kind of dumb because a linear classifier clearly is really limited。

 but it turns out that if you have are in high dimensions， if you have know 10000 dimensions。

 linear classifiers are actually very expressive。 So it's not as bad as it looks。 Of course。

 you can do more than if you go beyond linear classifiers。

 which we'll talk about when we talk about neural nets。So now let's go to the second question。

 which is defining a loss function。 So in particular， a loss function is going to be a judge。

 give me a predictor， give me a training set and tell me how good the predictor fits the training data。

So let's let's consider our predictor here。And let's get this training data。

 So we are defining a loss function that takes these two things and returns the number。 Basically。

 how happy are we。So how well does PRs fit the trainee data？And to do that。

 we're going to start with one data point。 let's say this one。

 and we're going to define a loss function that measures how unhappy one point is with the parameters。

So remember for linear regression。Or regressionpression in general， we use the squared loss。

So the intuition basically is that we could lose based on how far away the actual prediction is is away from the target。

So just if you recall the squared loss takes an example。

And takes the input takes the multipliers by the weight plus the bias。

 and that is the prediction is -2。 The target is minus-1。 so we sort of missed we're close。

 but we missed okay and the amount we missed is the residual which is minus1 and if you square the residual that's why it's called a squared loss you get a loss of one。

 so we missed by so we would suffer a loss of one if I on this example if I have these parameters。

Okay， so， so that's for regression。And we could plot what that loss function looks like as a function of the residual。

 which is how far we're off the target from the loss function。

 so as you see zero is where we've landed it so this is generally you want a property if you get the target correct。

 if you line a target you should have zero loss zero and if you the only question is if you're off know in what ways are you penalized。

So the square loss has pretty steep。Curves， which means that if you go away even a little bit。

 you're going to have quite a large slot。Okay， so we could just use this loss function for classification。

Okay。So why might we want to use it or not use this for classification？

So the loss wouldn't tell you which side of the classifier it fell on。 Yeah， so。

 so to put in other terms， we're trying to。Pdict a number and so so I'll give you the pro first right。

 The pro is that the square loss works because if you get the answer correct。

 if it's the true target is one and I predict one， then I get a loss of zero。

 And if I predict minus-1。 where the true answer is one， then I get two squared， which is4。

So in some sense， it works， right because if I minimize the loss all the way to zero。

 I get the training set perfectly。Yeah， so the idea of a residual doesn't quite make sense。

 It's a little bizarre。 I mean， it's type checks， right， because you have1 and -1 in。

 but there's only really two values。 I can get a residual of0 or it can get a residual of 2 or -2。

 I guess， but which gives you a lots of four。So somehow。

 this idea of classifying based on which side of the decision boundary isn't really being captured here。

In particular， let's say the target is one and I predict four。

 then I'm going to get penalized and I'm going to predict 8。

 I'm going to penalize even more and those that feels kind of wrong。

 in some sense I'm actually saying if you interpret the logic of eight as being positive with very strong confidence then I'm getting penalized a lot more for that。

So its this loss， I would say， is it's okay。 It' it's not completely crazy。

 It's just a little bit off。Okay。So let's just think from first principles。

 what do we want in binary classification。We want to classify correctly。 Okay。

 So what we're going to do is define the 01 loss and the 01 loss says， well。

 does the prediction essentially have the same sign as the target？ We don't care about them。

 the magnitude， because。We have the decision boundary， everything on one side should be plus。

 and everything on the other side is minus。 I don't really care how far it is。Okay。

 so let's do a quick example here。So if I have the data  point 20 and the target is 1。

 I send it through these， these parameters。First of all， I'm going to make up a prediction。

Using my current parameters， so I'm going to see how well I do。

 so have I showed you this binary classifier before， I compute the logt。

 threshold the logt if it's greater than zero， I predict1 and in this case the predicted y is 1。

 the target y is 1， and then I'm going to just define the loss to be whether these are different。

So this returns a boolean and inch just converts true to 1 and false to zero。

So then that's why it's called a zero one loss is it's0 or1 where zero represents I'm correct。

 and one represents I'm wrong。Okay。So let's do another example。

 So I have 0 minus-2 with a target being -1。 So in this case， I make a prediction of one。

And my target is -1。And so that is just going to give me a loss of one because I misclassify this example。

Okay， so it's fairly straightforward， zero1 loss basically says。

 did I classify it incorrectly or not？And one thing to note here is that I want you to start thinking in terms of loss function as something that's really custom。

 You can define a loss function to capture what you care about。

And I know there's these standard things like zero loss。

 you might have heard of logistic loss or squared loss。

 these are just standard things that people use， but they really are meant to capture what you care about in a problem and you can define your loss to be essentially any function and that' will give your own custom variant of a learning procedure。

Okay， so so so far so good， so I'm going to define the zero on loss as whether I the parameters driven predictor classifies this example incorrectly。

Okay， so now I'm going to play with a zero mod loss a bit。

 I'm going to write it in this in terms of this quantity called the margin。

 which will make it easier to do。Later things， so bear with me for now。

 So  zero1 loss in line is basically the same thing as a zero1 loss。

 but I'm just going to write it differently。And what I'm going to do is compute the logic。

 which is the do product of x and the wave vector plus the bias。

And now think about what the logic is doing so that s， whether it's positive or negative。

 is the prediction。And the magnitude is essentially how confident we are on the prediction。

This is sort of intuitive because if you have a large number。 if you predict 1000， that means it's。

 you know， plus 1。 I really think it's positive as opposed to you know， a loative like 001。

 which means that it's， it's barely positive。Okay。So。

 but the sign is what determines the ultimate classification。

So now I'm going to define the margin as simply the logict times the target y。

 So the target y is plus1 or minus-1。And you can just think through the cases here。 Okay。

 so what is the sign of the margin。The sign of the margin measures is basically whether you're correct or not。

OkaySo if the logic is positive and the target is plus one， then this will be plus positive。

 if the logic is negative and the target is minus-1， then this will also be positive。

So regardless of what the label is， as long as the sign of the logic matches the target。

 I'm going to get plus one， and if they have different signs， I'm going to get minus1。

So so this is a little bit of a shorthand trick just to compress into one number。

 something that measures where whose sign measures correctness。Okay。

 so now I'm just going to define the loss of whether the margin is not positive。Okay，So this。

 if the margin is negative， then that means the loss is going to be。Wan。

And if the margin is positive， that means the loss is going to be 0。Okay。

 so I'll let you mo on this for a bit and convince yourself that this is indeed exactly the same function as a zero on loss。

 but just written in this probably， somewhat mysterious way。Okay。

 so I've introduced a few notions here。 though there's a logic。Which is。Basically the prediction。

 sorry not the prediction， but the raw prediction， let's call it that and the margin which basically measures correctness。

 and then finally I get the loss。Okay， so maybe itll help if I visualize this。

 So if I'm plotting margin。And the zero loss， then I see that if the margin is ignore this。

 this is an artifact， it's supposed to be a straightray line down， if the margin is negative。

 then a loss is one if the margin is positive and the loss is zero。Okay。So in general。

 for classification， I'm going to look at these plots which measure margin loss as a function of margin。

 whereas for regression， I talk about loss as a function of residual。Okay。

 so margin is sort of a classification analog to residual。All right， so now the training loss is。

 again， the average over the per example losses。So if I have set of parameters and I define the train zero on loss。

 which now is going to compute the losses one for every training data point as before。

 and I'm just going to take the average and that's going to give me the training loss。Okay。

 so here the training loss， if I use the zero and loss is in other words it's the。

It's the error rate。Because one， I get a1 if I messed up and0 if I don't。

 so the average over those zeros and ones is exactly the fraction of examples that I misclassified。

Okay， so it's a very， very nice site and an intuitive quantity。Okay， so just to summarize。

 the logict is this raw score from the linear part of the model。

 and the sign of the logicit is the prediction。Which is positive or negative。

 And the magnitude is essentially how confident you are。

 The margin is you take the loging multiply by the target。

 and now the sign is whether the prediction is correct or not。

 And the magnitude of that margin is essentially how how correct you are， in some sense。

Zero on loss is defined in terms of margin， one， if wrong， zero if right。

 and training loss is the error rate， which averages over the training examples。Okay。

 so now we're done with the。The second question， which is what loss function am I optimizing。

 I want to optimize a zero on loss。 and now we're off to the races， we can do optimization。 Okay。

 so remember that for every setting of the parameters， we can compute a training loss。Okay。

 so in linear regression， we optimize the parameters using gradient ascent。

So let's try to do the same thing here。OkaySo I have my parameters， I have my data set。

 and I have this ability to compute the training loss。

And now I just want to do gradients asscent on this loss function。Okay。

 so let's compute the gradient of the zero loss with with， let's just start with a one example。 Okay。

 so I'll have the logic and the margin。And then I noticed that the gradient is what's the gradient of the zero and loss。

It's zero。Basically everywhere， almost everywhere。Except for when the margin is zero。

 and then it's undefined， but that's not that interesting。Okay， so that's。That might be a problem。

 Okay， so the gradient is 0 everywhere。 And if you look at this。

 you should be able to see why the gradient is 0。 right if you're sitting up here。

The gradient is zero， if you're sitting down here， the gradient is zero。

So the gradient is literally zero everywhere， except for at the margin zero。

So what happens if you run gradient descent on this？Is that you compute the gradient。

 you move in the step direction of the gradient， which is 0， and you。Don't move。

So gradient descent is not a very good way to optimize- actually。

 it's a completely ineffective way to optimize their zero on loss。So okay。

 so intuitively what's going on here is that with a zero1 loss。

 you're very sort of binary or discrete about your choices。

 So if you happen to be have a margin over here。And remember the gradient is a very local notion。

 it says， if I move my parameters a little bit。How much can I reduce the loss？

 And the answer is like， not at all。Like you can't make small changes to your parameters and move the zero lots。

 you have to move it a lot get to move from over here to over here。

 but there's nothing you can do over here。So local notions just don't work。

So it turns out there's actually many ways to fix this， infinite number of ways to fix this。

 actually。 but I'm going to give you one particular way to fix it。

 And this will require changing the loss function。Remember。

 I told you the loss function is something that is a custom thing you can play with。

 You can put it in whatever loss function you have。

 and you want ideally the loss function to capture what you care about in the problem。 but as we see。

We care about the Iran own loss， but we also want the loss function to be something that's amenable to optimization。

Okay， so sometimes these things are in conflict， but we might do with what we have。Okay。

 so we're actually going to take maybe a deeper conceptual turn and think about what the classifier outputs。

So let's go to this example here， I have a set of parameters， and I have my example。With the target。

 And so far， our predictor。Comp logic and what it does is it just outputs a single prediction。Okay。

And it， it is really kind of in this binary classification fire where things have gone wrong。

With respect to what we can， how can we solve this problem。

 Because the binary costifier produces predictive y， and there's no margin。 It got swallowed up。

RightSo I've lost already if I'm outputting just a single prediction。And this idea of thresholding。

 So if you remember the binary， where to go。Binary。So this will do。 So the binary cause。

 it does a thresholding。 I said if this， then something， if it's other way do something else。

 And that's just going to。Is a very discrete operation if statements are very disc。So what instead。

 we're going to do is we're gonna to make things continuous。 So the nice thing about regression。

 was it was nice and continuous。 Like any small change in the inputs or weights caused small changes in the output that。

 therefore， gradient descent has some signal to latch onto。😊，But if I'm thresholdholding。

 then I just I kill that。So what we're going to do。Is we're going to think about。

 and this is sort of the conceptual leap here is that instead of a classifier outputting a single label。

 I'm going to have a classifier output a distribution over labels。

A probability distribution over labels， and probability distributions are a continuous object。

 And I might imagine with that， I can。I can make some progress。Okay。

 so we're going to step through this。 So the key to doing this will be what is called a logistic function。

 So let's talk about the logistic function a bit and explore its properties。So remember。

 a logic is just a number， a real number goes from minus infinity to plus infinity。

 It can be anything。And we want to convert the logic into a probability。Which and probabilities。

 as you know， are between0 and 1。So there's also many functions that do this。

 but the logistic function is a standard choice that has some nice mathematical properties。

 and it looks like this。So if the logic is minus very negative， then it gets mapped to zero。

 and then there's a sort of smooth transition and if it's large and positive。

 then it gets mapped to1。Okay， so mathematically， I'll step through what the logistic function is。

 So logicit is 0。 If I pass zero into logistic function， here's the logistic function。

So it exponential sheets， the minus logicit adds one and then takes the inverse。

So if I punch in zero， fat gives me one，1 over1 plus1 is 0。5。Okay。And that corresponds to this point。

 so if I put in 0， that's 0。5。So if I put in one， I get 0。73， so that's like here， if I put in 8。

Then I get 0。999。 So you can see that it doesn't take very many logic。Y。

 the logic doesn't have to be very big for the probability to be very， very close to one。

And this is because I have this。Exponential， whenever you see exponentials。

 you think like crazy stuff happens。 So I'm gonna get very close to to one as a result of that。

 And in the other direction， if I have a lo of -1， then my probability is 02627。 and then -8。

 then it gets very， very close to 0。😊，Okay， so this is the logistic function。

So you might ask where it comes from， there's another interpretation which doesn't really matter。

 but just for your edification。You can think about。

It's instead of mapping logics to probabilities going the other direction。

 So imagine you have a probability02。So then if you divide the probability with one minus probability。

 this is called the odds。So if I have 0。2 probability divided by 0。8， that's odds of 0。

25 or 1 over 4。Okay， so that's a familiar notion。 If you think about you know， betting and。

 and then if you take the log of that， that is actually exactly the logic。O。So just to double check。

 if you can take that logic and you can push it back through the logistic function， you get。

The same probability。Okay。So another way to think about the logistic function is that its the inverse of this mapping from a probability to log log odds。

Okay， so hopefully this part is clear is the logic goes to negative infinity。

 the probability goes to  zero， positive infinity probability goes to 1， and add 0。

 the probability is 0。5。Another fun fact is that if you take a probability。The correspond gelog 3。

And you negate the logic and put in -3。 You'll notice that。These actually add to one。Okay， so。

You know， if three could of so basically。Logistic of Z plus logistic of minus Z is always one。

Or in other words， logistic of minus z is 1 minus logistic of Z。Okay。Let's look at the derivative。

 it's actually pretty nice and simple。So the gradient of the logistic function or the derivative rather。

 is just。The probability times 1 minus the probability。And I'll leave this as an exercise。

 You can do it on a piece of paper。 It's not particularly in lightning。

 but the result is kind of neat。So。Which what this means is that the derivative logistic function looks like this。

 if you're far away from zero， then the derivative is vanishing。

 it goes to 0 and the derivative peaks at 0。25 when the logic is 0。

So one thing you might start kind of to think about is youll remember zero gradients are bad。

This is already saw this with zero on loss， it's also going to be bad from neural nets in general。

 gradient descent， zero gradient is not your friend when you're doing gradient descent。

And which means that if you have logics that are super big。

 that means your gradient might be in batch， not necessarily because this is only looking at one piece of the equation。

 but you might be a little bit worried。O， cool。So logistic function takes。Logs。

 which are between minus infinity infinity and maps them into probabilities。

 which are between 0 and 1。Okay， so logistic function was actually comes from the you 19th century。

 but it was first used in statistics in the context of logistic regression。

 So actually what I'm going to talk about is identical to logistic regression。

 and this comes from the 40s。Okay， so now we have our logistic function。 How do we use it？

 So remember， we have this predictor。 We didn't like how it was outputing just a single prediction。

 I'm now going to have an output a distribution over classes。

So I compute the logic and I can just declare that if I take this logic and push it through the logistic function。

 I'm going to interpret that as the probability of positive。And because of that cool identity。

 I showed you， logistic of minus logicit is the probability of the negative class。

And it's also conveniently one。 And these also conveniently sum to one。

 which is always good for probabilities。So in this case， I have 0。95 and 0。05。Okay。

So now I can take back， come back to the margin。 margin remember is how correct I am。

And if I look at the logistic function applied to the margin。I get the probability。

That I hit the target why。In this case， because the target is one。

That means probably if target is the probability of the positive label。 So I have 0。

95 probability of of the target， y。So you can see this might be helpful because before I was just saying oh。

 I predict one you know good enough。 and now I get a very fine grain notion of how much probability mass I'm putting on the correct label because 0。

95 is is good， but maybe I want to increase it to 0。

97 or something and and because everything's continuous。

 I can actually look at the gradient and tell me the direction to move to increase the probability。

 So even though I'm classifying this correctly， I might want to increase the probability of classifying it correctly。

Okay， so at this point， I have if I have an example。And I have a set of parameters。

I can get a number which tells me a probability that this classifier with these parameters is going to output this target y。

Okay。So there's a general principle which also comes from statistics。

 but we'll see it again in other contexts called the maximum likelihood principle。

 and it's very intuitive， it says maximize the probability of the training targets。 more generally。

 maximize the probability of the data under a probabilistic model。So in general。

 if you have multiple examples。Then you end up multiplying the probabilities because you it's like I want for x1 to get the target label Y1。

 and for x2。 I want to get the target label Y2。 And so I'm multiplying the probabilities。

 This is equivalent to summing the log probabilities。

Because I take the log of a product that's equal to the sum of the logs。

So I'm going to therefore I'm trying to make some progress toward defining the logistic loss。

 so now I'm going to look at the log probability of the target， not just the probability。

And then finally， the final step is that。I I still want， I want the probability of target to be high。

 I want to maximize this。 I also want to maximize the log probability of the target。

But in the context of loss minimization。I to turn this into a loss， I just flipped the sign。

 So the loss is minus the log probability of the target。

And so it depends on if you're a pessimist or optimist， if you're an optimist。

 you say maximized likelihood， if you're assimist， you say minimize loss。

 but there are two sides of the same coin。Okay， so for this particular example。

 I went through all these devations to compute a loss。Which is a number that I want to drive down。

Okay， so let me package up into a nice function for you。

 so the logistic loss takes an example and a set of parameters。And what I do is I compute the logic。

Which is。The sign is prediction， magnitude is how confident we are margin。

 the sign measures whether we're correct or not， the probability of the target is the logistic function applied to the margin。

 and then the loss is the minus log of that。Okay， so I now I have this the nice function。

 the logistic loss。 let's see what it looks like。 So remember the zero and loss we didn't really like because the gradient was0 everywhere。

 And if I plot the logistic loss。😊，Then， I see。This beautiful curve。

So the gradient is actually it's not zero anywhere。Which is interesting。

So over here it's definitely not zero， the gradient is you can think about what happens if you put like a ball here。

 you're going to just start rolling down。And this is saying that， well， if you're very， very wrong。

 then you should you know， move， increase the margin essentially。 And， But， but interestingly。

 even if you're here。Even if you're at margin three， the gradient is not zero。

Which means that the logistic loss is a little bit of overachiever。

 even if you've gotten the example correct， there's always， you can always improve the probability。

Okay。So that's the logistic loss。Okay， so once I define a loss function per example。

 then I can just define the training logistic loss as an average over all the examples。

 so I define loss losses for each of my training examples I take the average。

 and that gives me a single number that defines for this particular classifier how well does it fit my data。

And this is a very nice， continuous function。 Everything is continuous and differentiable。

 and I can take gradients of this。So the question is。

 why do I have to take a log probability to to get the loss。 So one could say， well。Probabilities。

 I want to maximize these probabilities。 Why don't I just maximize the probabilities。By convention。

 if you think about the what like the training error is generally average over the individual errors。

 So the average， in order to be able to average， I need to take the log so that I'm averaging the log probabilities。

You could so the other reason is that if you work directly with the probabilities。

 you're going to get underflow very， very quickly because probabilities are small and if you get a probability of 10 to the minus you know you 200 and you're gonna to just everything is going to go to zero。

 whereas if you take a log， then you have much more kind of space to work with。Alright。

 so let's move on。 So now it took also a little bit of a detour。

 But we finally got to the answering the second question， which is。

How should we evaluate predictors and we're now going to use the logistic clause？

Now let's go back and try to optimize the logistic loss function。

 and hopefully those will work this time。So。First of all。

 we have to compute the gradient of the loss for you know one example。

 So let's use this as an example。 and you might wonder。

 like isn't the whole point of doing the computation graphs so you don't have to do this。 And yes。

 indeed， I could have done everything in pytorch and we never have to actually compute a single gradient。

 but I'm going to go through this process just to show you that you， first of all， at this scale。

 it's very doable and furthermore by computing the gradient， you get additional insights sometimes。

Okay， so let's take the gradient of the logistic loss。

Okay so just remember the definition of the logistic gloss， I have the log。

 which is the do product between the input vector and the weights and the margin。

 which is a log times y， and then the loss， which is minus log of the logistic of the margin。Okay。

 so first there is。The gradient of the so derivative D D loss D logic。

 So this quantity is if I change the logic by a little bit， how much does the loss change。

 and this happens to even minus logistic times minus of the margin。

 basically you take this quantity you differentiate it with respect to margin。

 and this is what you get。And then once you have that， then by the chain rule。

 the gradient to the weights is this quantity， gradient logic at times。

The gradient of the logic with respect to the appropriate parameters， which is。

The example dot target times example dot X for weight and for bias， its。Just the example target。

I can just talk through a little bit of how this works so you see this log here。

 so minus here's a minus log of something is one over that do remember the derivative of logistic is the logistic times one minus the logistic so then that logistic and the denominator cancels and then you have one minus logistic which is the same as logistic of the minus so if that made sense great if that didn't you can I'll leave it as a homework exercise。

But the point is that you can compute the gradient of the logistic lots either using computation graphs。

 or you can just do some quick calculus and you have that。Okay， so now let's。

The the gradient of the training loss is just the average of the gradients of the three examples。

 So if I have。In my training examples， I compute the gradient of。The logistic loss for each example。

 and I get these three things here， and then I'm just going to average them。So notice。

 one thing is that the type signature。 So the gradient of remember is the same shape as the parameters。

 So if the parameters have weight bias， then the gradients also have weight bias。嗯。Okay。

And so I basically average the weights， average the biases， and this is the gradient。Alright。

So now it's not0， I can do gradient new descent。 So let's just run this。

 So Im going initialize in general for linear classification。

 it's okay to initialize the weights and bias to 0。 As we'll see for neural nets， you can't do that。

 Let's use a learning rate of1， which usually this is。You know， this is fine for this example。

 But generally， this would be probably pretty high for any practical application。

 And we're going to step through hourlistically 20 times each step you compute the loss。

 you take the。The gradient， and then you update the parameters in the direction of the gradient。

 and then you kind of do this over and over again， let's see。So you can see that the loss goes down。

And then。And then you see and this time I've plotted the learning curve。

 which is basically the losses that I've accumulated as a function of step。

 and you see that the loss is going down if I let this run for longer， it'll go down even more。Okay。

 so optimization seems to be working。 And if I look at the final classifier that I get。

 I get something like this， which classifies。This this point is positive and these points is negative。

 which means I'm getting the examples correct， but notice that the line is also。

 it's not like hugging this point and barely classs correctly。

 it's trying to push away from these points because the larger the margin is。

 the farther away from the distinct boundary， the higher the probabilities。Okay。All right， so。

That concludes binary classification。 I've talked about the hypothesis space。 I've talked about the。

 the loss function， tried 0，1。 that didn't work， tried logistic， and it seems to work。

 And I use gradient descent to optimize the logistic laws。

So the question is where does this boundary come from。

 So this boundary is a depiction of the parameters here。

So the parameters remember defines a function that predicts pla positive for some points and minus for some points。

And the decision boundary is when the。You know， basicallyically。

 the logicite is exactly zero for this linear classifier。Yeah， so this works for higher dimensions。

 so here there's two dimensions so there's three parameters for the two dimensions and plus a bias if it were 10 dimensions then it would be 11 numbers and it would be much harder to visualize but the math all works the same and the code also works the same。

O。So。That is binary classification。Now I want to talk about multiclass classification。

So binary classification， the output is minus1 plus1 multi class， that output is 0 through k minus1。

Okay， so let's review binary classification， we compute just a single number。

 a single logic for the input， and that sign of the logic is the predicted class。So in this case。

 if I get a logic of one， then the probability of positive is just the the logistic of the logic。

And probability of the negative class is one minus thatt。Okay。So how do I extend this to multiclass？

What I'm going to do is I'm going to define a weight vector for each class so you can think about a weight vector as kind of representing some sort of information about what each class is about。

That will allow us to compute a logic for each class。And then given that vector of ws。

I'm going to do some。Stuff to make it a distribution。Okay， so again。

 we learned our lesson with binary class。 We don't just want to do 0，1 loss。

 We want to do something probabilistic。 And in the multiclass classification setting。

 I wanted a probability distribution over all K labels。Okay， so let's work through this example。

 So suppose I have three classes。 so my weight vector weight matrix now is going to be wave vector of dimension 2 for the class 0。

 class 1 and class 2。And the bias is also going to be a bias for each class， class 0， plus 1。

 class 2。And so now I have this input here， I can compute the logicits。

Whi is taking X and it's actually conveniently the same notation as before。

 but now I'm doing it for every class instead of a effective a single class。I add 3，3，0。Okay。

 so1 times 2 plus0 times 1 minus1 is3 or sorry， plus1 is3 and so on。Okay。

 so I have a logic for every class。Now， how do I turn logicits into probabilities？Okay。

 so I need another function before I had the logistic function。

 which turned a logic into a probability between 0 and1。 now have a vector of logics。

So what if I just apply the logistic function on each logic or that， is that going to work？No。

 because remember the probabilities have to sum to one， they have to be coordinated。Okay。

 so I'm going to introduce a function called the softm， so the logistic function maps。

Just a single number， the soft math function generalizes multiple classes and applies to a vector。

So the logics， let's just do this by example。 So suppose I have1 1 minus-1，0。

 and what does softmax function do？First of all， it's going to exponentiate each of the lots。Okay。

So e to the zero is 1， e to the minus1 and something less than 1， and so on。

And then I'm just going to normalize by normalize， I mean sum these up and divide by that number。

 So I get this distribution that sums to one。And you can see that in general。

 higher logicits means that higher probability。But it's sort of a nonlinear relationship。For example。

 this minus1 has pretty low probability and so on。So if you sum these numbers。

That is the thing that you're dividing by。And in some sense。

 it's like whatever you need to do to make this sum to one。In some sense。

 you can think about the softm as sort of like the bare minimum that you need to do。

 Like if you're lazy， is's like， okay， I need a distribution， how do I get a distribution？ Well。

 you look at this logic and say， oh man， probabilities cant be negative。

 What's the easiest way to make something not negative。 You exponentiate。 And it's like， oh。

 this doesn't sum to one。 So how do I make it sum to one。 You divide。

 So it's like the lazy way to make a distribution， but it also turns out to be like kind of mathematically nice in other ways。

Okay， so one property just so you have some intuition is that shifting the logics doesn't change the relative probabilityba。

 So if I have this these logics， I get these probabilities。

 and if I just add two to all these logics。Then miraculously， I get the same set of probabilities。

Okay， and。I'll leave it to you to figure out why that is。

 It has something to do with when you're dividing out。

 sort of you multiply and then you're dividing by the same number。Okay。

 this actually is a useful trick later， I don't know if you'll need in this class。

 but to avoid numerical underflow， whenever you exponential something。

 you should be really scared because a computer doesn't actually represent real numbers。

 it has finite range， so if you're exponentialiate something。Big。

 it could just kind of blow up and so the idea is that you can shift the logicts all up and down to make them kind of a nice range and then you can compute the softmax。

 and that's mathematically identical。So okay， so that's just a fun fact。Alright。

 so now we have this function， Somax that takes us a vector of logicits， one for every class。

 And I now I have a distribution。Over the classess。So this is great。Okay。

 so now I need to turn this distribution into a loss， so to do that。

 I'm going to take another detour and talk about cross entropy。So in general。

 cross entropy is this idea from information theory。

 it measures the difference between a target distribution and a predicted distribution in general。

 so suppose the target distribution over  three things is 0。5。2。3 and I predict 0。1。5。

4 so the question is do I have a number that tells me how far predicted is from target。And。Basically。

 the intuition is if I。The target says there's high probabilityant outcome。

 and the predicted puts low probability on it。 I want to penalize that。Okay。

 so what I'm going to do is。Take the target， which is every element in the target。

I'm going to multiply by minus log of the predicted probability。 so I'm going to take 0。

5 times minus log of this plus 0。2 times minus log of this and so on。And if I sum all these up。

 then that's the cross entropy。So some of this should。

Kind of seem a little bit familiar like this minus log you've seen before when we were looking at the logistic loss and how we took the probability and made it into a loss。

 Now this is just generalized so this should in fact if you take k equals2 you should get this multiclass reduce。

 recover the binary class classification setting as a special case。Okay， so some other properties。

 the cross entropy is minimized when target equals predicted。

And that value is the entropy of the target。Or predicted equivalently。Okay， so in general。

 if you're designing a loss function， the first thing you check is that。

If the thing you want is true， then your loss should be as low as possible。

 Otherwise you've sort ofve done something wrong。Okay。

 so our goal is to make target distribution equal call to predicted。

Now I'm not going to there's much more you can say about cross entropy。

 you can go look at some information theory notes， but for example， KL divergence。

 divergence is related to the entropy and cross entropy if you subtract off the entropy here。

 then you get the KL。But that's not necessary for understanding the rest of his lecture。Okay。

 so I've done the cross entropy in general because I just wanted to define what cross entropy。

 but in practice， this is going to be a very special case where the target usually is a single label。

And it's representing as a oneh vector。 So， for example， if the target is actually one。

 then I'm going to represent that as a distribution where all the probability mass is on the index1。

Okay。And then the predicted is whatever distribution I have predicted。And。

If I do go through the cross entropy calculation， then I see that and I sum。

 then I get the cross entropy result， and you can see that in the special case。

 all this is is that it's the negative log probability of the target class。

So actually it's kind of the same thing as what we had in the binary case。

 but people seem to like talking about the cross entropyed loss。

 so I've done it this in a slightly more general terms。

This also allows you to do things like if your ground truth were not just a single label。

 but an natural distribution， then there's a natural way to incorporate that as well。O。

But the end of the day， it's still you're trying to do maximum likelihood。

 If you have a probabilistic classifier。Then you want to maximize the probability of the target class or equivalently minimize the minus log of that probability。

Yeah， so the question is， why are some of these terms 0。

 And it's because the terms are target element wise multiplication of target and this thing。

 So if the target is 0， then the terms are also 0。O。

So now we can compute those cross entropy loss for a given example。嗯。And。So I compute the logics。

 I take the softmax to get a to get a distribution。

 and then I'm going to take the cross entropy as the minus log probability of the target。

 And you know， that's it。 And given this， this loss。

 we can perform gradient descent to optimize the hyperparmeter。 sorry optimize the parameters。

 I'm not gonna bother you with that this time， but you hopefully can do that。

So just to summarize this part， softftmax is the main function that turns the logicits into probabilities。

 cross MP measures the target discrepancy between the target distribution and predicted distribution and the cross Mpy loss。

 generalizes the logistic loss and is the predicted probability of the target class。Okay。

 so now you know how to do multi class classification。 There's one final thing I want to end with。

 which is representing text。 So remember the input。Of a classification problem might be strings。

 but machine learning， everything that we looked at relies on tensors。 So what do。

 this is not a tensor。 So what do we do with it， And typically。

 there's some processing that has had to happen to turn strings into tensors。

And I'm going to talk about this in two steps， one is tokenization。

 I'm going to first convert the string into a sequence of integers。

 and then I'm going to represent each integer as a one hot vector。

 and that's going to give me a tensor。So tokenization。So the idea here is that this is a string。

 I want to first split it into。嗯。A spaces and convert them into integers so I'm going to have this vocabulary class that basically maps between integers and strings so first I'm going to split into words the cat in the hat and then for every one of these words I'm going to call get vocab do at index which what does it do it basically looks up do I have I seen the stream before and if I haven't then I'm going to assign it to index and record it。

And if I have， then I'm going to use the same index。 so at the end of the day。

 I'm going to map these words into indices where you see that the occurs both times and they get the same index。

 and this is the mapping between the strings and the indices。Okay。

 so this is typically what's done to essentially take strings and map them into。To integers。

There more recently， with language models， people do fancier things than just splitting on spaces。

 which is problematic for many reasons。 For example， some you have periods。 if I do this naive thing。

 the periods would get attached to words， which is no good。

 And then you have to like okay find out split out punctuation。 But then like 3。

4 get split into three things and then some hyphenated words are really long。

 And if you're in German， then you get like really long tokens， it's a kind of a big mess。

 So what happens is that there's more automatic ways to determine how to split strings into tokens。

 something called BP or by pair encoding， this is what pioneered by GP using NLP。

 but then in language models is pioneered by G2。And there's libraries for this where you define a tokenizer and then you just encode a string into a sequence of integers。

 and there's a few encodings you can use， but that will be outside the scope of this class。Okay。

 so at the end of the day when you have tokenized， you get a set of indices and now I'm going to represent each index as a 1ha vector。

 so for example， let's take a look at this index， index 3。

 I'm going to represent this as a1ha vector where I have a one exactly in position 3。

And I can represent the entire string as of a matrix where every row corresponds to a position in the token sequence。

 and that row correspond is the 1 half vector， so have 0，1，2，0，3。Okay， so now I have a tensor。

 and now I know what to do with them。So in practice。

 we can store the indices and not the1h vectors because this is going to be sequence length times vocab size if you do it really naively。

And you can directly operate on the indice。 so suppose we have this vector and we said。

 we want to multiply this matrix by this vector。So you can do this simply in P torch by writing or I guess this is even nupy matrix at W。

And this basically gives you this vector。But you can also just use these indices directly into W。

 and that gives you the same thing。Okay。Okay， so finally。

 what I want to talk about is bag of words representation。Generally， the tokenization。

 I've going to give you basically a vector for every position。

But one thing I can do is I can average all of these row vectors together。

And get something that's like kind of an average vector。

And that's called the bag of wordss representation。 And then using this bag of wordss representation。

 I can take dot products and do whatever I want with it。 And also equivalent， I could have just。

Operated on the indices directly as well。Okay so in your assignment you're going to actually look at the bag of words representation the nice thing is that it's very simple and it doesn't depend on the length of the text so no matter how long your document you get yourself into a fixed dimensional vector which is convenient because the number of parameters you have is generally fixed the con is that it doesn't pay attention to word order。

 so dog bites man is the same representation as man bites dog which are clearly very different sentences。

But when we talk about transformers， we will talk about how we can get around that limitation。Okay。

 so to sum up。We convert strings into tensors using tokenization and one hot encoding。

 and the one hot encoding it's convenient to think about them mathematically as just vectors。

 but in code sometimes it can be useful to work with the indexes directly。So in this lecture。

 we've talked about linear classification where we take。You map to a fixed set of K choices。

 we looked at zero on loss， which is what we ideally want to measure。

 but this you can't optimize that so we relaxed the space into probabilistic classifiers and we defined the logistic loss which we could optimize。

 we saw a multi-class classification as an extension and then we saw how we can represent text as tensors。



![](img/f92022e820477c26e0a94cb171efe655_3.png)