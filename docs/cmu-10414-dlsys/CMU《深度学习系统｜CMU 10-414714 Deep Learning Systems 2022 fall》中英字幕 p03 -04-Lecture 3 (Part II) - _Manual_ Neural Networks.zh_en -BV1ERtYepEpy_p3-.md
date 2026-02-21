# CMU《深度学习系统｜CMU 10-414714 Deep Learning Systems 2022 fall》中英字幕 p03 -04-Lecture 3 (Part II) - _Manual_ Neural Networks.zh_en -BV1ERtYepEpy_p3-

All right， so let's jump in now and start talking about back propagation， i。e。

 how we compute gradients in neural networks。

![](img/d274b065e30e493185aa38c4a0cbb160_1.png)

![](img/d274b065e30e493185aa38c4a0cbb160_2.png)

All right， so set the stage here。

![](img/d274b065e30e493185aa38c4a0cbb160_4.png)

As we talked about last time。The term neural network really just means specifying one of the three ingredients of a machine learning algorithm。

 so remember there were three ingredients that was the hypothesis class， the loss function。

 and the optimization procedure。

![](img/d274b065e30e493185aa38c4a0cbb160_6.png)

And it turns out that two of these are exactly the same as before so as before in the case of soft mass regression。

 so our loss function is still going to be cross entropy loss。



![](img/d274b065e30e493185aa38c4a0cbb160_8.png)

And our optimization procedure is still going to be stochastic reading descent。

 both of these exactly like last time。

![](img/d274b065e30e493185aa38c4a0cbb160_10.png)

In other words， our actual optimization problem is exactly the same as before。

 it's just given by minimizing over our parameters。



![](img/d274b065e30e493185aa38c4a0cbb160_12.png)

The average of our losses of our cross entropy loss。Between the hypothesis and our true output。



![](img/d274b065e30e493185aa38c4a0cbb160_14.png)

The only difference is that our hypothesis class now instead of just being a linear function。



![](img/d274b065e30e493185aa38c4a0cbb160_16.png)

Is now a neural network， either the simple two layer neural network or。



![](img/d274b065e30e493185aa38c4a0cbb160_18.png)

A multi multi layerer L layer， multi network。 and of course， very soon we'll talk about even more。

Complex and structured hypotheses。So what this means is that our entire the only difference practically speaking in an implementation of a neural network versus softmax regression is that we just need a way of computing these gradients。

 the gradient with the theta， and when I say gradients with the theta。

 what I really mean well this come up the next slide。

 what I really mean of course is the gradient respect both of the parameters， so W1 and W2。



![](img/d274b065e30e493185aa38c4a0cbb160_20.png)

![](img/d274b065e30e493185aa38c4a0cbb160_21.png)

![](img/d274b065e30e493185aa38c4a0cbb160_22.png)

And that's the only difference。Okay， so let's， in fact， jump in and actually。

Figure out what these gradients are。And in doing so。

 we will derive the actual rule of that propagation。



![](img/d274b065e30e493185aa38c4a0cbb160_24.png)

![](img/d274b065e30e493185aa38c4a0cbb160_25.png)

Alright， so when I say the gradient with be theta， what I really mean is the gradient respect to W1。

We need that thing， we need the gradient of our loss we care about。



![](img/d274b065e30e493185aa38c4a0cbb160_27.png)

And here I'm just subsituting in our hypothesis function。 So let's talk about。

 in fact that that two layer network I had before。 our hypothesis is， in fact。

 just this sigma of x times w1 all times w2 right that is our hypothesis。

 So this thing here is just H theta of x。

![](img/d274b065e30e493185aa38c4a0cbb160_29.png)

![](img/d274b065e30e493185aa38c4a0cbb160_30.png)

![](img/d274b065e30e493185aa38c4a0cbb160_31.png)

And what we want is the gradient of this quantity with respect to W1。😊，And with for the W2。

 that's what we mean by the gradients， which for the theta。

 just with respect to both those two parameters。Al right， so now we have nothing that we can do here。

 but just actually do this。 So we have to just sit down and do it。嗯。😊。

We're going to use the exact same techniques that we use last lecture。

 so if these if you're forgetting exactly how we did this， go back and watch that last lecture。

 the trick we're going to do is we're going to take partial derivatives as if everything as if all our values here were scalar valued。

 we're going to then look at the sizes of the resulting quantities and we're going to then figure out what our actual gradient has to be in order to make these sizes work。

😊，In this case， so we're doing the cheating way of computing all these gradients。

In this case it becomes starts becoming even way more important now to actually check our gradients because now we definitely can make a lot of mistakes very easily。

 but these will in fact be all the cru gradients and this is the last time I'm going have subjected to this after this lecture you will you will be able to to。

😊，Safely ignore a lot of these things because you can do them well with automatic differentiation。

All right， so let's first take the gradient of our loss with respect to W2 and W2 here is sort of the second layer of weights in our simple two layer network。



![](img/d274b065e30e493185aa38c4a0cbb160_33.png)

![](img/d274b065e30e493185aa38c4a0cbb160_34.png)

![](img/d274b065e30e493185aa38c4a0cbb160_35.png)

All right， so what is this？Well， this is going to be the derivative of the the partial of the cross entropy loss of。

Sigma X W1。W2 and Y。With respect to the arguments to that cross entrytropy loss。

 so that would just be sigma。Partial sigma。X， W1。W2 times。Partial of the inside thing， Sigma X W1。W2。



![](img/d274b065e30e493185aa38c4a0cbb160_37.png)

Partial W2。

![](img/d274b065e30e493185aa38c4a0cbb160_39.png)

Okay。嗯。This though， despite the seeming complexity here actually and again。

 you can feel free to go back to the slides from our previous lecture too here。

 this actually is exactly the same as our gradients we're computing last time for soft mass regression。

 the only difference is instead of just having X here， we actually have sigma of x times W1。

 but nothing actually else changes because that's all just a constant for the partial derivative with respect W2。

😊。

![](img/d274b065e30e493185aa38c4a0cbb160_41.png)

So what this was going to be actually is just equal to I'll actually use the word the term S here。

 S minus IY， we used Z for like the softmax applied to the last layer of the network last time。



![](img/d274b065e30e493185aa38c4a0cbb160_43.png)

![](img/d274b065e30e493185aa38c4a0cbb160_44.png)

I we to use Z for other things now， so I'm going to use S here。 S is just equal to。



![](img/d274b065e30e493185aa38c4a0cbb160_46.png)

Me memoir read it up above did not crowd text too much。S here。Is just equal to normalizing。Normalize。

The exponential of H。Data of x。I。e。 it equals。Normalize。Exp。Of。Well， sigma X W1， W2。



![](img/d274b065e30e493185aa38c4a0cbb160_48.png)

So it's， it's just basically equal to， let's sorry， awesome some prezis there let be moving back。



![](img/d274b065e30e493185aa38c4a0cbb160_50.png)

