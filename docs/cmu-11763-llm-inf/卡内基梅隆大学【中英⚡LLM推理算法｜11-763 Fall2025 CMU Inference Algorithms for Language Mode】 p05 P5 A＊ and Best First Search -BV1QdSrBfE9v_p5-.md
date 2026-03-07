# 卡内基梅隆大学【中英⚡LLM推理算法｜11-763 Fall2025 CMU Inference Algorithms for Language Mode】 p05 P5 A＊ and Best First Search -BV1QdSrBfE9v_p5-

Okay so welcome back everyone I will be talking about best first search for language models and one thing before I do that that I'd like to talk about a little bit is just kind of in general on the way over here I was talking to Amanda about like the relative importance of the stuff we're talking about now compared to like the stuff that's used more frequently now so like to give an example。

 the stuff that's used frequently now is like sampling greedy search maybe to a lesser extent some beam search and then the stuff that we're doing that I'm going to talk about today is probably use the least out of all the stuff we have。

 but I actually think there's a reason for that， which is。



![](img/b90f00e39198c6caa40bd41d0044406d_1.png)

![](img/b90f00e39198c6caa40bd41d0044406d_2.png)

![](img/b90f00e39198c6caa40bd41d0044406d_3.png)

![](img/b90f00e39198c6caa40bd41d0044406d_4.png)

![](img/b90f00e39198c6caa40bd41d0044406d_5.png)

![](img/b90f00e39198c6caa40bd41d0044406d_6.png)

![](img/b90f00e39198c6caa40bd41d0044406d_7.png)

有。

![](img/b90f00e39198c6caa40bd41d0044406d_9.png)

Yeah had kind of like a G。GP， like one。To things like this， these were like。



![](img/b90f00e39198c6caa40bd41d0044406d_11.png)

I don't know， really。

![](img/b90f00e39198c6caa40bd41d0044406d_13.png)

Really broken models。 And so they had lots of problems。

 And so if you like tried to find the highest probability output from them。

 they would give you things that repeated over and over again。

 so like you did greedy search or you did the beam search。

 it would give you like an output of length of zero and that would be completely useless so in order to fix this basically what we did is we went in and we like broke inference。

 So we used sampling strategies where we didn't sample like directly from the distribution we didn't use greedy search。

 we didn't use all of these other things。 And so。

![](img/b90f00e39198c6caa40bd41d0044406d_15.png)

![](img/b90f00e39198c6caa40bd41d0044406d_16.png)

![](img/b90f00e39198c6caa40bd41d0044406d_17.png)

![](img/b90f00e39198c6caa40bd41d0044406d_18.png)

![](img/b90f00e39198c6caa40bd41d0044406d_19.png)

![](img/b90f00e39198c6caa40bd41d0044406d_20.png)

![](img/b90f00e39198c6caa40bd41d0044406d_21.png)

This was kind of like the era of let's this was the era of like break。



![](img/b90f00e39198c6caa40bd41d0044406d_23.png)

Break search。To get better results。Now we get to like GP。

3 and four we're starting to get like much better models like three still wasn't good enough like four was u was kind of like getting to be good enough。



![](img/b90f00e39198c6caa40bd41d0044406d_25.png)

Where it's like， okay now search actually works， so let's just do greed let's just do greedy outputs。



![](img/b90f00e39198c6caa40bd41d0044406d_27.png)

![](img/b90f00e39198c6caa40bd41d0044406d_28.png)

嗯。And then we also have models like。

![](img/b90f00e39198c6caa40bd41d0044406d_30.png)

You know， I'll just stick with the open AI models， so I'll say like 001 to 04。嗯。



![](img/b90f00e39198c6caa40bd41d0044406d_32.png)

Now open AI like doesn't even allow you to do things other than temperature equals to one。

 it like forces you to sample from the model and so this is like they give you a no release。



![](img/b90f00e39198c6caa40bd41d0044406d_34.png)

![](img/b90f00e39198c6caa40bd41d0044406d_35.png)

