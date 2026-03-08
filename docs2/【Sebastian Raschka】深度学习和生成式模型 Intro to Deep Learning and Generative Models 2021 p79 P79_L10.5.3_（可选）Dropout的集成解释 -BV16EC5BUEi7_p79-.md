# 【Sebastian Raschka】深度学习和生成式模型 Intro to Deep Learning and Generative Models 2021 p79 P79_L10.5.3_（可选）Dropout的集成解释 -BV16EC5BUEi7_p79-

![](img/3d5686d713db9d1054e3ebf13930f5bd_0.png)

Yeah now let's look at other explanation for why dropout might perform well。

 and this is in the context of ensemble methods， so we can essentially see dropout as an ensemble method as I will show you in the next couple of slides and yeah what is an ensemble method So students who have taken 451 we talked there about ensemble methods a lot。

 we talked about， for instance， majority voting， begging。

 random forests boosting you don't have to know any of that for this class here but in a nutshell what is an ensemble method。

It's essentially a combination of multiple models where you average the results of the models。

 So you can think of it intuitively。 Let's say you have to make an important financial decision。

 let's say， yeah， you you want to make or you want to buy something or invest。

 let's say you want to invest into something。 And it's a very important decision。

 So you consider asking an expert。 So the expert here is your model。

 And it might give you a prediction or some advice。That might be， yeah。

 a good advice if it's an expert and expert。now is the topic very well。 However， in practice。

 it's usually an even better idea to ask a couple of experts and then consider， yeah。

 the shared opinion of the experts。 So it's not always better than let's say the opinion of a single person。

 especially if yeah the committee doesn't agree with a single person and the single person knows something the committee doesn't know。

 but on average， usually asking committee of multiple people is a better idea than just relying on the opinion of a single person right So in that way。

 using multiple models and then averaging the predictions or taking the majority vote。

It's also often a better idea than yeah using a single model。 Why don't we do that always then， yeah。

 well because it's usually very expensive to train models， especially in deep learning。

 So in deep learning， I would say most of the time we want to focus on a single model because it's computationally cheaper and we also often care about yeah improving a model in general and then let's say in production you can always yeah train multiple of these models and then combine them。

To make the predictions even more robust， in any case。

 talking about the ensemble approach now why dropout can be seen as an ensemble method。



![](img/3d5686d713db9d1054e3ebf13930f5bd_2.png)

So you can think of yeah， drop out the procedure as having a different model for each mini batch right。

 so because you randomly drop node， each forward pass。

 each mini batch will see a slightly different model and。Essentially。

 what we do is we sample over2 to the power of H models， but H is the number of hidden units。

 If we only consider a hidden layer， if we have multiple hidden layers， well。

 this becomes even larger。 But if you have already， let's say。

Or if you only have a hidden layer with 10 units， you already have 10 to the power of 10 possible combinations。

Of hidden layers that you may sample during each forward pass。So in that way， it。

 it can be seen as a model ensemble。Except that there is one restriction。

And the restriction is that we have a time dimension。 So we don't have these models in parallel。

 right。 So what I mean is if we have。Say hidden there。

 a network like that and another network like that。And it be。Im runningning out of space。

Let's say each of these is one multiceptron。 I'm not connecting all the units here。

 but let's say in this first one， first forward pass， we drop this one and the other one。

 we drop this one。 And then here we drop these ones。 So we have three different networks here。

 but we don't use all of them in parallel， right， We usually。Because it's a training for for loop。

 we。Go through them one at a time， So we。Have during the first followed pass， maybe this model。

 during the second pass， this fall this model and during the third pass this model。

 So there's essentially a time constraints， a restriction。And。

We can also see this restriction as weight sharing， because。The second model。Receive or it will。

 the first model will update the weights， and then the second model。

Will be depending on the weight updates from the first model， right。

 it's just like how the regular training works， because each iteration you update the weights and each consequent model will work with the weights from the previous backward pass。

 So in this way， there's like this weight sharing between the different forward passes。

So there's a weight sharing over these models。 And yeah， we can see that as a type of regularization。

 like a constrained， an additional piece of information or constraint that we add。 So in that way。

 we can see this weight sharing as a， yeah， as a regularization and。Still， we have。 Meanwhilewhile。

 we have this weight sharing during training。 we could technically。

Create all these different models after training during inference and then average over all these models。

I mean， there's nothing that prevents us from doing that。

 The only problem with that is if we even only consider a small case with 10 to the power of 10 combinations。

 This is like a very large combination of models。 So this is very， very， very expensive。

 And this is something we technically wouldn't want to do in practice because yeah。

 it's it's just way too expensive。

![](img/3d5686d713db9d1054e3ebf13930f5bd_4.png)

But yeah， let's just for a second， continue with this thought experiment and assume we have now。Yeah。

 created all these models for or during inference。 So， for instance。

 if we had a hidden layer with 10 units， we have these 10 to the2 to the power of 10 models。

 Let's call that。M we have M models now。 So how do we average the predictions of these models for simplicity。

 think of a binary classification case。 And in this case。

 it's essentially averaging the lock likelihoods。Of the predictions。

 which is essentially what you probably know as the geometric mean， so。For instance。

 if we have a P probability Sc P for a given test data point I。 So thiss test data point I here。

 then we multiply all these probabilities for the M models and take this。To the power of one over M。

 And here， I was just rewriting this to show you this is， yeah， essentially averaging likelihood， so。

Its sum over the lock likelihood terms here。 And then times1 over m。

 And here I'm just adding the exponent。 So I was just taking considering the lock of this here and this one un the un does it。

 So it's essentially the same computation。 And here inside。

 you can think of it as averaging the lock likelihoods。

 So essentially what this is it's we are computing the geometric mean。

So that would be one way we can combine the predictions。And yeah， if we have multiple classes well。

Yeah， more than binary classification。 we also want to normalize these so that they sum up to one probabilities because we have multiple classes。

 right， if we have multiple classes， we have multiple probabilities scores and ideally we want them to sum up to one and the class label can then be obtained by considering the class with the highest probability。



![](img/3d5686d713db9d1054e3ebf13930f5bd_6.png)

Yeah， but this still doesn't solve our problem that this is very computationally expensive because we we have to consider2 to the power of 10 models right for averaging。

 And here this is also assuming that we only have one hidden layer with only 10 units if we have a hidden layer。

 let'd say， with 64 units。 then yeah， this would be really infeasible。So what do we do about that。

 How can we address this problem， So actually， the regular dropout technique that we discussed earlier。

Essentially， is already computing this geometric mean or essentially。

 it's approximating this geometric mean。 because， yeah， the scaling factor that I mentioned。

 the 1 minus P that we use to scale the data after training when we use the model for testing。

 This is essentially an approximation of this geometric mean。

 So we don't have to create all these different models。

 we only consider the last model after training。 So just the model that comes out out of training。

 and then this scaling will essentially。Compute an approximated version of that geometric mean。

 as they mentioned in the original dropout paper。And they also argue， essentially， if you。

Have a linear model。Then the geometric mean would be ex actually exactly like this scaled version here。

 So essentially， we are approximating the geometric mean in dropout of a model ensemble。

 And this is essentially the explanation of dropout why it might work well， because essentially。

 we can think of it as a model ensemble。

![](img/3d5686d713db9d1054e3ebf13930f5bd_8.png)