![](img/d274b065e30e493185aa38c4a0cbb160_51.png)

It's just equal to basically the。

![](img/d274b065e30e493185aa38c4a0cbb160_53.png)

The softftmax operator applied to our final prediction of our classifier。



![](img/d274b065e30e493185aa38c4a0cbb160_55.png)

嗯。

![](img/d274b065e30e493185aa38c4a0cbb160_57.png)

And that' again， this is exactly the same as in the last lecture。

 what we saw for the gradient of the softm because this is just the gradient of the cross entropy loss right and so that term with affected its input。

 so that term is exactly the same as before。😊。

![](img/d274b065e30e493185aa38c4a0cbb160_59.png)

![](img/d274b065e30e493185aa38c4a0cbb160_60.png)

![](img/d274b065e30e493185aa38c4a0cbb160_61.png)

And then times， well， the derivative of this thing which with the W2 is just this term right here。

So will be times sigma。X， W1。Al right， now how， how big are these things Well， S here。

 that would just be the the output remember our。

![](img/d274b065e30e493185aa38c4a0cbb160_63.png)

The class1 is k dimensional， so the output here would be an M by K dimensional matrix。



![](img/d274b065e30e493185aa38c4a0cbb160_65.png)

![](img/d274b065e30e493185aa38c4a0cbb160_66.png)

And this term here， this next term。Sigma of x W1。Well， that would also be。M dimensional。

 because we're applying it to every element of our data。 But then will be M by D， right。

 because D is the dimension of our。These is the dimension of our。

Essentially the activations or the hidden units。After we apply our first layer。So then。

Our next question， of course， is how do we。

![](img/d274b065e30e493185aa38c4a0cbb160_68.png)

How do we actually compute the gradient from this， Well we know that our gradient here。

 the W2 W2 and hence also the gradient with respect to W2 of this loss is going to be a D by K dimensional matrix right that actually was if to go back a few slides that was the size you saw of our matrix。



![](img/d274b065e30e493185aa38c4a0cbb160_70.png)

![](img/d274b065e30e493185aa38c4a0cbb160_71.png)

![](img/d274b065e30e493185aa38c4a0cbb160_72.png)

![](img/d274b065e30e493185aa38c4a0cbb160_73.png)

And so to make the sizes work out here， this was again， the exact same thing we did last time。

 up what you will end up doing is you have to take this thing。😊。



![](img/d274b065e30e493185aa38c4a0cbb160_75.png)

![](img/d274b065e30e493185aa38c4a0cbb160_76.png)

And transpose it。Times this thing。So the final form of our gradient。



![](img/d274b065e30e493185aa38c4a0cbb160_78.png)

Will just be。Sigma X， W1 transpose times S minus。

![](img/d274b065e30e493185aa38c4a0cbb160_80.png)

IY and IY again， is sort of a one hot encoding of our labels across the whole data set。



![](img/d274b065e30e493185aa38c4a0cbb160_82.png)

Okay， so that that's the easy one。

![](img/d274b065e30e493185aa38c4a0cbb160_84.png)

Um， now we're going to take a deep breath here and do the next one。

So what is the derivative of our cross entropy loss with respect to W1 because we need both gradients。

 right we have to update both parameters here in order to actually perform an update via gradient desent。

All right， so I'm going to just do it here again as the slide says。

 take a deep breath and we're going to do it again。

 we won't have to do it too often and there is a bit of structure sort of method to this madness which we'll show the next slide。

 but this is how we're going to at least start doing this。😊，All right。

 so we have to just sort of dig in， we want to compute this thing and this will will apply a chain rule a few different times here。



![](img/d274b065e30e493185aa38c4a0cbb160_86.png)

All right， so I'm just going to write out what this is。

 so this is going to be partial L cross entropy of sigma in the numerator x1 or W1， W2， y。

All with respect to， hopefully I won't run out of space here。

 it's kind of hard to write this so small and stay on my screen。With respect to its argument， X。

 this is actually the same thing as before。W2 okay， so that's the same as before。



![](img/d274b065e30e493185aa38c4a0cbb160_88.png)

But now we have the partial of sigma Xw1。

![](img/d274b065e30e493185aa38c4a0cbb160_90.png)

W2 with respect to W1。 And because we have W1 here， you know， this， this argument here still。



![](img/d274b065e30e493185aa38c4a0cbb160_92.png)

Still sorry still affects W1， so we can't just be done here。

 So in fact I get to apply the chain rule some more times。



![](img/d274b065e30e493185aa38c4a0cbb160_94.png)

And so this thing is going to be times the or。

![](img/d274b065e30e493185aa38c4a0cbb160_96.png)

Divative of sigma X， W1， W2， partial Sigma X， W1， That's a term that depends on X1。

 And I'll just finish out the rest here without doing without sort of breaking down each term individually。

 you would next have partial sigma X， W1， partial。

![](img/d274b065e30e493185aa38c4a0cbb160_98.png)

![](img/d274b065e30e493185aa38c4a0cbb160_99.png)

![](img/d274b065e30e493185aa38c4a0cbb160_100.png)

X W1 times partial。

![](img/d274b065e30e493185aa38c4a0cbb160_102.png)

X， W1。Pial， there'll be one。

![](img/d274b065e30e493185aa38c4a0cbb160_104.png)

So that is actually our whole chain rule， basically factoring out everything we need to compute all the pars we want。

 finally ending up in terms that can all be computed basically term by term。Okay。

 so what are all these things？

![](img/d274b065e30e493185aa38c4a0cbb160_106.png)

They fortunately aren't that hard to do。 So this first one here， this， this one here。

 that's exactly the same as we saw before。 So that's going to be in the same way。 S minus I Y。

 I'm gonna put。

![](img/d274b065e30e493185aa38c4a0cbb160_108.png)

![](img/d274b065e30e493185aa38c4a0cbb160_109.png)

Princes around this to keep everything kind of simpler here。



![](img/d274b065e30e493185aa38c4a0cbb160_111.png)

Times， well， what's this one？Ohoops。What is this one here？



![](img/d274b065e30e493185aa38c4a0cbb160_113.png)

This is the partial derivative or just again， the derivative of something times W2 with respect to that thing。



![](img/d274b065e30e493185aa38c4a0cbb160_115.png)

![](img/d274b065e30e493185aa38c4a0cbb160_116.png)

So the derivative there is just going to be W2。

![](img/d274b065e30e493185aa38c4a0cbb160_118.png)

嗯。Then we have this one here。The partial derivative of sigma of xw1 with respect to its argument。



![](img/d274b065e30e493185aa38c4a0cbb160_120.png)

And that's actually a bit seems a bit kind of tricky and arbitrary， but remember。

 sigma is just a scalar function。And that scalar function just has a derivative and let's call that derivative。

Sigma prime right so for the value the derivative would be actually so you know the re is a function that looks like this。

 I haven't really introduced this yet， but a function that looks like this。

 it's 0 in this less plain than linear after this。 And so its derivative would just be0 here and then one over here。



