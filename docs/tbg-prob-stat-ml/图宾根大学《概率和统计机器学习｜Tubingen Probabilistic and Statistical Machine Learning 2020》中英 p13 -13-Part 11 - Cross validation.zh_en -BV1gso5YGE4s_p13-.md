# 图宾根大学《概率和统计机器学习｜Tubingen Probabilistic and Statistical Machine Learning 2020》中英 p13 -13-Part 11 - Cross validation.zh_en -BV1gso5YGE4s_p13-

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_0.png)

Now， we would like to talk about cross validation data。

Cross validation is a systematic procedure by which you can find out what are the best parameter choices for your particular algorithm on this particular problem that you' are trying to solve。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_2.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_3.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_4.png)

Remember all the machine learning algorithms we've seen so far。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_6.png)

Nearly all of these algorithms have a parameter that needs to be set。 It starts with the can nearest。

 If you look at the can nearest neighbor classifier。

 it has this parameter K that says at how many neighbors we need to look at and depend on how we fix this parameter K。

 we might have overfitting underfitting or be just right。😊。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_8.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_9.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_10.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_11.png)

And the question is， how could we find out what is the best parameter okay to choose for our particular application。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_13.png)

The method of choice is cross validation， and I want to talk about how cross validation works in practice。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_15.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_16.png)

Heres again a slide that essentially makes the point I've just made。

 essentially in all algorithms we have to set parameter and make design decisions。

 this could be and many of these algorithms we haven't seen so far。

 but maybe if you recap the slides at the end of this lecture you might know all of them。😊。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_18.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_19.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_20.png)

We have the regular parameter in regression algorithms like root regression or laso。

 the parameter C in the support vector machine， the kernel width of the Gaussian kernel。

 the number of principal components if we run a PCA，😊。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_22.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_23.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_24.png)

But there might also be other choices。 for example。

 you might want to figure out whether it makes sense to first cluster your data or not cluster it and then what is the number of clusters or which clustering algorithm do you want to use。

 Should you rather rely on Kmin as your clustering algorithm in a preprocessing step or would you rather use spectral clustering and which kind of which of these algorithms is going to give you a better result in the end。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_26.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_27.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_28.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_29.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_30.png)

So there are all these design choices， and ideally。

 you should make an informed decision about all of them。

 and the method you can use there is called cross value。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_32.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_33.png)

This is how cross validation works on one slide， so the input to cross validation is your training points。

😊。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_35.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_36.png)

And a set of different parameter combinations。 For example。

 all the parameters K that you would like to test。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_38.png)

Now， what you're going to do is you partition your training set into K parts that are equally large。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_40.png)

You do this randomly once， and these parts are often called the folds of your dataset。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_42.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_43.png)

。And now， for all choices of parameters that you want to try out for So for example。

 for all values of K for your kous na algorithm， you now do the following thing。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_45.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_46.png)

Iteratively， you look at each of these parts of your data set。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_48.png)

You built a training set out of all the parts， except one。😮。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_50.png)

And you build a validation set with the remaining part。

 So you take like if you have five is a typical size， if you do fivefold cross validation。

 you partition your training set into five pieces， you train on four pieces with all your particular parameters that you want to try out。

 you validate the result on the remaining piece and you record what is the validation error The test and the validation error is essentially the test error on this little piece that you have left out just that at this partition at this point we don't call it the test error but the validation error。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_52.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_53.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_54.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_55.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_56.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_57.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_58.png)

And then you cycle through all the choices of which folds you use for training and which you use for testing。

 so if we have five folds， then we can always use four of them for training and one for testing so we have five different possibilities and we try all of them。

😊。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_60.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_61.png)

For all of them， we train using the parameter that we were interested in compute validation error on the remaining fold。

 and then we average over all these procedures。😊。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_63.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_64.png)

And this is what is then called the result is then called the validation error。😊。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_66.png)

And here we have it as formulas， maybe to be a bit more precise。

 So we built the training set out of the fold。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_68.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_69.png)

12 k minus1 k plus 1 until upper case is k。 So the fold lower case K we have left out。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_71.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_72.png)

