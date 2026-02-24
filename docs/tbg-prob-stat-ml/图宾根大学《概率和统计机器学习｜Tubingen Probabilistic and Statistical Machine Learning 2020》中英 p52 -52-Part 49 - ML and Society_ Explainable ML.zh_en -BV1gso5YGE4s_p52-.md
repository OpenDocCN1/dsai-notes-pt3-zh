# 图宾根大学《概率和统计机器学习｜Tubingen Probabilistic and Statistical Machine Learning 2020》中英 p52 -52-Part 49 - ML and Society_ Explainable ML.zh_en -BV1gso5YGE4s_p52-

In this lecture， I now want to talk about explainable machine learning。



![](img/721083320adbdaed1f33a52bdfb9c1fc_1.png)

Explanations for machine learning algorithms or the outcome of machine learning algorithms are very。

 very important in particular if it comes to applying machine learning in a social context。😊。

Or in a medical context， consider an application where you have like an assistive system for some doctor。

 you put in some data by a patient and then the system maybe makes a recommendation for what to do。😊。

OrA suggestion for the disease that this person has。And now you as a doctor。

 you don't want to trust any black box algorithm where you sort of cannot really understand why the machine came to this decision。

 so maybe this patient has very unusual symptoms and you don't really understand it and then the machine says something and you as a doctor if you want to be able to trust the thing。

You need to get some explanation of the machine why it came to that conclusion。

Also in a social context， like if you imagine a certain situation， for example。

 a bank giving someone a credit or giving you not a credit。

 then you would also like to have an explanation for why the machine came to this particular decision。

😊，And the Eu data protectiontection regulation， which came into effect 2018。

 has an explicit paragraph about this。😊，Which is typically interpreted as a right for explanations。

And if you read this regulation， it was a bit surprising to myself how sloppy it is formulated。

 but what it essentially says is something like what is written here on that slide。😊。

In case of automated decision making， the controller， which is the person who runs the algorithm。😊。

Shall provide the subject， the person on whom this decision is being made。

With meaningful information about the logic involved。So somehow。

 if you're the bank and there's this customer and you tell the customer you don't get a credit。

 the customer should get some explanation for why he or she didn't get the credit。And as I said。

 the goal of these explanations might be from a machine learning or like maybe rather from the application point of view。

 I mean， you want to establish understanding。😊，You might want to establish stress trust。

 like in this medical example。You might want to have sanity checks also in a medical example。

 maybe you want to know that the thing doesn't really do something completely stupid。

 but in like more cases in society， you might have the possibility to object so maybe you want to say。

 well， if this is your reason for not giving me the credit。

 I think you're wrong and I should get the credit because and then you can start to argue about it。

But of course， you cannot argue if the bank just says we have this deep network and the deep network simply says you don't get a credit。

😊，And now the question is of course， how we can make machine learning more explainable。

 as we know there are many machine learning algorithms that are really not something that is easy to explain to the general public if you tell something you know。

 I trained the support vector machine with a certain kernel and then this is the outcome。

 I mean this is not something that anybody would understand and even more so for deep networks。😊。

So the question is now how can you provide explanations of？😊。

Either the working of machine learning algorithms， but most of the cases。

 it concerns about the prediction that the machine learning algorithm makes。😊，And now there exist。

 I mean this is now an active field of research it used already to be a somewhat active field of research。

 but the data protection law has really pushed this field very much and I think it's a positive example for a regulation that really had some effect because I mean since this regulation is in fact is active。

 oil companies need to be able to produce these explanations。😊。

At least in the extreme case that somebody takes you to court and wants to say， okay。

 I think something is wrong and I have the right for explanation and you don't provide it to me。

 so the companies need to think about it and this promoted the same at the same time。

 a lot of research to start thinking about how could we generate these kind of explanations。



![](img/721083320adbdaed1f33a52bdfb9c1fc_3.png)

![](img/721083320adbdaed1f33a52bdfb9c1fc_4.png)

Now they exist many different mechanisms I have here a couple of them on the slides and I will present one slide or so for each of them。

😊。

![](img/721083320adbdaed1f33a52bdfb9c1fc_6.png)

![](img/721083320adbdaed1f33a52bdfb9c1fc_7.png)

You could start explaining by the mechanism of the algorithm like in a kind Ne graph or a decision tree。

 there exist exemplar based explanations， feature based explanations。

 counterfactual explanations and local explanations Now this of course doesn't mean anything to you and now I'm trying to explain each of them very briefly just it's just meant to give an overview one on each slide。

😊。