![](img/d274b065e30e493185aa38c4a0cbb160_122.png)

![](img/d274b065e30e493185aa38c4a0cbb160_123.png)

Okay。

![](img/d274b065e30e493185aa38c4a0cbb160_125.png)

We'll get to more of those， you'll use that a lot more later。



![](img/d274b065e30e493185aa38c4a0cbb160_127.png)

But basically this。This derivative of sigma is the function we can compute， right。



![](img/d274b065e30e493185aa38c4a0cbb160_129.png)

Any scalar function we have we just we just know it' derivative and so it' derivative so then the partial derivative of sort of its argument with respect to its argument is just going to be the partial of or it's going to be its derivative applied to that argument right it's going to be sigma prime of xw1。



![](img/d274b065e30e493185aa38c4a0cbb160_131.png)

![](img/d274b065e30e493185aa38c4a0cbb160_132.png)

![](img/d274b065e30e493185aa38c4a0cbb160_133.png)

![](img/d274b065e30e493185aa38c4a0cbb160_134.png)

Right， so again that。This would be because sigma is scalar valued。

 this function here would also be scalar valued， just so it would be a scalar value of derivative。

 and we just apply that scalar function to this whole argument here。



![](img/d274b065e30e493185aa38c4a0cbb160_136.png)

![](img/d274b065e30e493185aa38c4a0cbb160_137.png)

![](img/d274b065e30e493185aa38c4a0cbb160_138.png)

Okay。Times finally the last one， well again。

![](img/d274b065e30e493185aa38c4a0cbb160_140.png)

Those are both matrices。 So maybe in reality， it's some nasty tensor。

 But for the sake of printing everything a scalar here， it's just be equal to。



![](img/d274b065e30e493185aa38c4a0cbb160_142.png)

![](img/d274b065e30e493185aa38c4a0cbb160_143.png)

Next。All right。

![](img/d274b065e30e493185aa38c4a0cbb160_145.png)

Now the really fun part。Let's talk about these sizes here。So this one here as before。

 was just going to be M。

![](img/d274b065e30e493185aa38c4a0cbb160_147.png)

By K， okay， that was the， that was theal dimension of that thing。



![](img/d274b065e30e493185aa38c4a0cbb160_149.png)

W2 is a D by K matrix。

![](img/d274b065e30e493185aa38c4a0cbb160_151.png)

Okay。😊。

![](img/d274b065e30e493185aa38c4a0cbb160_153.png)

This one here， well， this this matrix here is going to be M by this one's going to be M by D。

 So this whole thing is also you know scalar functions， this whole thing here would also be M by D。



![](img/d274b065e30e493185aa38c4a0cbb160_155.png)

And then this quantity here would be M by n。

![](img/d274b065e30e493185aa38c4a0cbb160_157.png)

That's the sizes of everything。

![](img/d274b065e30e493185aa38c4a0cbb160_159.png)

All right， so now what is the gradient we're after。

 what is the gradient of our loss with respect to W1？



![](img/d274b065e30e493185aa38c4a0cbb160_161.png)

Well， again， maybe the first thing I'll write here is to sort of write the size。

 this thing would be a matrix。The same size is W and if you go back up to slides。

 what you will see is that W1 is n by D。

![](img/d274b065e30e493185aa38c4a0cbb160_163.png)

![](img/d274b065e30e493185aa38c4a0cbb160_164.png)

It transforms anal space to dedisal space as part of the first layer。

So how do we get an n by D dimensional matrix from all this stuff？Well。

 the first thing we have to do is the only term that involves n in all of this is x there。

 so we're definitely going to have to take X and transpose it first。



![](img/d274b065e30e493185aa38c4a0cbb160_166.png)

![](img/d274b065e30e493185aa38c4a0cbb160_167.png)

![](img/d274b065e30e493185aa38c4a0cbb160_168.png)

All right， and then we have other things where we need， we want this to be。

 So x is now x transpose would be M by n。 its a lot here， So this x transpose would be n by M。

 So whatever is inside here， we want it to be M by D。



![](img/d274b065e30e493185aa38c4a0cbb160_170.png)

![](img/d274b065e30e493185aa38c4a0cbb160_171.png)

![](img/d274b065e30e493185aa38c4a0cbb160_172.png)

![](img/d274b065e30e493185aa38c4a0cbb160_173.png)

Okay， well， we already actually have one of these， right， so we already have this one。



![](img/d274b065e30e493185aa38c4a0cbb160_175.png)

Which is M by D。

![](img/d274b065e30e493185aa38c4a0cbb160_177.png)

So let's put that in there。Sigma prime。X W1， but we have to sort of multiply with other things， too。



![](img/d274b065e30e493185aa38c4a0cbb160_179.png)

and I guess the other thing that could be in this whole sort of sequence here that could also be M by D would be this term here。

 would be this term。

![](img/d274b065e30e493185aa38c4a0cbb160_181.png)

![](img/d274b065e30e493185aa38c4a0cbb160_182.png)

Times this term transpose would also be M5 D， so we also have。



![](img/d274b065e30e493185aa38c4a0cbb160_184.png)

It's other term， let's ignore what we're doing with them right now， but let's talk about S minus IY。

Times。W2 transpose。 That's also the right size。

![](img/d274b065e30e493185aa38c4a0cbb160_186.png)

And we have to multip those things together。 In fact。

 those those matrices So this matrix here you know， is。



![](img/d274b065e30e493185aa38c4a0cbb160_188.png)

Is M by D。

![](img/d274b065e30e493185aa38c4a0cbb160_190.png)

This one here is M by D。And so in fact， the way we combine these two in this particular case。

 let me just take。

![](img/d274b065e30e493185aa38c4a0cbb160_192.png)

![](img/d274b065e30e493185aa38c4a0cbb160_193.png)

Their're scalar product， they're scalar multiple of each other。

And and and then combine them that way， we to multiply them at the same size。

 so all we can do is multiply them scale element wise。

 and that ends up being the correct gradient of this all。😊。



![](img/d274b065e30e493185aa38c4a0cbb160_195.png)

So this node here is probably very appropriate if you're actually going through all of this。



![](img/d274b065e30e493185aa38c4a0cbb160_197.png)

So this is our final gradient， this is the gradient with respect to W1。Of everything。 And， you know。

 again， this is this seams。 which did a lot of math to get here， right。

 but you have to implement this。

![](img/d274b065e30e493185aa38c4a0cbb160_199.png)

You know， to implement gradient descent this on this network， keep it at the right。



![](img/d274b065e30e493185aa38c4a0cbb160_201.png)

Two or maybe three， if you want to compute some intermediate terms， you know。

 compute this term first， right？

![](img/d274b065e30e493185aa38c4a0cbb160_203.png)

And you basically have this line of Python。

![](img/d274b065e30e493185aa38c4a0cbb160_205.png)

And this line of Python。And you're kind of done。

