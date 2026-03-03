# Vizuara【中英⚡AI研究员训练营｜AI Researcher Bootcamp】 p13 P13 Can Language Models reason？ [BV1qi4VzJEPd_p13]

🎼Yeah。🎼Hello， everyone。My name is Dr。 Richard Duneker and I'm a PhD graduate from Purdue University。



![](img/79cb9c9f4c5da762ccd16e44e893f75e_1.png)

So。In this in this session， I want to。Just give a brief overview of a recent paper which I have been reading and the title of the paper is star which is self taught reasoner bootstrapping reasoning with reasoning。

So I was mainly interested in this paper because。I was seeing one of the interviews of Ervins Reniassen。

 who is the CEO of Perplexity。And the discussion was regarding。

How do we know whether Jd GPT or any language model？

Is coming to the answer with the right series of steps。

So generally what happens is that if we give a prompt to chat GT。

Pro charge GPT gives an answer to that prompt， however。

 we do not know what is the thought process behind that promptm。So what I mean by this is that。

 let's say。You have。Given a prompt。And you get an answer。Now啊。

If Cha GPT is giving an answer by truly understanding the logical thought process from the prompt to the answer。

 then that is fine， but what if the answer that you are getting is。Just based on a。

Sort of a mapping from the prompt to the answer without really understanding what's happening in the process in between。

And if if that' is the case， then we cannot say that language models are intelligent because they are going from point a to point B without really understanding the series of thoughts in between。

And that is how humans tend to think if let's say we are asked a question and we give an answer to that question。

It is based on a。Jin of thought， right， and。We are not sure whether Cha GT is giving an answer that is based on that chain of thought or。

It's randomly giving us an answer without really understanding what's happening。呃。

In the process of thinking so the question that people are trying to grapple with is that does Cha GPT really have intelligence or its simply a mapping that is being done from an input to the output。

And that is what mainly attracted me to this paper because what they have done here is that。

They have proposed a technique。To iteratively use a small number of rational examples and a large set of data without rationals。

To。Perform more complex reasoning。So what does that mean so they have actually mentioned this very nicely in this diagram？

So let's say we give a question to the language model。And。The language model will give。

A rational along with the answer。 So this is the answer that is fine。

 but there is a rational which comes along with it。For example， if we ask the question。

 what can be used to carry a small dog？And then we give four options like these。

So what we have over here is that we have a rational which is mentioned in red over here。

 the rational says something like the answer must be something that can be used to carry a small dog。

Baskets are designed to hold things， therefore the answer is basket， which is option number B。

So we have the answer， which is option number B that is correct because the basket is indeed used to carry a small dog。

But there is some rationale behind it。Allright， and。

That is what we are trying to really understand here。

 we are trying to sense whether Cha GT is able to give an answer along with the rationale and not just the answer associated with it。

So okay， so what they have done here is that let's say you ask a question and then the language model gives you a rationale along with the answer。

There are two possibilities， right， if the answer is correct or the answer is wrong。

If the answer is correct， then。The question along with the rational and the answer is again fed back to the model to find unit。

If the answer is wrong， then what happens is that。The language model is given the correct answer and then it backtracks to find out the actual rationale behind it。

And then that information is again used for the training。So for example。

 if we ask this question and then。The model answers wrong， let's say it answers Doc show。So。

 we know that it is a wrong answer， so what we do here is that we tell the language model that the correct answer is basket。

And then it backtracks the rationale from it and then we again give that as as an input to the language model and then fine tune in the training database on it。

So。That' is why they say this technique relies on a simple loop。

Generate rationals to answer many questions prompted with a few rational examples。

If the generated answer is wrong， then try again to generate a rationale given the correct answer。

Findine tune in all rationals and ultimately yield the correct answers and repeat。

So through this process， what they are trying to do is that。

They are trying to impart reasoning capabilities。Two language models。

And reasoning is one area of intelligence which human possess， but the question is that can。

Language models actually reason。And can language models reason。

And is this is the question that well be trying to answer as a part of this paper。

So just to give you a more。Practical understanding of what do we mean by rationals。

 there are a bunch of examples which。They have given towards the end of this paper。

So let's look at some of these examples。Okay， so。Let's say there is a question that we ask。

What might。What might someone gain。From learning about science。And the answer choices are， let's say。

 headache。Seeing things differently increase knowledge， accidents and appreciation of nature。

 so I would tend to answer increased knowledge。And okay。

 so this is what the language model does the language model gives us the correct answer it does say the answer is C。

But look at the rationale that it generated says that。

The answer must be something that someone would get from learning about science。Which is true。

 learning about science would increase knowledge。And therefore， the answer is increase knowledge。

So this is good， I mean， I'm really satisfied with this。With this kind of a rationale。

 now if you look at the second question。The Christian rock band was on a large stage。

 The singer's foot were caught on a wire， and he had a small v。So we know that the answer is stumble。

 he had a small stumble now let's see how the language model got to it。

The answer must be something that would cause the singer to stumble。 So you can see that the。

The answer is directly included in the rational， which which will never be the case when I am trying to rational。

 I can say that okay， the singer's foot got caught on a wire。So。

 it should be something that indicates that the singer is falling。

 therefore the answer is option number D。But here， what's happening is that the。

The answer is coming in the rational itself。Which means that you don't really understand what's happening in the background。

And there are a lot of examples which they have given。嗯。

And here is another example where it doesn't really understand what what's happening。So let me， okay。

 so let's let's take this example， a person hands hurts。After hitting the bottle。

 what might happen to the bottle and the answer choices are alcoholism breaking nausea and and antique。

 So what might happen to the bottle， we know that the answer is breaking。

 So it says the answer must be something that happens to the bottle。 The bottle is broken。 Therefore。

 the answer is B。And here， okay， it has got to the right answer but。

The ratio should be something like when the bottle。A person hand hurts after hitting the bottle。

 so it means that the impact of the hand in the bottle would cause the bottle to break and therefore the bottle is broken so here also it is kind of okay but it is still not completely convincing。

Okay， and there are there are many examples here where they have given how。



![](img/79cb9c9f4c5da762ccd16e44e893f75e_3.png)

Language models。Give prompt。