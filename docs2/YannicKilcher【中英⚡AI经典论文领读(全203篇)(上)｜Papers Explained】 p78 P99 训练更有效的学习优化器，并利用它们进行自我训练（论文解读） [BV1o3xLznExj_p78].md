# YannicKilcher【中英⚡AI经典论文领读(全203篇)(上)｜Papers Explained】 p78 P99 训练更有效的学习优化器，并利用它们进行自我训练（论文解读） [BV1o3xLznExj_p78]

Hi there Today we'll look at tasks， stability， architecture and compute。

 training more effective learned optimizers and using them to train themselves by Luke Mes。

 Ne Varaanaan see Daniel Friedman bandpo and Yasha So Dixstein So on a high level this paper deals with sort of a meta problem it deals with learning optimizers that learn machine learning models learned optimizes is kind of a new field of research and the goal is to obtain an optimization function that can be used to train all kinds of machine learning models and this paper builds on a line of research and kind of extends that research doesn't it's not the first one to do this but it is so far the largest and most compute intensive and most task encompassing notion of learned optimizes and the optimizer they end up with。

Has some nice properties as they're going to show and also it can be used to train itself so it can iteratively be used to train itself ending up with a even better learned optimizer So we're gonna go through the paper and we're gonna to find out how much of these claims are kind of wishful thinking and how much are actually true。

 I have mixed feelings about this paper， though in all of this。

 remember my opinion is my opinion and they are very open about their results。

 which is something I really， really appreciate， I feel that if more papers were as open as these people are about what worked and also what didn't work。

 we would be in a better place as a research community。 That being said， as I said。

 I do have some mixed feelings about these statements being made here and about how the results are interpreted。

So stick around if you're interested into that， also I find the broader impact statement to be a bit funny。

 but we'll come to that at the very end。If you like content like this， as always。

 don't hesitate to share it out。 I've been on a bit of a break。

 it feels good to be back making videos after after paper deadlines。



![](img/dda6ca99a7ef39d8f3ee14c4632a6149_1.png)

![](img/dda6ca99a7ef39d8f3ee14c4632a6149_2.png)

Let's dive in。They say much as replacing hand design features with learned functions has revolutionized how we solve perceptual tasks。

 we believe learned algorithms will transform how we trained how we train models so lots of packing in this sentence for those for you young kids that have been growing up with deep learning there was a time before deep learning and basically what we would do is we would use hand design features and this works really well if you have like a database of customer data it worked moderately well if you have like a picture so if you have a picture whatever of your cat what people used to do is they used to run these kind of very handcrafted detectors。

 feature extractors over this so these might be like fixed filters like three by three soble filters。

 gradient filters and so on run them over the image， try to detect。



![](img/dda6ca99a7ef39d8f3ee14c4632a6149_4.png)

Corners try to detect very small things。 and then once they had a couple of features like this。

 they would feed this into a classic kind of classification algorithm like a logistic regression and so on。

 There were sophisticated approaches， but most required the hand engineering of features。 Of course。

 deep learning transformed all of this。 deep learning basically。

 if you want to take a cynical look at deep learning。

 it's simply replacing the part that creates the features。

 The classifier is still like a logistic regression。



![](img/dda6ca99a7ef39d8f3ee14c4632a6149_6.png)

![](img/dda6ca99a7ef39d8f3ee14c4632a6149_7.png)

However， deep learning knows how itself can extract good features， in fact。

 better features than humans ever could， for perceptual tasks。

 so four images for sound in the latest iterations also for language。



![](img/dda6ca99a7ef39d8f3ee14c4632a6149_9.png)

These people say that this can also this kind of thinking can also be applied to this optimization algorithms。

 so in optimization， what you want to do is you want to train your deep network right whatever goes from your image from this thing right here to your final output。



![](img/dda6ca99a7ef39d8f3ee14c4632a6149_11.png)

You want to train this and we train this using gradient descent。

 So what this has is usually there's Za。Many， many layers in your deep neural network and each one has parameters。

 well let's call them theta， theta 1， theta 2， and so on， these are all vectors or matrices。

 your convolutional filters， your batchche norm parameters， and so on。



![](img/dda6ca99a7ef39d8f3ee14c4632a6149_13.png)

![](img/dda6ca99a7ef39d8f3ee14c4632a6149_14.png)

We can collect all of these into a big parameter vector， let's call that theta。

 and the task is now to find the best theta， I think you're introduced to that。



![](img/dda6ca99a7ef39d8f3ee14c4632a6149_16.png)

![](img/dda6ca99a7ef39d8f3ee14c4632a6149_17.png)

![](img/dda6ca99a7ef39d8f3ee14c4632a6149_18.png)

In optimization， what you want to do is you。Have a theta， you feed an X。

 you feed an example through it， you get some sort of output， let's call that F。