I think a lot of other people have just spend following this and just sampling from the model of temperature wanted and so the idea is like okay。

We will。Just sample directly from the model's distribution because the model has been trained to be reasonably good when we sample directly from the distribution。



![](img/b90f00e39198c6caa40bd41d0044406d_37.png)

![](img/b90f00e39198c6caa40bd41d0044406d_38.png)

But。Like greed research actually kind of works with like our best models and it actually works better than sampling with temperature one。

 And so that kind of makes me think that it's like now is the time to go back to like actually searching better and like one way that people search better is they you know do really long rollouts of reasoning models and and sample lots of outputs and things like this and you know maybe maybe that's good we're going to be talking a lot about that but maybe also we really want to be looking for the things where we get the highest model score and so maybe maybe now is the time to reconsider these methods that search efficiently for the things that have very high model scores So that's kind of on a high level my thinking about this before we go into the details。

😊。

![](img/b90f00e39198c6caa40bd41d0044406d_40.png)

![](img/b90f00e39198c6caa40bd41d0044406d_41.png)

![](img/b90f00e39198c6caa40bd41d0044406d_42.png)

![](img/b90f00e39198c6caa40bd41d0044406d_43.png)

![](img/b90f00e39198c6caa40bd41d0044406d_44.png)

![](img/b90f00e39198c6caa40bd41d0044406d_45.png)

![](img/b90f00e39198c6caa40bd41d0044406d_46.png)

![](img/b90f00e39198c6caa40bd41d0044406d_47.png)

Any any。Comments， sir thoughts。Okay， cool。

![](img/b90f00e39198c6caa40bd41d0044406d_49.png)

嗯。😊，So。Just to go back to what we were talking about before last time we talked about like things like greedy search and beam search and to give a kind of outline。

 let's see if I can make that bigger Okay， there we go So greedy search basically selected the highest probability token at each set。



![](img/b90f00e39198c6caa40bd41d0044406d_51.png)

![](img/b90f00e39198c6caa40bd41d0044406d_52.png)

![](img/b90f00e39198c6caa40bd41d0044406d_53.png)

![](img/b90f00e39198c6caa40bd41d0044406d_54.png)

And it's， you know very fast， but it's myopic， it can make very bad local decisions when a better global decision would be possible。



![](img/b90f00e39198c6caa40bd41d0044406d_56.png)

![](img/b90f00e39198c6caa40bd41d0044406d_57.png)

No backtracking of any variety is possible， no consideration in multiple hypotheses。



![](img/b90f00e39198c6caa40bd41d0044406d_59.png)

In contrast to this beam search maintained top K hypotheses。

 explored multiple pest site simultaneouslyly and gave。



![](img/b90f00e39198c6caa40bd41d0044406d_61.png)

![](img/b90f00e39198c6caa40bd41d0044406d_62.png)

If you have a good model， it will give you better quality than research。

 what's just to make sure that everybody's awake and paying attention。

 what's the relationship between these two？Yeah， you be with one。Yeah， exactly。

 So beam search with a beam width of one is search。



![](img/b90f00e39198c6caa40bd41d0044406d_64.png)

Cool， so。I'm going to talk about search spaces as graphs here because a lot of the algorithms that I will be talking about today were originally created for search over graphs。



![](img/b90f00e39198c6caa40bd41d0044406d_66.png)

And we can represent it specifically as a weighted finite state automaton。

 and how many people have done this in some class？

![](img/b90f00e39198c6caa40bd41d0044406d_68.png)

It's like 10 to 20% of people Okay that's great this is another place where I get to feel the 2025 because this used to be like a staple of computer science curriculum。

 but it's not it more so Okay， cool so basically S is a finite set of states and so these are all the states that we have in our graph。

😊。

![](img/b90f00e39198c6caa40bd41d0044406d_70.png)

![](img/b90f00e39198c6caa40bd41d0044406d_71.png)

Sigma is a finite alphabet， so alphabet is another term for vocabulary。

 so we could also say it's a vocabulary of our language model。