![](img/d274b065e30e493185aa38c4a0cbb160_207.png)

So again， despite being pretty complex math here， you can write。



![](img/d274b065e30e493185aa38c4a0cbb160_209.png)

Sttochastic green descent。For a two layer neural network in maybe a few more maybe six or seven lines of Python code。



![](img/d274b065e30e493185aa38c4a0cbb160_211.png)

That's amazingly powerful。

![](img/d274b065e30e493185aa38c4a0cbb160_213.png)

Now， a few words of caution here， I don't want to do too much more of this derivative。

 I have a little bit more coming up， which I admit， but I don't want to do too much more。

 so in some sense， hopefully the biggest takeaway from all of this for you should be to decide that you never want to do this anymore and you just want to invest all your time learning about automatic differentiation so you don't have to do these things anymore。



![](img/d274b065e30e493185aa38c4a0cbb160_215.png)

The second thing to keep in mind is when we start getting at these things。

 you really have to check check this numerically right so again Tanjs going to talk about how you check things numerically in future lectures。

 but it would have been really I mean。😊。

![](img/d274b065e30e493185aa38c4a0cbb160_217.png)

![](img/d274b065e30e493185aa38c4a0cbb160_218.png)

Really， like how did I really know that was that was going to be a scalar multiple there？

There are many other ways you can possibly contribute possibly combine these things together。

So you have to check your answers here， if to check them numerically。

 make sure they're actually right whenever you get some that's this complicated and I wouldn't be able to get these things right unless I could actually check them。

Don't do it anymore， but if you do do it， then check your answers。Okay。

So now presumably no one else wants to do a three layer network。

I'm going to actually illustrate the general case of this for an L layer network。

 which will actually involve some simplification at some point， though。

 things that should be simpler when we do that not more complicated。



![](img/d274b065e30e493185aa38c4a0cbb160_220.png)

So。Suppose we once did the same thing now for an arbitrary kind of feed forward neural network like we talked about before at the very beginning。

 So this is essentially a a network where we have Z I plus one。



![](img/d274b065e30e493185aa38c4a0cbb160_222.png)

![](img/d274b065e30e493185aa38c4a0cbb160_223.png)

Is some nonlineararity applied to a linear function of the previous layer。

 which repeated it up to L layers， and eventually the output of the network is just going to be the L plus1 layer in this temptationation。



![](img/d274b065e30e493185aa38c4a0cbb160_225.png)

Okay， so how would we actually go about deriving this？

I don't think people really wants to go through the whole sort of explicit process I did last time so what I'm going to do instead is I'm actually going to。

😊，Be a bit more condensed with my notation。 But I'm going to basically illustrate the fact that when you do this。

What you will find is that a lot of terms in your。Gradients and your derivatives。

 however you want to compute them。They end up sort of being the same。

No matter how many layers deep you go or sort of you have a lot of similar terms when computing the gradients for a lot of different layers。

So I want to illustrate that briefly here。

![](img/d274b065e30e493185aa38c4a0cbb160_227.png)

All right， so let's think about a generic。

![](img/d274b065e30e493185aa38c4a0cbb160_229.png)

L layer network， feed forward network again， following this sort of simple iteration here。

s what we talked about on that on those slides a few a few slides back。

And suppose I wanted to compute the gradient of the loss of this network。

 which again would be the gradient the loss of the1 L plus1 layer because that's considered the output of the network。



![](img/d274b065e30e493185aa38c4a0cbb160_231.png)

With respect to。

![](img/d274b065e30e493185aa38c4a0cbb160_233.png)

WI。So this would be to update my parameters W。All we can really do here is just kind of do it。

 So I'm going to be a bit more abbreviated to meditation to'll kind of see that。

 but essentially I'm going to read this as a whole bunch of partial derivatives where I'm not going to sort of write down eat the exact form of these things。

 but but you'll see in a second this is a valid application of the chain rule。😊。



![](img/d274b065e30e493185aa38c4a0cbb160_235.png)

![](img/d274b065e30e493185aa38c4a0cbb160_236.png)

![](img/d274b065e30e493185aa38c4a0cbb160_237.png)

So this is going to be equal to the derivative of I'll just write derivative partial of L as that's this whole thing here。

 but writing it all is a bit cumbersome。So the partial L， partial Z L plus 1。

 that's the input argument to L。Times。Partial Z L plus 1。

Partial ZL because ZL plus one is a function of ZL， and if I'm going all the way back to WI。

 I need to sort of separate out all these partial derivatives。



![](img/d274b065e30e493185aa38c4a0cbb160_239.png)

![](img/d274b065e30e493185aa38c4a0cbb160_240.png)

Times the partial Z L。Partial Z。That's that since E Z partialel Z L。



![](img/d274b065e30e493185aa38c4a0cbb160_242.png)

ZL minus1， et cetera， just all the way down。

![](img/d274b065e30e493185aa38c4a0cbb160_244.png)

Z呃。

![](img/d274b065e30e493185aa38c4a0cbb160_246.png)

L。inus1， L of minus  two， et cetera。Down to。Well。Partcel C。



![](img/d274b065e30e493185aa38c4a0cbb160_248.png)

It would be i+ 2。We're trying to get down to the Ithe。So the I element here。

 so we have partial Z I plus 2， partial Z I plus 1， and finally partial Z I plus 1。Partial W I。

 because finally， this term here， which is just this term there， depends directly on WI。

 I guess I mean， I guess through an and sigma， but but。



![](img/d274b065e30e493185aa38c4a0cbb160_250.png)

![](img/d274b065e30e493185aa38c4a0cbb160_251.png)

Does does not depend on ZI。

![](img/d274b065e30e493185aa38c4a0cbb160_253.png)

Okay。Now， the interesting thing here is if you do this a lot， so imagine I do this for， you know。

 WI minus1， WI minus2， etc。What you would of course， see is that a lot of these terms here。

They end up occurring again and again。 right， This term here would occur。

In the derivative of any W I， you know， less than this I， right， like it would also occur for M1 Mt。

 like this exact same term here would。And。This is actually a really， really important notion。

 This notion that we are kind of using in or computing intermediate products or intermediate terms that we reuse。

Not just on computing one gradient， but computing kind of all the gradients we care about。



![](img/d274b065e30e493185aa38c4a0cbb160_255.png)

That's going to be really， really important。And it's so important， in fact。

 in the case of neural networks。 So we're actually be going to give this term a name。



![](img/d274b065e30e493185aa38c4a0cbb160_257.png)

So this whole term here。We're going to call this GI。😡。



![](img/d274b065e30e493185aa38c4a0cbb160_259.png)

And G is equal to。The partial derivative of our loss。

 I've been write out of our loss of Z L plus 1 and y with respect to Z。



![](img/d274b065e30e493185aa38c4a0cbb160_261.png)

Actually here I'll write G plus1 there is because this whole term is the count to Z plus1。

 so G plus1 is the partial derivative of our loss with respect to Z I plus1。