So we train on all those folds with all our parameters and then for each of these four for each of these situations we get a validation error which I call error S of S and K。

 So S is the current parameter set that we are looking at and K is the current fold that we use as our test fold or validation form。

😊。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_74.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_75.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_76.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_77.png)

Then what we do is we compute the average error over all these folds。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_79.png)

So the average is taken over the folds over the essentially devaluation sets。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_81.png)

We do this for all parameters， S。And now we need to select this parameter S for which this validation error is as small as possible。

 So we build the arc min over all these errors。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_83.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_84.png)

And a star is then the parameter con the parameter configuration that we want to use in the end。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_86.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_87.png)

If you've understood the the principle， it's really very easy。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_89.png)

Here's another way to explain it。So here we have so the big blue set here is the training data。

 all of our training data we have say we want to solve image classification。

 it's all the images that we can use for training in our database。😊。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_91.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_92.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_93.png)

We split this up into several folds。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_95.png)

You always train and say you do five fold cross validation。 These are four of our folds。

 and this is the validation fold， the fifth one。😊。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_97.png)

We train on this part， first part of the data set， which is now called the training the sort of the internal training set。

 The other one is the validation set， and we get the validation error。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_99.png)

And we do this with all the different choices of faults。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_101.png)

And in this way， we get the cross validation。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_103.png)

So once you now in this way selected the parameter， the best parameter of configuration is star。

 what you do in the end is you once train on your whole training set。😊。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_105.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_106.png)

Because you want to you now want to find the best classifier say to all the training data so you don't want to leave out some part of your data。

 you now want to use all your training data to find the best classifier for this fixed parameter combination S。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_108.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_109.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_110.png)

。And now you want to compute the test error。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_112.png)

And for the test error， you do this on a completely new dataset。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_114.png)

So it doesn't have anything to do with our training set。 We do it once on a test set。

 And that this is then an estimate for the two test error that the procedure has。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_116.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_117.png)

It is really， really， really important that this test set is independent of your training set and you haven't touched it at all while doing the training。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_119.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_120.png)

。And here are two important points。 And I know that in theory， it sounds nice in practice。

 Sometimes it's not as easy。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_122.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_123.png)

But never， never， never。 you're allowed to use your test set in the validation phase。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_125.png)

This means。You have your training set， you do cross validation， you select your parameter S star。

 you finally settle for a set of parameters， you run it on your test set and then you see oh them it doesn't really get the precision as I said would like it on my test set。

😊。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_127.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_128.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_129.png)

So you go back and train again， try to figure out what is a different way of of of running the algorithm。

 Maybe you choose a different parameter said whatever。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_131.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_132.png)

And then you want to go and test again。If you now use the same test set as we have done before。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_134.png)

This test that is already spoiled。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_136.png)

You would need to use a completely new test set that is completely independent of everything else that you have seen before。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_138.png)

And only on this very independent test set， the error that you record on this test set is is an is a true estimate for。

 for the training error for the test error， for the true underlying error。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_140.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_141.png)

As soon as you touch that， it means， for example， by testing and then seeing， oh。

 it's not good enough and going back to training， what can happen is you can overfit again because I mean。

 the whole point of having the difference between training error and test error is to avoid overfitting。

😊。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_143.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_144.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_145.png)

Now， what could happen is your test set maybe has a particular structure and maybe there are a particular set of I don't know。

 objects in this test set。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_147.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_148.png)

And maybe this is why you're classifying you selected in the first place doesn't work。

 So now you start improving。 you always look at your test and say I'm not satisfied。

 I go back to training and I do cross validation in this very neat way and on my training data but then I go back to the test data I'm still not satisfied and you do it as long until you're satisfied Now if your test set has a particular structure then of course in this round of iteratively going back between training and test set you start to adapt to this particular structure in your test set and of course then this error you record on the test set is not an unbiased error of your true test error。

😊。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_150.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_151.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_152.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_153.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_154.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_155.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_156.png)

So this is really important。 If you want to have an independent estimate。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_158.png)