![](img/721083320adbdaed1f33a52bdfb9c1fc_9.png)

![](img/721083320adbdaed1f33a52bdfb9c1fc_10.png)

![](img/721083320adbdaed1f33a52bdfb9c1fc_11.png)

Explaining by examples， so the typical thing is you say to this there is a person and the person doesn't get the credit and then you say you don't get this credit because you' are very similar to this other person X and person X didn't get the credit either。

😊，This might not be a completely satisfactory answer， at least if you don't get the credit。

 but at least it gives you some kind of reasoning。😊。



![](img/721083320adbdaed1f33a52bdfb9c1fc_13.png)

In a medical case， this could also be very helpful you say to the doctor。

 well I think this patient it has this particular symptoms because he's very similar to this other patient and he had these symptoms as well and treatment A had this particular person so maybe it's also going to help this other person。

😊，So this is a very simple kind of mechanism which relates on some kind of neighborhood argumentation。

 you say， okay within the training set you look for similar people and then you sort of explain the decision that is taken on yourself by the decisions that happen to the people around you。

😊。

![](img/721083320adbdaed1f33a52bdfb9c1fc_15.png)

Another thing that is really popular is to identify relevant features。 For example。

 if you have a decision tree。😊。

![](img/721083320adbdaed1f33a52bdfb9c1fc_17.png)

Typically many decision trees are built in such a way that like at the top notes you split at the features that are most important for the decision that you need to take in the end。

 so if you now have a medical example and you have a decision tree and at the top the first note splits your patients into young people and elderly people and then it splits into patients who have I don't a low blood pressure and a high blood pressure and then after like a couple of vertices you at the bottom and you get the diagnosis。

😊。

![](img/721083320adbdaed1f33a52bdfb9c1fc_19.png)

![](img/721083320adbdaed1f33a52bdfb9c1fc_20.png)

Now the doctor can go along this path and can see， okay， yes， it's a person， it's an elderly person。

 he has low blood pressure and these other kind of symptoms， Yeah。

 it makes sense that this person maybe should get this in this treatment。



![](img/721083320adbdaed1f33a52bdfb9c1fc_22.png)

![](img/721083320adbdaed1f33a52bdfb9c1fc_23.png)

So here you would explain the decision of a system by talking about the features or the most important features of this person that made the algorithm decide in this particular way。

You can do something similar in a linear model if you instead of a decision tree have simply a linear model where you say we have we take all the features of this patient train a linear model and then some kind of regression output and then in this linear model we now have a linear combination a weighted linear combination of all the features and now you can say maybe let's look at the features that have the highest weights so maybe the features with the highest weights in our linear model are the blood pressure the age and I don't know what。

😊，And then you could and then there are some more features。

 but those are maybe don't have so large weights。 then you could tell the doctors's look I mean。

 this machine takes into account all all100 features， but in the end。

 it focuses on the first three or first five ones。 and these are the following ones。

And then the doctor can say， I mean， either this makes sense or this is complete bullit because I don't think that the age has anything to do with this particular disease。

 I don't trust this machine。

![](img/721083320adbdaed1f33a52bdfb9c1fc_25.png)

Another field of research that is quite active is counterfeual explanations。

 again it relates to the theory of causality and I don't want to give any big introduction here。

 but essentially what you' are trying to produce is counterfual statements like if your income would be 500 more than you would get the credit。

😊，So sort of this tries to tell you what is the least amount of things that you would need to change such that in the end you would get the credit。



![](img/721083320adbdaed1f33a52bdfb9c1fc_27.png)

And then the last thing I want to talk about a bit more extensively is local explanations for highly complex models。

 and this is an area that I find particularly interesting maybe also because we have a recent paper in this area and the idea is now the following。

😊。

![](img/721083320adbdaed1f33a52bdfb9c1fc_29.png)

Assume we are in a high dimensional Euclidean space and we have learned a complex function。

 and this could be like a support vector machine with a Gausian kernel。

 but it could also be a neural network。 So the standard neural network setting is you get images。

 they live in a very high dimensional Euclidean space and you train some very complicated thing and you get a prediction out。

😊，Okay， and this is a very complicated function。😊，And now。

I mean one approach that you might want to take is to say， okay， look now I have this function。

 but in order to be able to explain it， I need to find a simpler function by which I can explain the behavior。

 for example， a linear function or a decision tree or so that reproduces the outcome of this complicated function。

But of course， in principle， this is not possible because， I mean。

 we took all the care we could to construct this very complicated model because I mean。

 if we could have fitted or achieved the same result with a linear function。

 then we wouldn't need to use a deep neural network。😊，But typically， in many cases。

 where we use these networks like a simple linear function or a simple decision tree wouldn't do the job。