![](img/d274b065e30e493185aa38c4a0cbb160_263.png)

![](img/d274b065e30e493185aa38c4a0cbb160_264.png)

![](img/d274b065e30e493185aa38c4a0cbb160_265.png)

And the really interesting thing here is that there's a very simple， of course。Relationship。



![](img/d274b065e30e493185aa38c4a0cbb160_267.png)

Between the different Gs。Because if I had， say， G plus2， I didn't write the terms here。

 but basically the G plus 2 would involve all the terms up to this one。



![](img/d274b065e30e493185aa38c4a0cbb160_269.png)

![](img/d274b065e30e493185aa38c4a0cbb160_270.png)

![](img/d274b065e30e493185aa38c4a0cbb160_271.png)

And then to compute GI， you just multipied by this last term here as well。



![](img/d274b065e30e493185aa38c4a0cbb160_273.png)

And the way we can write this kind of formally is to say that G is equal to。



![](img/d274b065e30e493185aa38c4a0cbb160_275.png)

Right blue。G I plus 1 times the partial derivative of Z I plus 1。



![](img/d274b065e30e493185aa38c4a0cbb160_277.png)

![](img/d274b065e30e493185aa38c4a0cbb160_278.png)

Partial C。Again， treating everything's a scalar here， doing all our hacks still。

 we'll in the next slide talk about the actual size of these things。

But this is sort of the relationship， even in the scalar case， it would be in the scalar case。

So we have this very nice relationship between these things and we're going to give these things again and again。

 so rather than competing them all from scratch， let's just compete them this way。

' compete them kind of in an iterative fashion like this。



![](img/d274b065e30e493185aa38c4a0cbb160_280.png)

![](img/d274b065e30e493185aa38c4a0cbb160_281.png)

In fact， we can we can write this out more explicitly。 So so now we can sort of write out。

 you know what is Z I plus1 here。 So what is this Z I plus1， Well。

 this is the exact expression for it up here。 So let's be a little bit more precise and actually write out what these what these things really are。

 So this would really be G I plus1 times well， we're going to apply the chain rule one time here。

 And we're going to get partial sigma Z I W I。😊。

![](img/d274b065e30e493185aa38c4a0cbb160_283.png)

![](img/d274b065e30e493185aa38c4a0cbb160_284.png)

![](img/d274b065e30e493185aa38c4a0cbb160_285.png)

![](img/d274b065e30e493185aa38c4a0cbb160_286.png)

Partial Z， I， W， I。

![](img/d274b065e30e493185aa38c4a0cbb160_288.png)

Partial Z， I， W I。Partial Z I。

![](img/d274b065e30e493185aa38c4a0cbb160_290.png)

So let's just applying the chain rule to this expression here。



![](img/d274b065e30e493185aa38c4a0cbb160_292.png)

to this， I mean， to this expression。

![](img/d274b065e30e493185aa38c4a0cbb160_294.png)

And finally， let's now do them， you know， we can use the exact same logic as we did on the previous slide。

 but actually quite a bit more straightforward， I think in this case。 what would this term be， Well。

 this term again is just the derivative of a scalar non nonlineararity with of that argument。

 So this thing will， of course， this one doesn't change。

 So you still just have still just have G I plus one there。 The next one though would just be well。

 it's gonna to be sigma prime of the argument， Z I W I。😊。



![](img/d274b065e30e493185aa38c4a0cbb160_296.png)

![](img/d274b065e30e493185aa38c4a0cbb160_297.png)

![](img/d274b065e30e493185aa38c4a0cbb160_298.png)

And what would then this one be here？This last one with the partial of ZIwiI with the ZI。

 so that would just be WI。

![](img/d274b065e30e493185aa38c4a0cbb160_300.png)

![](img/d274b065e30e493185aa38c4a0cbb160_301.png)

And that that is our expression for basically our recurrence that shows how to form G as a function of G+1。



![](img/d274b065e30e493185aa38c4a0cbb160_303.png)

![](img/d274b065e30e493185aa38c4a0cbb160_304.png)

![](img/d274b065e30e493185aa38c4a0cbb160_305.png)

All right， but this is still kind of using our cheating the patient， you know。

 these are all treated as scalrs。

![](img/d274b065e30e493185aa38c4a0cbb160_307.png)

What do we really do here？

![](img/d274b065e30e493185aa38c4a0cbb160_309.png)

Let's talk now about how we can actually use these operations to compute not just sort of the pretend scalar gradients。

 but the real gradients using the same tricks of size matching that we did before。



![](img/d274b065e30e493185aa38c4a0cbb160_311.png)

And this， I promise you will be the last time we do this。

 at least the last time you do it for a whole derivative。

 not just for sort of individual operations and automatic differentiation。



![](img/d274b065e30e493185aa38c4a0cbb160_313.png)

![](img/d274b065e30e493185aa38c4a0cbb160_314.png)

Okay， so let's， let's first talk about what these Gs actually are。 Okay。

 so these G is the way to define them， it was the derivative of our loss with respect to Z I right。

 G I would be right G I would be the derivative of the partial derivative of whatever the。

Of our loss with respect to Z， but if we think about this as an actual quantity。

 what we would actually be computing here would be what we want to store here would be the gradient with respect to Z I of this loss right this is just now I'm just writing these things kind of as when you compute the gradient what this really is is you know when you can these parts of it' kind of cheating。

 which are really after here is the gradient So what really after here is the gradient of our loss。😊。



![](img/d274b065e30e493185aa38c4a0cbb160_316.png)

![](img/d274b065e30e493185aa38c4a0cbb160_317.png)

![](img/d274b065e30e493185aa38c4a0cbb160_318.png)

![](img/d274b065e30e493185aa38c4a0cbb160_319.png)

ZL+1 and Y with respect to Z。And the key point I want to emphasize here is the size of this thing。



![](img/d274b065e30e493185aa38c4a0cbb160_321.png)

Al right， so the size of Z I remember was actually and this this is I kind of went over briefly here about like what size you know what dimension Z I was。

 But if if you go back a few other slides， what you'll see is that Z I was actually。



![](img/d274b065e30e493185aa38c4a0cbb160_323.png)

![](img/d274b065e30e493185aa38c4a0cbb160_324.png)

![](img/d274b065e30e493185aa38c4a0cbb160_325.png)

M M rows， because we had one， again， Z icon kind describes those hidden units or the activations for every single example in our data set。

 or in our batch， if you do it by batch， etc ceter。

 and it was by NI because the dimensionality of each row was NI dimensions。



![](img/d274b065e30e493185aa38c4a0cbb160_327.png)

Okay。

![](img/d274b065e30e493185aa38c4a0cbb160_329.png)

So that means， of course， that our gradient of our loss with respect the I should also be that same size。

 it should be M by N。

![](img/d274b065e30e493185aa38c4a0cbb160_331.png)

All right， so let's now use our， our logic here to。So use our logic here to figure out， you know。