Of your true test error， you need to do it on a test set that you haven't touched at any time during training。

 not a single time， not any of these points should have been considered during this whole training iteration loop of going between training and testing before。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_160.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_161.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_162.png)

Otherwise， you cannot trust your test error。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_164.png)

Now I know that in practice this is sometimes difficult because if you're in a particular situation where you don't have an infinite amount of data。

 you can't simply produce new test sets by by drawing new points from your underlying distribution so you just have a finite amount of data and you have to work with it。

😊。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_166.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_167.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_168.png)

And there are essentially two conclusions from this。

 if you have so little data that you really cannot avoid this。

 at least you must be very clear about the fact that you cannot trust your test error。 Also。

 if you would write a publication in your paper about about this about this particular。

 like if you would write a paper， a scientific paper about this application。😊。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_170.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_171.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_172.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_173.png)

You would need to be very open and say， I couldn't test on an independent test set。

 I have used the set in training。 So it is an indication。 Maybe it goes in the correct direction。

 but we don't really know。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_175.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_176.png)

And this is essentially the only way in which it could go。

 The other way would be to to simply test once and be happy with whatever reside you are happy or unhappy。

 but don't touch it anymore， because maybe you think you cannot improve it anymore。 You test once。

 and this is simply the outcome。 And then you use a classifier that you have found so far。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_178.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_179.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_180.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_181.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_182.png)

。There are a number of practical questions that are also related to cross validation。

 So if you do K for cross validation， what is the parameter K。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_184.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_185.png)

I think the bottom line is that typically it's not so important。

 So what happens in practice often is people use k equals 5 or k equals 10 or so。

 it doesn't really make such a big difference in the end。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_187.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_188.png)

What is maybe more crucial is what is sort of the number of parameters that you need to test。

 And this might also have an influence on the number of folds that youre afford that you can。

 in fact， afford to work on。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_190.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_191.png)

So assume we just have one parameter that we want to tune。

 say we have a regularization problem and this is we just have the regularization constant that we want to figure out like in rich regression。

😊。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_193.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_194.png)

And then what we can do is we choose these this regulargization constant typically on a log scale。

 say from 10 to the minus-3 to 10 to the3。 so we have like  seven choices here and we try all of them in five foot cross validation。

😊。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_196.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_197.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_198.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_199.png)

That's all fine。 That's feasible。Now， in many algorithms， you not not only have one parameter。

 but you have a number of parameters。 Just consider a simple support vector machine。

 And we are going to see that later in the in the lecture， it has the straight of parameter C。

 which is essentially something like lambda， but it also has the kernel with sigma。

 So we have two parameters。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_201.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_202.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_203.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_204.png)

Now， if you assume you want to choose C。嗯。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_206.png)

Again， on a log scale and you want to choose s more also on a log scale now we have different combinations of these parameters。

 and it might be that one particular combination works whereas another combination does not work。

 so essentially you need to look at the product space。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_208.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_209.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_210.png)

Of like all combinations of the value of C and sigma。

And you can already guess where this is heading to here we have like if each of these set like this one has now  seven parameters or eight and this one has six parameters。

 so you already have six times eight many combinations。 youre already already close to 50。😊。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_212.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_213.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_214.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_215.png)

If you have three parameters， you have even， I mean。

 it explodes grows exponentially with the number of parameters， even。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_217.png)

If the number of choices that you look at for each particular parameter is not large， I mean， here。

 this is sort of like6 choices is not a large set。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_219.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_220.png)

It looks even maybe you should use more， but you cannot afford it essentially。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_222.png)

Because think about what do you need to do now， you have now these close to 50 choices of different parameters。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_224.png)

And you need to run5 fold cross validation。 That means for each of these parameters。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_226.png)

You need to train your algorithm five times on the training fold and test on the test fold。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_228.png)

So you have already five times 50 many instances of your training of of your machine learning algorithm that you need to solve。

 so you have to solve 250 optimization problems and already that I mean like if one of your runs takes one minute fine then you can still do it。

 you have 250 minutes， it takes the afternoon and you're done maybe you're still not so happy but it's feasible if one of your training runs takes one hour you already need 250 hours。