😊，Now， so we cannot simply say we replace this complicated function by something simple that we can explain。

 at least not on a global scale。😊，But what we can do now is we can try to approximate this complicated function locally by something that is much simpler。

 So what we could do is we could try to see in the in the neighborhood。

 So we might be interested in the。An explanation。For a prediction of that one particular input。

 So there's one patient。 The patient gets a diagnosis。

 and we want to explain why we get this diagnosis for this particular patient。



![](img/721083320adbdaed1f33a52bdfb9c1fc_31.png)

And now the idea of these local explanations is that you now locally approximate the decision function in this region and around the patient by something simple。

😊。

![](img/721083320adbdaed1f33a52bdfb9c1fc_33.png)

![](img/721083320adbdaed1f33a52bdfb9c1fc_34.png)

And the idea is that even though globally the function。

 say the decision surface between two classes might be very complicated weekly function。

 but of course locally， even if the function globally is very weakly locally you might be able to approximate it even with a linear function。

😊，Or something very simple and then try to generate an explanation out of this。



![](img/721083320adbdaed1f33a52bdfb9c1fc_36.png)

In one algorithm， that does this， particularly for neural networks and image recognition。

 but it also works more generally is the algorithm lime。😊。

I have the reference a couple of slides later。And here I simply want to explain lime for tabular data。

 tabular means data that lives in RD， but as I said， it has been developed also for images。

But this is sort of the very rough outline， how it works。So it's a local model。

 so you always need to fix the point for which you want to generate an explanation。

 So you have this complicated function F。 It makes a prediction on this particular input value x。😊。

And now you want to explain what this function F does。

Now what you are going to do is you as sample other data points locally around this function x around this point x and you evaluate what the function would like what your model would predict for these particular data points。

😊，Then you approximate this complicated function by linear function。

And now what you do is you identify the most prominent coordinates in this model。

 like the most prominent coefficients I think I should have said in this model and then you say those are the ones。

That explain the behavior at this particular point part of the space best。

 and then you use those highest like the features that get these highest coefficients as your explanation。

The important and cool thing about this approach is that you don't need to know anything about the learning algorithm so it' is completely irrelevant whether the function has been generated by a neural network or by a support vector machine or by something completely different you just need to be able to always evaluate what is the result of your function on some particular input point and you need to be able to sample points locally these are the two most important ingredients。

😊，And here' is a particular illustration。 So assume we have。



![](img/721083320adbdaed1f33a52bdfb9c1fc_38.png)

We have a complicated so this is a one dimension example of course it's a toy example simply to illustrate what's going on so you have one dimensional data points。

 you have this blue function is maybe this regression function that you would like to it's supposed to be a complicated function that you' are trying to explain and you want to explain it at this particular data point that is in red。



![](img/721083320adbdaed1f33a52bdfb9c1fc_40.png)

![](img/721083320adbdaed1f33a52bdfb9c1fc_41.png)

Now you approximate the blue function by this red linear function and then you use the coefficients that have the highest weight of this linear function to explain what goes on at this red data point。



![](img/721083320adbdaed1f33a52bdfb9c1fc_43.png)

![](img/721083320adbdaed1f33a52bdfb9c1fc_44.png)

So a postdoc of mine has recently published a paper this year at AS Stas where he essentially showed that these coordinates。

 I mean he proved theoretically， tried to analyze this algorithm which I mean the way I presented it here it sounds very。

 very simple but there are many complicated spinningning steps and so on so it's not as straightforward as it looks here he analyzed it and found that the coordinates that I mean that this model。

😊。

![](img/721083320adbdaed1f33a52bdfb9c1fc_46.png)

![](img/721083320adbdaed1f33a52bdfb9c1fc_47.png)

That the explanation gives you back are typically the ones that contribute most to the gradient that F。



![](img/721083320adbdaed1f33a52bdfb9c1fc_49.png)

At this particular point， and this somehow makes sense because you would think like if you fit a linear model。

At a particular function， then you would of course， hope to find that I mean。

 the weights that have the largest weights would be the ones that correspond to the steepest direction。

 which is the gradient。😊，But of course this is completely nonobous because this algorithm has been designed in some algorithmic experimental fashion and the fact that it really relates back to the gradient and prove that you can prove that something useful comes out。

 this is sort of what happened in this paper。The reference is somewhere at the bottom。



![](img/721083320adbdaed1f33a52bdfb9c1fc_51.png)