What what the GI sort of backward iteration really should be not in terms of sort of you know scale if everything was scalar。

 but if these things are actually matrices。

![](img/d274b065e30e493185aa38c4a0cbb160_333.png)

Okay， so GI just copying what we had in the last slide and to sort of count on me on this that I'm fact copying correctly here。

 it was G plus1 times Sigma prime Z I W I times W I。



![](img/d274b065e30e493185aa38c4a0cbb160_335.png)

![](img/d274b065e30e493185aa38c4a0cbb160_336.png)

Alright， and let's do our thing one more time。 Well， actually maybe not quite。

 we're gonna do it again in the next half of this this slide too。 but G plus one， well。

 that would be actually， that's just going to be the same size as you know for for our next vector。

 what that will be， so that will be。😊。

![](img/d274b065e30e493185aa38c4a0cbb160_338.png)

![](img/d274b065e30e493185aa38c4a0cbb160_339.png)

![](img/d274b065e30e493185aa38c4a0cbb160_340.png)

M by N+ 1。

![](img/d274b065e30e493185aa38c4a0cbb160_342.png)

Okay， that's the size of GI。The size of。Sigma Z I W I is actually the same thing because right。

 that's that's the that's the same， the size of our Z I after we had then applied W I would be the same as as the size。

 So this would be M by N。

![](img/d274b065e30e493185aa38c4a0cbb160_344.png)

![](img/d274b065e30e493185aa38c4a0cbb160_345.png)

![](img/d274b065e30e493185aa38c4a0cbb160_346.png)

I plus 1。And this last one here， W is just N by N plus one。



![](img/d274b065e30e493185aa38c4a0cbb160_348.png)

![](img/d274b065e30e493185aa38c4a0cbb160_349.png)

Okay， so again， deep breath， hopefully you know， not sweating too much here as we go through all of this。



![](img/d274b065e30e493185aa38c4a0cbb160_351.png)

This thing would be equal to well how do we make these fit， well。

 we know we want our final thing to be some M dimensional thing by os。



![](img/d274b065e30e493185aa38c4a0cbb160_353.png)

Some M dimensional thing by N。The only way we can get an NI term at the end is if we have something here times WI transpose。

 that's the only thing that has an NI， we have an NI as a last dimension。



![](img/d274b065e30e493185aa38c4a0cbb160_355.png)

![](img/d274b065e30e493185aa38c4a0cbb160_356.png)

And then we have something here， so this right so this this term here would be。And。I plus1 by N I。

 So in here we need something which is M by N I plus1 and actually just in the same way that we did this for the two layer case。

 the thing we actually do to make， you know these are both these are both that size。

 right these are both the size we want there。

![](img/d274b065e30e493185aa38c4a0cbb160_358.png)

![](img/d274b065e30e493185aa38c4a0cbb160_359.png)

![](img/d274b065e30e493185aa38c4a0cbb160_360.png)

![](img/d274b065e30e493185aa38c4a0cbb160_361.png)

So what you do is you just take their element wise multiplication again that actually comes out because sigmas also applied element wise。

 but what this ends up being is just G plus1 headammard or element wise multiplication with Sigma prime Z W Okay so that's the actual this thing here is the actual update。



![](img/d274b065e30e493185aa38c4a0cbb160_363.png)

![](img/d274b065e30e493185aa38c4a0cbb160_364.png)

![](img/d274b065e30e493185aa38c4a0cbb160_365.png)

Or Gs， if you want to not just sort of conceptualize it。

 but actually implement it in matrix operations， this is the update you need。



![](img/d274b065e30e493185aa38c4a0cbb160_367.png)

Okay。😊，Almost there。We have the backward iteration for the G's now in real matrix arithmetic。

 but we also need to compute the gradient we want， which is the gradient with respect to the parameters。

 that's what we actually need in order to compute our updates。Okay， so what is that？That is。

Our the parameter up that we want， of course would be this size here。

 right we want something which is N by N plus one。So let's just write out what this gradient actually is。



![](img/d274b065e30e493185aa38c4a0cbb160_369.png)

Well， again， actually just just taking the question from the previous slide。

 you can go back and look to make sure that I'm copying them correctly here。



![](img/d274b065e30e493185aa38c4a0cbb160_371.png)

![](img/d274b065e30e493185aa38c4a0cbb160_372.png)

But， this would be。G I plus 1 times partial Z I plus1。



![](img/d274b065e30e493185aa38c4a0cbb160_374.png)

![](img/d274b065e30e493185aa38c4a0cbb160_375.png)

Partial。W I。

![](img/d274b065e30e493185aa38c4a0cbb160_377.png)

But that would be equal to。GI+1 times partial， well let's just plug in the definition of what's Z plus1 there。

 it would be partial sigma， Z I， W I。Very similar actually to the past expression we had to。

 partial Z I， WI。Times partial Z I， W I， partial WI。



![](img/d274b065e30e493185aa38c4a0cbb160_379.png)

All right， and that's going to equal G times sigma prime Z I W I。

 a lot of terms are the same as before， of course， times sorry G plus1。



![](img/d274b065e30e493185aa38c4a0cbb160_381.png)

![](img/d274b065e30e493185aa38c4a0cbb160_382.png)

对。There is that there， G。

![](img/d274b065e30e493185aa38c4a0cbb160_384.png)

I plus1 times Z。 The only difference between this and the press expression is that because we're differentiating now with respect WiI。

 you get Z I here， right because it's this product lookss respect the WI。



![](img/d274b065e30e493185aa38c4a0cbb160_386.png)

![](img/d274b065e30e493185aa38c4a0cbb160_387.png)

Other than that actually ends up being the same， kind of hiding with my head。 I realized that， but。



![](img/d274b065e30e493185aa38c4a0cbb160_389.png)

We won't need it soon。😊，Okay， so now let's now let's I'll duck down here and we'll write the sizes for this。

 Okay so this one here is going to be same as before it's going to be M by N plus1。

 This one here is also M by N plus1 and this one's only difference thing we have from last time This is going to be M by N。



![](img/d274b065e30e493185aa38c4a0cbb160_391.png)

![](img/d274b065e30e493185aa38c4a0cbb160_392.png)

![](img/d274b065e30e493185aa38c4a0cbb160_393.png)

O。嗯。

![](img/d274b065e30e493185aa38c4a0cbb160_395.png)

All right， so now how do we arrange these sized matrices？2。Add up to this size。Well。

Hopefully I won't belabor this point too much， but what you have to do is we need an NI first you have to take ZI。

And transpose it first。D I transpose？Times really， it ends up being， it's this product here。

Which actually is exactly the same thing as we had before。

 and it ends up being the same product as before。 So it would be this times G plus1。



![](img/d274b065e30e493185aa38c4a0cbb160_397.png)

Element wise product with。Sigma Prime Z， I， W I。And that is， in fact， the gradient we are after。



