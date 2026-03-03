# YannicKilcher【中英⚡AI经典论文领读(全203篇)(下)｜Papers Explained】 p67 P167 预测递归序列背后的规则——深度符号回归方法（附作者访谈） [BV1j8x5zJEvx_p67]

Hello there。 Today， we'll look at deep symbolic regression for recurrent sequences by Stean Dscoli。

 The Alexandcaeni Giom Lomp and Fransoa Charton。 This is another paper where the main part will be an interview with the first author。

 Stefan and I'll just briefly introduce the paper right here for 10 isch minutes or so。

 So if you want to just skip to the interview。 feel free。

 We'll go over the paper just so that you know what's going on。

 And there is also an interactive demo online where you can try it out。

 And it's a good place to start at what this paper is trying to do。 So in this paper。

 The authors care about symbolic regression to number sequences。

 They have a model for integer and float number sequences。 In this case。

 this is an example for an integer sequence。 So you can enter any sequence right here。

 you can see that the sequence that is already entered is the Fibonacci。😊。



![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_1.png)

![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_2.png)

![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_3.png)

![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_4.png)

![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_5.png)

Sequence， and you enter as many terms as you want。 obviously， the more you enter。

 the more success probability the model is going to have。

 And what the model will do down here is it will predict an expression。

 You can see it correctly predicts the expression for the Fibonacci sequence。

 saying that the current element is the last plus the last last element。

 and it will predict the next terms for you， and it will extrapolate the sequence that you've input。

 So you can do any， any that you want。 I'm going to go one。



![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_7.png)

I'm， I'm very bad at coming up with stuff on the spot 2，1，3，1，4。1，5， let's see if it can get that。

 So as soon as you exit from the model。

![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_9.png)

It will。 yeah， look at that。 So the caution， which is not even sure what that operation is， but。嗯。

ASo it divides， it divides the sum of the last elements， maybe。



![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_11.png)

By the last element。figured it out somehow。 It is It is not really good at like if conditions。

 And this is one thing we're going to talk about in the interview。

 But you can see it correctly predicts the next sequence right here。 So give that a tried。

 This is this pinpoint exactly what this paper does。

 It does symbolic regression for recurrent sequences。

 recurret sequences are sequences of numbers that can be somehow expressed as a logical rule as a function of the last elements of the sequence。

 There is like most sequences can be expressed like this。 For example。

 they give a bunch of examples right here。1，2，71，2，4，7，1116。

 So you can see that it's always sort of plus 1 plus 2 plus 3 plus 4 plus 5 and so on。

 or this function right here。 These are simply the squares。 So the recurrence relation。

 actually isn't a recurrence relation at all。 But it is also a special case。😊。



![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_13.png)

![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_14.png)

![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_15.png)

![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_16.png)

![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_17.png)

Of a recurrence relation or this formula right here， it can get very complicated。

 They have a bunch of examples right here of recurrence relations。 As you can see。

 they can go pretty complicated to express something like the final digit of n times n 1 divide by 2 or the final two digits of two to the n or some maximum or anything like this。

 So the goal of the model is that you input a sequence like this。

 And then the model will output this recurrence relation。

 It will not output the numbers directly of the sequence of the following numbers。

 That's what they would call a numeric model， and they also train one as a baseline。

 But the model would actually output exactly the formula itself。

 And then you can use the formula to produce the next elements。 Now。

 the good thing is we've all seen what happens if you train a numeric model on like a bunch of data points。

 let's say。

![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_19.png)

![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_20.png)

![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_21.png)

![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_22.png)

![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_23.png)