S to give you an insight of what is the the， the most prominent application domain for for Lyme。

 This is image classification by neural network。 So typically what Lyme would do is。

You have an image and maybe you have an image classification algorithm trained by neural network。

 for example， and it would say here's a strawberry and here's a turtle。😊。

And now what Lyme does to generate these explanations。

 it first of all constructs what is called super pixels。

 so these are slightly larger regions in your space。😊。



![](img/721083320adbdaed1f33a52bdfb9c1fc_53.png)

And now you want to find out which of these super pixels is most relevant for the output label that you produce。

 so for example， in this particular image if they recognize if the system says there's a strawberry。

 then it's probably these kind of pixels here around the strawberry that are important for this decision and not so much the pixel here or pixels somewhere here in the corner。



![](img/721083320adbdaed1f33a52bdfb9c1fc_55.png)

![](img/721083320adbdaed1f33a52bdfb9c1fc_56.png)

![](img/721083320adbdaed1f33a52bdfb9c1fc_57.png)

And so the kind of thing that the output you can produce is something like here you have the original image and then your classification system says for example。

 turtle orterrapin， I think that's a particular kind of turtle。😊。



![](img/721083320adbdaed1f33a52bdfb9c1fc_59.png)

And then you say， why do you think this is a turtle and then the image gives you back the lime algorithm gives you back these kind of super pixels which show a part of the turtle orter the same here for strawberry so。

😊。

![](img/721083320adbdaed1f33a52bdfb9c1fc_61.png)

The system gives you back these pixels that correspond super pixels that roughly correspond to the strawberry。

 And then as a human， you cannot look like look at this image and say guess that makes sense。



![](img/721083320adbdaed1f33a52bdfb9c1fc_63.png)

Now you can also consider this in a medical example if you have a body scan of a certain person or a certain organ or so。

 and maybe the system says or there might be a cancer in this piece of your body and then the doctor says oh well really I didn't see it and then you can ask the system that the doctor can say show me why do you think there is a cancer and then the system would outline a particular part of the image and then the doctor can really look at it closely and can say。

 oh yes， the system is right， there might indeed be a cancer a tumorour or you could say no this is not a tumor。

 I know this is something else and we can forget about it。😊。



![](img/721083320adbdaed1f33a52bdfb9c1fc_65.png)

![](img/721083320adbdaed1f33a52bdfb9c1fc_66.png)

![](img/721083320adbdaed1f33a52bdfb9c1fc_67.png)

![](img/721083320adbdaed1f33a52bdfb9c1fc_68.png)

![](img/721083320adbdaed1f33a52bdfb9c1fc_69.png)

![](img/721083320adbdaed1f33a52bdfb9c1fc_70.png)

![](img/721083320adbdaed1f33a52bdfb9c1fc_71.png)

So this was all I wanted to tell you about explainable machine learning there's a lot of research going on and we have even some colleagues who have devoted most of their time of research。

😊。

![](img/721083320adbdaed1f33a52bdfb9c1fc_73.png)

![](img/721083320adbdaed1f33a52bdfb9c1fc_74.png)

In tubing in two explainable machine learning， it's really an important field of research and both for bringing a eye to society and explaining really the decisions in applications that have impact on society or in human lives also。

😊。

![](img/721083320adbdaed1f33a52bdfb9c1fc_76.png)

But also， it comes from the data protection law that companies need to provide these kind of explanations。

And therefore to be able to do that。

![](img/721083320adbdaed1f33a52bdfb9c1fc_78.png)

There's lots of research going on in machine learning。

 but interestingly this is also a field of research that again connects back to ethics and philosophy of science because in philosophy of science it's a very important and very basic question that's been discussed since hundreds of years。

 what is an explanation and what does it mean to explain and other different types of explanations and what do I need in order to be able to explain to somebody else and so on and there's lots of interesting connections from which we as machine learners can also draw some insights。

😊。

![](img/721083320adbdaed1f33a52bdfb9c1fc_80.png)

![](img/721083320adbdaed1f33a52bdfb9c1fc_81.png)

![](img/721083320adbdaed1f33a52bdfb9c1fc_82.png)

![](img/721083320adbdaed1f33a52bdfb9c1fc_83.png)

When we are going to design new algorithms or new methods to provide explainable machine learning in general I think this is a field that is still widely open。

 I mean we have seen there there are a couple of approaches but there's definitely room for more and I think this is an important field that will still see a lot of developments in the future。

😊。

![](img/721083320adbdaed1f33a52bdfb9c1fc_85.png)

![](img/721083320adbdaed1f33a52bdfb9c1fc_86.png)