![](img/d274b065e30e493185aa38c4a0cbb160_399.png)

Okay， so now we actually have done everything you need to compute all your gradients for an arbitrary L layer network。

 I've told you how to compute。The not just like the theoretical gradients， but the actual gradient。

 the actual sizes of these different matrices here right so for all the actual parameters here in actual matrix therithmetic。

 how to do this and。😊。

![](img/d274b065e30e493185aa38c4a0cbb160_401.png)

This is maybe a bit more complicated than you seen before。

 so I wanted to sort of take a pause for a moment here and argue about kind of why I've done it this way a lot of times you will see。



![](img/d274b065e30e493185aa38c4a0cbb160_403.png)

![](img/d274b065e30e493185aa38c4a0cbb160_404.png)

Gradients for neural networks kind of written out element by element。

 So you know just because scans are easy to work with。

 you'll have derivatives of different terms to different individual terms of Wi will involve a lot of sums and stuff like this。

 But the reality is no one would actually ever implement it that way I mean。

 no one will implement it anyway， because everyones automatic differentiation。

 But even if you were implementing kind of back back propagation like this from scratch。

 I'll talk about what name is called back propagation in a second。

 you would implement it always using matrix operations。

 And so what I really want to you do from the start here is show you how to derive those actual matrix expressions because you're gonna to do little pieces of that when you do the equivalent matrix operations and automatic differentiation。

 So even though this may seem in some sense more confusing we're taking weird sizes and making them fit for this really hacky way that is hacky I admit。

 But。😊。

![](img/d274b065e30e493185aa38c4a0cbb160_406.png)

![](img/d274b065e30e493185aa38c4a0cbb160_407.png)

I a reason why we're doing it this way， it's much better to learn how these things actually work and work in a way that we actually would implement them than sort of derive each individual expression out in a way that no one would ever actually implement the as。



![](img/d274b065e30e493185aa38c4a0cbb160_409.png)

Al right， so with all this being said， what is the final form for our algorithm Now。

 the way this sort of way of compute goes by the name back propagation and back propagation is typically framed as having two different passes over the layers of our network。

 a forward pass and the backward pass， which basically compute in the forward pass。

 the Z terms and in the backward pass， the GiI terms。



![](img/d274b065e30e493185aa38c4a0cbb160_411.png)

![](img/d274b065e30e493185aa38c4a0cbb160_412.png)

So making this a bit explicit。 the way we compute the forward pass and back propagation is a way of computing all these gradients。

 So the way we compute forward pass is we first is initialize our first layer to just be our input。

 right， That's kind of convention。 We just make our first layer equal to our input。

 really so we can use the sameim notation for all subsequent layers。😊。



![](img/d274b065e30e493185aa38c4a0cbb160_414.png)

![](img/d274b065e30e493185aa38c4a0cbb160_415.png)

![](img/d274b065e30e493185aa38c4a0cbb160_416.png)

Then we form our iteration here of Z I plus1 equals sigma I of Z W from i equals 1 to L， by the way。

 just just reemp this again， you know I had my nonlinear here vary by I and frequently the last layer would just not even have an nonlinear it would just be a linear layer。

 but that's just details you can really actually do whatever you want in this formulation。



![](img/d274b065e30e493185aa38c4a0cbb160_418.png)

![](img/d274b065e30e493185aa38c4a0cbb160_419.png)

![](img/d274b065e30e493185aa38c4a0cbb160_420.png)

![](img/d274b065e30e493185aa38c4a0cbb160_421.png)

Okay， so this just computation， really， computation of the actual output is called the forward pass of the network of back propplication。



![](img/d274b065e30e493185aa38c4a0cbb160_423.png)

Or forward pass to the network。The backward pass and sometimes of them actually just the backward pass is referred to as back propagation。

 though whether you call both the forward backward pass propagation。

 actually what you even called back propagation is a bit is a bit odd like he is automatic differentiationation actually doing back propag or not。

 I think even actually Tiianch I use slightly different terminology here so be aware there's no like single definition of this。

 but other than say that backpro is the way that you actually compute gradients here。😊。



![](img/d274b065e30e493185aa38c4a0cbb160_425.png)

![](img/d274b065e30e493185aa38c4a0cbb160_426.png)

![](img/d274b065e30e493185aa38c4a0cbb160_427.png)

What the backward past does is it initializes the first of all the last backward gradient。

 which just be the gradient of the loss with respect to， you know the last unit itself in the case。

 I should sort of qualify this， you know in the case of，😊，Crossentpy。Loss。

 this would actually be equal to that S minus IY term he saw before。 So take the output。



![](img/d274b065e30e493185aa38c4a0cbb160_429.png)

![](img/d274b065e30e493185aa38c4a0cbb160_430.png)

Form the softm that becomes S。 subtract off the one hot encoding。 That's the。

 that's the first term G I or G L plus one。

![](img/d274b065e30e493185aa38c4a0cbb160_432.png)

And then you perform the backward updates on the GIs as we exactly derived in the previous slides so that is just the previous slide here。

 that is just this update here for those。

![](img/d274b065e30e493185aa38c4a0cbb160_434.png)

![](img/d274b065e30e493185aa38c4a0cbb160_435.png)

![](img/d274b065e30e493185aa38c4a0cbb160_436.png)

All right。And finally。You can do this from L， you just the in reverseverse order。

 you do it from I equals L to 1， and then as you go， as you do this。

 you can also of course compute the gradients， which again was exactly what we had in the last page of the parameters。



![](img/d274b065e30e493185aa38c4a0cbb160_438.png)

![](img/d274b065e30e493185aa38c4a0cbb160_439.png)

![](img/d274b065e30e493185aa38c4a0cbb160_440.png)

Now， the important thing keep in mind here is this sort of computes simultaneously all the parameters in one forward pass and one backward pass。

 right， because we can kind of use these GI terms and the ZI terms to compute all these needed gradients。



![](img/d274b065e30e493185aa38c4a0cbb160_442.png)

![](img/d274b065e30e493185aa38c4a0cbb160_443.png)

![](img/d274b065e30e493185aa38c4a0cbb160_444.png)

![](img/d274b065e30e493185aa38c4a0cbb160_445.png)

But to do that， we need to sort of cache things along the way， right。

 we need to sort of compute this term， these GI terms to kind of reuse them。

 we're not going to kind of form them from scratch。



![](img/d274b065e30e493185aa38c4a0cbb160_447.png)

![](img/d274b065e30e493185aa38c4a0cbb160_448.png)

And so really， in some broader sense， all back propagation is is just the chain rule and intelligent caching of the intermediate results。

 and that's what back propagation is。Now， one important point that I want to highlight on this is that。



![](img/d274b065e30e493185aa38c4a0cbb160_450.png)

This let's look at the form that is required to compute the gradient for the WI of our loss。



![](img/d274b065e30e493185aa38c4a0cbb160_452.png)

![](img/d274b065e30e493185aa38c4a0cbb160_453.png)