These are your input data points。 You train a numeric model on that it will perform pretty well on the data you give it。

 But as soon as you go like outside of that data， as soon as you extrapolate too much away from the support base of the training data without very strong inductive biases。

 it will sort of。Do whatever you can't really predict it。

 what it will do where there is no training data。 That's why also deep learning relies on on lots of training data in covering a lot of the input space。

 whether that's called extra interpolation or whatnot。 will leave it at that。

 But if you have a symbolic regression and the symbolic regression actually predicts the correct formula to match this sequence right here。

 like saying this is just a sine wave。 then you can extrapolate indefinitely right。

 and because you have the correct symbolic formula， you'll be right you know in all places。

 So potentially this is very very strong method for certain types of problems。

 This paper consider this a sequence to sequence problem。

 So it considers transformer stack and this is， I guess。

 along the classic transformer stack of you have an encoder and a decoder stack the encoder stack gets fed with the input sequence as numbers。



![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_25.png)

![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_26.png)

![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_27.png)

So here1，1，2，3，5 and so on that is the input sequence。

 it is fixed and then the output sequence is the formula that you want to predict and they predict the formula in reverse Po notation of the prefix tree of the formula so they have an example down here for example。

 the cosine of 3 x can be expressed as this as cosine of multiplying3 by x so you would you would sort of loaded onto the stack and then work your way down the stack in in this reverse reverse Po notation measure so that would be cosine of mo of3。



![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_29.png)

![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_30.png)

Of X or whatever that formula is。 And then you try to train your transformer to auto aggressively predict first the first token without seeing those tokens。

 And then once you have the first token， you w to predict the second token given the input and the first token。

 there is like theres multi attention in here， like。There is cross attention over here。

 There is Excel attention in here as well。 your regular transformer stack。

 So this is classic sequence to sequence problem。 The only question is how do you obviously encode the input and the output。

 the output we've already discussed and they have a very detailed description of how they produce the data。

 So what they do is they take a bunch of operators。

 you can see them in this table and they make random formulas from those operators。

 They have a bunch of constraints on these formulas。

 but essentially they make random a data set out of just random formulas。 So first of all。

 they sample the number of operators between one and a maximum number In this case， that would be 10。

10 is the maximum number of operators and then they build a unary binary tree with that many nodes So for example。

 they would sample two operators right here like or。



![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_32.png)

![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_33.png)

![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_34.png)

![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_35.png)

3，A relo， a sub and a mod。 And then they would build a unary binary tree。 So Relu。

Then that is a urary thing right So it only has one input。 So sub that's a binary operation。

 So it needs two inputs here， let's say mod that again needs two inputs。

 So the second step is to sample the nodes of the tree from the list of operators that's what we've already done。

 we've combined steps 1 and2 sample the recurrence degree between one and Dmax。 Dmax is6。

 So were maximum allowed to look back six elements into the past。 This is kind of a Markov condition。

 You can say your recurrence relation can only look back6 items。

 That's kind of a limit but most sequences that humans could come up with。

 don't refer back to the seventh last element right There is usually a way to express it in forms of either the current index or the last few like three or four elements at max。

 then they sample。

![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_37.png)

![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_38.png)

![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_39.png)

Leavs of the tree so the leaves of the tree are either a constant with probability P constant these all these probabilities are 1 third and they stress very much that hyperparameter settings are not very crucial in this way。

 they sample the leaves of the tree， so either it is a constant or the current index or one of the previous terms of the sequence。



![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_41.png)

So let's do that， so we'll say here we sample the previous term， which is U n minus2。

 here we sample the index， which is n， and here we sample a constant which is 3。

 so that would result in the formula relu of U n minus2 minus and then n mod 3。



![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_43.png)

That would be the formula for this。 Then they need to sample initial terms of the sequence。

 So in with the formula， you also need to decide， you know， how the initial terms， the initial terms。

 since we go back two elements， We need probably at least two elements at the beginning of the sequence。

 So let's call that 1 and 2。 That's we also need to sample that from a distribution。

 You can see here。 That's just a uniform distribution from negative 10 to 10。



![](img/0f7d3b7ee0bbf653bdc09198eab20e1f_45.png)

And then what's the last？