😊。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_230.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_231.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_232.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_233.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_234.png)

That's already less comfortable。 And if it takes like a day， then you need to wait 250 days。

 which is probably too long because it's nearly it's more than half a year。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_236.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_237.png)

And this is only for like， very simplistic setups。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_239.png)

嗯。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_241.png)

So there is， of course， there's something more clever that you can do even in particular。

 if you have more parameters， there is now more systematic ways in which you can walk through your parameter space and essentially do something like a gradient decent in the space of parameters。

 and this has been implemented in many of the toolbox that you can use in machine learning。😊。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_243.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_244.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_245.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_246.png)

I don't want to discuss really how this， how this works。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_248.png)

But what is important is that you at least know or you look up what is the procedure that is being used in your particular package。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_250.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_251.png)

You should at least try to figure out whether it uses some kind of cross validation or clever procedure to choose these parameters or whether it simply uses the default parameters so they exist many packages which just say if you don't specify the cross validation procedure。

 I always use Lambda is 1 C is 1， Sigma is 1。😊。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_253.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_254.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_255.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_256.png)

And then， of course， it's not so likely that your algorithm is going to succeed。

Theres one more comment on the previous slide， overfitting can， of course。

 happen for cross validationation。

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_258.png)

And maybe in the exercises， we are going to look at an example where this is really the case。

So what are the advantages and disadvantages of cross validation。There are lots of disadvantages。

 It is computationally expensive， as I just outlined in particular。

 if there are more than one parameters that you wanted to。

There's one little thing that you might want to take care of that the training size of the problems。

Used in the individual cross validation is a bit smaller than the one that you do in the very final training one。

 So in your cross validation procedure， say you use fivefold cross validation。

You train on a training set that is4 over five times the size of your whole training set。

So you have this factor which is not large， which goes from 4 over 5 to one。

If your training set is huge， it might not make a big difference， but if in particular。

 if you have a small training set， it might be the case that the parameter you choose on the smaller data set is not the best one that you could have in the larger dataset set。

 for example， because of the because for example， there are two norms scales with the number of dimensions you have or something like that。

From a theoretical side， what is also a bit annoying。 I mean。

 there exists a couple of theoretical results and cross validation。 In principle。

 it is not so easy to prove theorems about like the consistency or the fact that cross validation always finds the best parameters or is a consistent estimate of your test error。

Because you have all these dependencies， like in statistically proofs。

 whenever you have things that are independent， you're good because then you can take averages and these averages if you do it properly。

 hopefully convert to the true value that you want to estimate。😊，Now。

 if these things over which you want to take the averages are dependent on each other。

 Ta the average doesn't really save you。And so this is the case for cross validation。

 so its not they exist theoretically results， but maybe the state is not as satisfactory as we might want it to have。

I gave a couple of references already in the beginning of the of the chapter。

 I have a paper I point to a paper by Svan Alo， who was worked on cross validation a lot and has a nice paper in Jlar。

 I think he is also a somewhat but older reference。In Statistic， as her from 2006。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_260.png)

Now， these were all disadvantages。 What is the advantage well。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_262.png)

The advantage is that there doesn't exist any other procedure that would help you to find in a systematic way what are the best parameters that you have to use for your learning algorithm。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_264.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_265.png)

And you have to have a procedure that tells you which are your best parameters。

 because default choices don't help。 There is not a single best choice of the parameter K for canous neighbor。

 It really depends on your problem， on your distance function on the number of data points you have and so。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_267.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_268.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_269.png)

So this is simply you have to use cross validation because there's nothing else。

 And you always have to do that。 And you really， really。

 really need to keep that in mind when you have parameters， you use cross validation。

 When you use a software， you check whether the software uses cross validation。

 You always have to do that。 And otherwise， you cannot trust your results。



![](img/f08ad89c201cedc5f10ed9e33b45dcd5_271.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_272.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_273.png)

![](img/f08ad89c201cedc5f10ed9e33b45dcd5_274.png)