And notice that it contains terms both ZI and GI。

![](img/d274b065e30e493185aa38c4a0cbb160_455.png)

And what this means is that to compute this gradient。



![](img/d274b065e30e493185aa38c4a0cbb160_457.png)

You know， we do it， we can actually kind of do it along the way in our backward path。

But we had to store the Zs。 We can't throw away any of the intermediate terms in the forward passes。

 We have to keep them around so that we can use them to compute part of our backward of our backward gradient。

 And so even though this is sort of efficient from the standpoint of we're making one forward pass。

 the network and one backward pass， it ends up being actually just twice the complexity of a single forward pass。



![](img/d274b065e30e493185aa38c4a0cbb160_459.png)

It's much less memory efficient in some sense because we have to store all our items along the way we can't。

 if I would just kind of compute the output， right， I could actually， once I computed ZI plus1。

 I could throw out ZI， but I can't do that here。

![](img/d274b065e30e493185aa38c4a0cbb160_461.png)

![](img/d274b065e30e493185aa38c4a0cbb160_462.png)

![](img/d274b065e30e493185aa38c4a0cbb160_463.png)

And this notion of maintaining intermediate elements in this forward and backward pass is actually really crucial to back propagation becomes one of the chief kind of tradeoffs of back propagation。

 it's allowing for more efficient computation of gradients at the cost sometimes of more memory storage so that's not really a preview for sort of later things。

 but just keep that in mind when we talk about actually how efficient and back propagation is it is very efficient computationally。

 but it does incur at least naively speaking does incur some added memory cost。😊。



![](img/d274b065e30e493185aa38c4a0cbb160_465.png)

![](img/d274b065e30e493185aa38c4a0cbb160_466.png)

![](img/d274b065e30e493185aa38c4a0cbb160_467.png)

![](img/d274b065e30e493185aa38c4a0cbb160_468.png)

All right， so with that being said， I have only one slide left to talk about。

 which is to say the following。

![](img/d274b065e30e493185aa38c4a0cbb160_470.png)

So that's actually that's generic backpro for multilayer neural networks in true matrix form。

And I do think it's fair to say that most kind of machine learning courses that discuss backpro。

 they often end there。sort of say here's how you drive back， maybe they'll talk about convolutions。

 but they also don't even talk about how you derive backp for a convolution。

 They just talk about know the forward pass of avolution and assume it's all sort of works up when you talk about actual backp。

 most classes can stop there。 Maybe they don't even quite get there because they don't even get to matrix form。

 but they kind of get there and then that's deep networks。 that's the end of it。 And for us。

 of course， you know， that's the start of it right And in fact。

 it's not how we're gonna do it in any more of this class。😊。



![](img/d274b065e30e493185aa38c4a0cbb160_472.png)

![](img/d274b065e30e493185aa38c4a0cbb160_473.png)

So。😊，The last thing I want to lead you with， before we。Never see these things again。

Is to think a bit more about what's in some sense， really happening in the backwards iteration。



![](img/d274b065e30e493185aa38c4a0cbb160_475.png)

So to compute， you know， this gradient here。

![](img/d274b065e30e493185aa38c4a0cbb160_477.png)

Graadient will respect the WI of a term， of course I'm running it's derivative now。

 but really it to gradient。

![](img/d274b065e30e493185aa38c4a0cbb160_479.png)

What we need to do is we sort of had this， we had this term GI+1， and we multiplied it。



![](img/d274b065e30e493185aa38c4a0cbb160_481.png)

By the individual terms， of course broken down with a chain rule。

 but basically we have to multiply it by these terms here that involve just the derivatives of the Ih layer。



![](img/d274b065e30e493185aa38c4a0cbb160_483.png)

![](img/d274b065e30e493185aa38c4a0cbb160_484.png)

![](img/d274b065e30e493185aa38c4a0cbb160_485.png)

And one way to view this is what was the job of the I layer in some sense， right， Well， the I layer。

 first of all I had to compute itself， I had to know how to compute the I layer， but it also。

 if you just start trying to tell about like what's the responsibility of the I layer。

 and that's a very way maybe odd way of phrasing it， but its responsibility。

 it's first be able to compute kind of， you know its forward pass right。

 compute its layer compute itself。

![](img/d274b065e30e493185aa38c4a0cbb160_487.png)

![](img/d274b065e30e493185aa38c4a0cbb160_488.png)

And it also had to take this term here， this， what I'll call this like incoming backward gradient G plus1。



![](img/d274b065e30e493185aa38c4a0cbb160_490.png)

![](img/d274b065e30e493185aa38c4a0cbb160_491.png)

And multiply it。By its own derivatives， the derivative of Z+1 partial WI right。

 really the great I mean， this is actually some big sort of Jacobian thing。

 but ignoring that for a second， it had to actually figure out how to multiply this thing by this thing and whatever size actually made sense here。



![](img/d274b065e30e493185aa38c4a0cbb160_493.png)

![](img/d274b065e30e493185aa38c4a0cbb160_494.png)

![](img/d274b065e30e493185aa38c4a0cbb160_495.png)

![](img/d274b065e30e493185aa38c4a0cbb160_496.png)

And this is actually a crucial insight into making this whole procedure more modular。

Because this is a very general statement， generally speaking。

 all that any layer has to be able to do in order to fit into a back propagation framework。



![](img/d274b065e30e493185aa38c4a0cbb160_498.png)

Is be able to multiply the incoming backward gradient with its own derivatives。In fact。

 this is such a common thing that it has its own name。

 and this is an operation called the vector Jacobian product。



![](img/d274b065e30e493185aa38c4a0cbb160_500.png)

That term is actually quite misleading because GI in reality is not actually a vector。

 but what that really means is is you think of this whole thing as a vector and you think of this thing really a multivariate clus as what's called a Jacobian。

😊。

![](img/d274b065e30e493185aa38c4a0cbb160_502.png)

![](img/d274b065e30e493185aa38c4a0cbb160_503.png)

This operation multiplying this thing here by this thing。

 that is what's called a vector Jacobbian product。

![](img/d274b065e30e493185aa38c4a0cbb160_505.png)

![](img/d274b065e30e493185aa38c4a0cbb160_506.png)

And the very interesting thing is that this process can be made much more modular and much more general。

And this is exactly the process that we're going to cover next lecture。😊。

Maybe not in full generally but over the next few lectures and of course。

 also in the homework assignments， this is exactly the process you will cover when it comes to automatic differentiation。

 which then beautifully will sort of avoid the need for any of this hacky math and kind of manual application of the chain rule to the point where you start to sweat。

😊。

![](img/d274b065e30e493185aa38c4a0cbb160_508.png)

You have to do it， it's good to do it once， it's good to go through the exercise of manually deriving backpro for a multiplayer neural network once。

Now shove it away and let's start next time talking about automatic differentiation or how we really do this in practice。



![](img/d274b065e30e493185aa38c4a0cbb160_510.png)