That gives you some sort of loss。 You back propagate that loss。

 And what you end up with is a gradient of theta。 If we were just doing gradient descent。

 we would update theta right here。 We would update theta to be theta minus the gradient of theta。

 given some step size right here。

![](img/dda6ca99a7ef39d8f3ee14c4632a6149_20.png)

This is classic gradient descent and。Most algorithms are something like this in for example。

 gradient descent with momentum considers has like some additional term right here。

 where they consider the last steps at a grad for example。

 considers a factor down here where they divide by some kind of the square norm of past gradient So the sorry the the。



![](img/dda6ca99a7ef39d8f3ee14c4632a6149_22.png)

this。Do you add up the past gradient square norms like this， or you average over them？

There are many variants you can do this averaging right here also with momentum in kind of a decaying way。

 there are all sorts of algorithms to optimize these functions and the sense behind this is that ultimately deep learning is a nonconvex problem so instead of your classic classifiers。

 they look something like this as a loss function in your parameters or more。



![](img/dda6ca99a7ef39d8f3ee14c4632a6149_24.png)

![](img/dda6ca99a7ef39d8f3ee14c4632a6149_25.png)

![](img/dda6ca99a7ef39d8f3ee14c4632a6149_26.png)

![](img/dda6ca99a7ef39d8f3ee14c4632a6149_27.png)

Maybe more to say something like this。 if we look at it in 2D and you can just do gradient descent basically go to the optimum。

 However， in deep learning， it's a bit of a different situation。

 So you might have many different optima， many local optima。

 And we know by now that we can go to either one of them and that should be fine。

 So let's some level sets right here。 maybe here， here。Okay， but so。

You can see right here you have multiple optima where these dots are。

 but in between it's kind of shaky。 So you might have like a major flat area right here。

 but then as you get close to this optimum， maybe the steepness increases。

 So if you look at a cross section there might be like some sort of a flat area and then it increases again。

 and you want an optimization algorithm to kind of automatically adjust to the steepness and to changes in steepness and so on。

 And that's what these modifications to gradient descent are supposed to do。 So add a grad。

 for example， adjusts automatically to a landscape like this。 So even if it's convex。

 you can see that the scale of this parameter is much flatter then of this parameter at a grad would automatically kind of stretch one out and make the other smaller such that it transforms it to a nice kind of。



![](img/dda6ca99a7ef39d8f3ee14c4632a6149_29.png)

![](img/dda6ca99a7ef39d8f3ee14c4632a6149_30.png)

![](img/dda6ca99a7ef39d8f3ee14c4632a6149_31.png)

![](img/dda6ca99a7ef39d8f3ee14c4632a6149_32.png)

All dimensions are equal problem because you only have one learning rate per dimension。



![](img/dda6ca99a7ef39d8f3ee14c4632a6149_34.png)

If you go further and go into the regimes of atom or RMS Pro。

 these now can also kind of change over time。 at agrad also to a degree。

 but much more so these other algorithms can adapt to like changes in steepness and once it goes flat again。

 they can kind of recognize oh now it's flat again I might do some bigger steps once it goes steep again。

 they're like okay I should probably be kind of concerned right here。

 there's also this notion of momentum that's really useful that kind of counters stochasticity of stochastic gradient descent。

 it' it's a big field， but what they all have in common。

 it's humans sitting down coming up with this particular like a particular formula because they feel if I you know do this thing then it might it might do this it might stretch out these dimensions that might be beneficial These are humans sitting down now。



![](img/dda6ca99a7ef39d8f3ee14c4632a6149_36.png)

![](img/dda6ca99a7ef39d8f3ee14c4632a6149_37.png)

![](img/dda6ca99a7ef39d8f3ee14c4632a6149_38.png)

![](img/dda6ca99a7ef39d8f3ee14c4632a6149_39.png)

![](img/dda6ca99a7ef39d8f3ee14c4632a6149_40.png)

![](img/dda6ca99a7ef39d8f3ee14c4632a6149_41.png)

![](img/dda6ca99a7ef39d8f3ee14c4632a6149_42.png)

![](img/dda6ca99a7ef39d8f3ee14c4632a6149_43.png)

The analogy here that these people make is we used to do this for classifiers。

 we used to hand design features that we felt make sense like the image gradient and so on or the FFT for。

 let's say for。Sound and and that that worked so far。

 but it worked better when we let deep learning do its thing。 And the goal， of course。

 here is also that we let machine learning。

![](img/dda6ca99a7ef39d8f3ee14c4632a6149_45.png)

![](img/dda6ca99a7ef39d8f3ee14c4632a6149_46.png)

![](img/dda6ca99a7ef39d8f3ee14c4632a6149_47.png)

Come up with the optimization procedure。 So what exactly goes。 So if we try to update theta。

We might update it not as a fixed formula， but we might take the old theta we might take the gradient。



![](img/dda6ca99a7ef39d8f3ee14c4632a6149_49.png)