![](img/b90f00e39198c6caa40bd41d0044406d_73.png)

![](img/b90f00e39198c6caa40bd41d0044406d_74.png)

We have transitions where basically you take in a state。

 you take a element for the vocabulary and transition to a next state， a zero is the initial state。

 we also have a sync state where things things end or a set of sync states。

 yeah a set of final states and we call that F。

![](img/b90f00e39198c6caa40bd41d0044406d_76.png)

![](img/b90f00e39198c6caa40bd41d0044406d_77.png)

![](img/b90f00e39198c6caa40bd41d0044406d_78.png)

![](img/b90f00e39198c6caa40bd41d0044406d_79.png)

![](img/b90f00e39198c6caa40bd41d0044406d_80.png)

And W is a weight where we assign real weights to transitions， and in particular。

 things are a lot easier if you limit yourselves to purely positive or purely negative outputs here。



![](img/b90f00e39198c6caa40bd41d0044406d_82.png)

![](img/b90f00e39198c6caa40bd41d0044406d_83.png)

So this is an example graph maybe a little bit small。 Okay， there we go。

 And so here S0 is the initial state and or I guess you could call it S 10 is the final state and then we have。



![](img/b90f00e39198c6caa40bd41d0044406d_85.png)

![](img/b90f00e39198c6caa40bd41d0044406d_86.png)

Essentially elements of the vocabulary here vocabulary is ABC and of sentence。

 and we have each one of them is weighted。

![](img/b90f00e39198c6caa40bd41d0044406d_88.png)

So here， each one of them is weighted with a probability。



![](img/b90f00e39198c6caa40bd41d0044406d_90.png)

And because this is a probability， all of these need to add to one coming out of the like node here。

Oh good。Okay， cool。So there's a number of different ways to express edge weights。



![](img/b90f00e39198c6caa40bd41d0044406d_92.png)

And I'll just talk about these kind of in the abstract。 But like if you're interested in math。

 there's actually a concept called a semi ring that allows you to do all kinds of crazy things to express edge weights。

 So if you're bored of hearing me talk， you can look up what a semi ring is and try to figure out what's going on here。

 But basically some of the things you define when you want to define edge weights or you define the range in which the edge weight is valid。

 So this for a probability， this would be between 0 and one。😊。



![](img/b90f00e39198c6caa40bd41d0044406d_94.png)

![](img/b90f00e39198c6caa40bd41d0044406d_95.png)

![](img/b90f00e39198c6caa40bd41d0044406d_96.png)

![](img/b90f00e39198c6caa40bd41d0044406d_97.png)

![](img/b90f00e39198c6caa40bd41d0044406d_98.png)

嗯。Then you define a addition function。

![](img/b90f00e39198c6caa40bd41d0044406d_100.png)

What不 said。You define an addition function and actually when you define a summary ring。

 the addition function is written like this。And what that means is it's abstracted away addition and it's what happens when you combine together two edges。

 So in the case of a probability， this function is is a multiplication function or no。

 actually sorry。

![](img/b90f00e39198c6caa40bd41d0044406d_102.png)

![](img/b90f00e39198c6caa40bd41d0044406d_103.png)

This is like abstracted away so this is aplication a multiplication function。

 and so here you multiply weights together。The way you do the best path is you take the Argaacs。



![](img/b90f00e39198c6caa40bd41d0044406d_105.png)

And the example of an example path would be like 0。5 times 0。3 times 0。2。



![](img/b90f00e39198c6caa40bd41d0044406d_107.png)

Another thing we can express is log probabilities and so the range for log probabilities is obviously minus infinity to zero。

 we add the weights together when we're doing path scoring， the best path would be the Arac。



![](img/b90f00e39198c6caa40bd41d0044406d_109.png)

![](img/b90f00e39198c6caa40bd41d0044406d_110.png)

![](img/b90f00e39198c6caa40bd41d0044406d_111.png)

![](img/b90f00e39198c6caa40bd41d0044406d_112.png)