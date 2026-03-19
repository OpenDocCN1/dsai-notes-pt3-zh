# 优达学城（Udacity）：无人驾驶汽车纳米学位项目-十位大牛亲授自动驾驶技术，硅谷前沿科技（计算机视觉⧸车道识别⧸感知控制⧸人工智能⧸谷歌） p06 6. Part 02-Module 01-Lesson 04_Conditional Probability [BV1Vd4y1r7QG_p6]

Let's talk about conditional probabilities。 So sounds very cryptic。

 but conditional pro is the basic mechanism of which a self-diving car can take some sensor data and infer something else。

 like， for example， it could see a picture of a tree and inferor or I'm about to crash to the language that is needed in mathematics to make this inference from a sensor measurement to some internal belief is called conditional probability。

 so let's dive in。😊，As Sebastian said， this termconal probability sounds very cryptic。

But before we jump into the math behind conditional probability。

 I want to show you that you already understand the concept intuitively to do that。

 I'm going to ask you two questions well really one question twice。First。

 whatever town or city you're in right now， I want you to come up with your best guess of the probability that exactly one year from now。

 it will be cloudy outside。All right， you've made a probabilistic estimate about the weather one year from now。

Now， I'd like you to look out of a window。Go ahead。

 pause this video and go look out the nearest window I can wait。Did you do it？Great。😊，Now。

 I want you to make the same estimate you made before。But this time。

 I want you to estimate what is the probability that wherever you are now。

 it will be cloudy one minute from now。I'm going to guess you felt much more confident in that second estimate。

 so you probably estimate a probability that's very close to0 or1。

 depending on whether it is not or is cloudy right now。

 and that's because cloudiness now and cloudiness one minute for now are not independent events When you looked at the window to evaluate the cloudiness you were in effect taking a sensor measurement of your surroundings and you use that data to inform your probabilistic estimate。

And that is all that conditional probability is taking advantage of what we know to make better estimates about what we don't in the rest of this lesson。

 you'll learn how to formalize the intuition mathematically。In real life。Things depend on each other。

 Sa you can be born。

![](img/a93c27f221645a0ab9ba264ca4e04e53_1.png)

![](img/a93c27f221645a0ab9ba264ca4e04e53_2.png)

Smart or dumb。 And for the sake of simplicity， let's assume。Whether you're smarter dumb， is just。

Nature's flip of a coin。Now， whether you become a professor at Stanford is not entirely independent。

 I would argue， become a professor at Stanford is generally not very likely。

 So probability might be 0。001， but it also depends on whether you are born smart or dumb。

 if you are born smart， the probability might be larger， Whereas if you are born dumb。

 The probability might be much， much smaller。No， that's just an example。

 But you can think of them as。Two consecutive coin flips。The first is whether you are born。

 smarter them。 The second is whether you get a job of a certain type。

 And now if we think of them as two coin flips， they are not independent anymore。

 So whereas in our last unit， we assume that the coin flips were independent。

 That is the outcome of the first didn't affect the outcome of the second from now on。

 were going to study the more interesting case。 but the outcome of the first does impact the outcome of the second。

 And to do so， we need to introduce more variables to express these cases。



![](img/a93c27f221645a0ab9ba264ca4e04e53_4.png)

![](img/a93c27f221645a0ab9ba264ca4e04e53_5.png)

To do so， let's study a medical example。 Suppose we have a patient in a hospital who might suffer from a medical condition like cancer and say the probability of having this cancer is 0。

1。 That means you can tell me what's the probability of being cancer free。



![](img/a93c27f221645a0ab9ba264ca4e04e53_7.png)

And the answer is 0。9， which is1 minus thick cancer。Of course， in reality。

 we don't know whether a person suffers cancer。But we can run a test like a blood test。

 And the outcome of the blood test may be positive or negative。 but like any good test。

 it tells me something about the thing I really care about， whether the person is cancerous or not。

 So let's say。If the person has the cancer， the test comes up positive with the probability of 0。9。

 And that implies if the person has cancer， the negative outcome would have a 0。1 probability。

 And that's because these two things have to add up to one。

 I've just given you a fairly complicated notation that says。

The outcome of the test depends on whether the person has cancer or not。

 That is more complicated than everything we else we talked about so far。

We call this thing over here a conditional。Probability and the way to understand this is through this very funny notation。

 There's a bar in the middle。 and the bar says， what's the probability of the stuff on the left。

Given that we assume the stuff on the right is actually the case。 Now， in reality。

 we don't know whether the person has cancer or not。 and in a later unit。

We're going a reason about whether the person has cancer given a certain data set。 But for now。

 we assume we have Godlike capabilities。 We can tell with absolute certainty whether the person has cancer and we can determine what the outcome of the test is。

 This is a test that isn't exactly deterministic。 It makes mistakes。

 but it only makes a mistake in 10% of the cases as illustrated by 0。1 down here。 Now。

 it turns out I haven't fully specified the test。 The same test。

Might also be applied to a situation where the person does not have cancer。

 So this little thing over here is my shortcut of not having cancer。

 And now let me say the probability of the test， giving me a positive result a false positive result when there is no cancer。

 is 0。2。 You can now tell me。What's the probability of a negative outcome in case we know for a fact the person doesn't have cancer。

So please tell me。And the answer is 0。8， as I'm sure you noticed in the case where there is cancer。

 the possible test outcomes add up to 1， in the case where there isn't cancer。

 the possible test outcomes add up to1， so 1 minus 0。2 equals 0。8。Look at this。

 This is very non trivialvi， but armed with this。We can now build up the tooth table for all the cases of the two different variables。

 cancer and non cancercer and positive and negative test outcome。

 S me right on cancer and test and let me go through the different possibilities He could of cancer or not。

 and the test may come up positive。Or negative。 So please give me the probability。

Of the combination of those for the very first one。 And as a hint。

 it's kind of the same as before We we multiply two things。

 but you have to find the right things to multiply in this table over here。

This is not an easy question。And the answer is probability of cancer is 0。1。

 probability of tests being positive given that we have cancer。Is the one over here， 0。9。

 multiplying those two together gives us 0。09。Moving on to the next case。

 But I think the probability is that the person does have cancer， but the test comes of negative。

 What's the combined probability of these two cases。And once again。

 we multiply the corresponding numbers over here on the right side， 0。

1 for having cancer times the probability of getting a negative result conditioned on having cancer。

 and that is 0。1 times 0。1， which is 0。01。Moving on to the next case。

 What do you think the answer is。And here the answer is 0。

18 by multiplying the probability of not having cancer， which is 0。9。

 with the probability getting a positive test result for a non cancercer patient， 0。2， multiplying 0。

9 with 0。2 gives me 0。18。And let's just quickly do the final one， which is the most likely one。

And here we get 0。72。Which is the product of not having cancer in the first place，0。

9 in the probability of getting a negative test result under the condition of not having cancer。Now。

 quickly do me a favor and add all of those up。 What do you get， And as usual， the answer is one。

 That is， we study in the truth table all possible cases。 When you added the probabilities。

 you should always get the answer of one。Now， let me ask you a really tricky question。

 What's the probability of a positive test result， Can you somehow determine irrespective of whether there are cancer or not。

 What is the probability that we get a positive test result， And the result once again。

 is found in the truth table， which is why this table is so powerful。

 Let's look at where in the truthth table We get a positive test result。

 I would say this is right here。Right here。If we take the corresponding probabilities of 0。09 and 0。

18。And add them up。We it 0。27。And that's the correct answer of for getting a positive result。



![](img/a93c27f221645a0ab9ba264ca4e04e53_9.png)

Putting all of this into mathematicale notation， we are given the probability of having cancer。

 And from that， it follows that we know the probability of not having cancer。



![](img/a93c27f221645a0ab9ba264ca4e04e53_11.png)

![](img/a93c27f221645a0ab9ba264ca4e04e53_12.png)

And we're giving two condition probability that of the test being positive。

 If we have cancer from which we can now predict the probability of the test being negative。



![](img/a93c27f221645a0ab9ba264ca4e04e53_14.png)

![](img/a93c27f221645a0ab9ba264ca4e04e53_15.png)

Of having cancer in the probability of the test being positive can they be cancer free。

 which it can compute the probability of a negative test result in the cancer free case。

 So these things are just easily inferred by the one minus rule。



![](img/a93c27f221645a0ab9ba264ca4e04e53_17.png)

![](img/a93c27f221645a0ab9ba264ca4e04e53_18.png)

They what be really did we complete with the probability of a positive test result。



![](img/a93c27f221645a0ab9ba264ca4e04e53_20.png)

As the sum of a positive test result given cancer times the probability of cancer。

Which is our tooth table entry for the combination of P And C plus the same。

 given we don't have cancer。 Now， this notation is confusing and complicated。

 If we ever dive deeply into probabilityability， know that's called total。Probability。

But it's useful to know。That this is very， very intuitive。 And to further develop intuition。

 let me just give you another exercise of exactly the same type。 This time around， we have a bag。

 And in the bag are two coins。 Co 1 and coin2 And in advance we know that coin1 is fair。

 So P of coin1 coming heads is 0。5， whereas Co2 is loaded。 There is P of coin2 coming up heads is 0。

9 quickly。

![](img/a93c27f221645a0ab9ba264ca4e04e53_22.png)

![](img/a93c27f221645a0ab9ba264ca4e04e53_23.png)

![](img/a93c27f221645a0ab9ba264ca4e04e53_24.png)

![](img/a93c27f221645a0ab9ba264ca4e04e53_25.png)

Give me the following numbers for the probability of coming up tails for coin1 and for coin2。



![](img/a93c27f221645a0ab9ba264ca4e04e53_27.png)

And the answer is 0。5 for1 and 0。14。2， because these things have to add up to 1。



![](img/a93c27f221645a0ab9ba264ca4e04e53_29.png)

For each other coins。So now what happens is I'm going to remove one of the coins from this bag。

 and each coin， Co 1 or coin 2 is being picked with equal probability。 Let me know。

 Flip that coin once。

![](img/a93c27f221645a0ab9ba264ca4e04e53_31.png)

![](img/a93c27f221645a0ab9ba264ca4e04e53_32.png)

And I want you to tell me， what's the probability that this coin， which could be 5% cent chance。

 a fair coin and 5% cent chance a loaded coin。 What's probability that this coin comes up heads。

 Again， this is an exercise in conditional probability。



![](img/a93c27f221645a0ab9ba264ca4e04e53_34.png)

![](img/a93c27f221645a0ab9ba264ca4e04e53_35.png)

![](img/a93c27f221645a0ab9ba264ca4e04e53_36.png)

And let's do the truth table， we have a pick event for by flip event。We can pick coin 1 or coin 2。

 and which with is a 。5 chance for each of the coins。

 and now we can flip and get heads or tail for the coin we've chosen。 Now。

 what are the probabilities， I'd argue picking 1 is 0。5。

 And once I pick the fair coin and know that the probability of heads is once again 0。5。

 which makes a 0。25， the same is true for picking the fair coin and expecting tails。

 but as we pick the unfair coin with a 0。5 chance。 we get a 0。9 chance of heads。 So 0。5 times 0。

95 gives 0。45， Whereas for the unfair coin， the probability of tails is 0。

1 multiply the probability of picking it of 0。5 gives a 0。05。 Now。

 when I ask you what's the probability of heads。 we find that two of those cases Indeed come over with heads。

 So we add a 0。25 and 0。

![](img/a93c27f221645a0ab9ba264ca4e04e53_38.png)

4，5， and we get 0。7。So in this example， there's a 0。7 chance that we might generate heads。



![](img/a93c27f221645a0ab9ba264ca4e04e53_40.png)

Now， let me opt the ante by flipping this coin twice。 Once again。

 I'm drawing a coin from this bag and I pick one and fit with chance。

 I don't know which  one I've picked。 It might be fair or loaded。 And in flipping it twice。

 I get first heads。

![](img/a93c27f221645a0ab9ba264ca4e04e53_42.png)

![](img/a93c27f221645a0ab9ba264ca4e04e53_43.png)

And entail。 What's the probability that if I do the following。

 I draw a coin at random with his probability shown， and then I flip it twice that same coin。

 I destroyed once。 I flip it twice。 What's the probability of seeing heads first and entails。 Again。

 you might derive this using tooth tables。

![](img/a93c27f221645a0ab9ba264ca4e04e53_45.png)

So this is a nontravia question。 And the right way to do this is to go through the tooth table。

 which I drawn on over here。 There's three different things happening。

 We take an initial pick of a coin， which you can take coin 1 or coin2 with equal probability。

 And then you go we flip it for the first time。 and there's heads or tails outcomes。

 and we flip it for the second time with the second outcome。

 So these eight different cases summarize my tooth table。

 I now need to observe just the cases where head is followed by tail。

This one right here and one over here。 So we compute the probability for those two cases。

 The probability of picking coin number 1 is 0。5 for the fair coin we get 0。

5 for heads followed by 0。5 for tails。 that together is 0。125。 let's look at the second case。

There's a 0。5 chance of picking coin number two。Now， that one comes of its heads at 0。9。

 but it comes of its tails at 0。1。 So multiplying these things together gives us 0。045。

 a smaller number than a here。Adding these two things together results in 0。17。

 which is the right answer。With a question over here， there was really non trivialvi。

And I'd be amazed if you got this， correct。

![](img/a93c27f221645a0ab9ba264ca4e04e53_47.png)

Let me do this once again。 There are two coins in the bag。Coin 1 and coin 2。 And as before。

 picking coin 1 of 0。5 probabilityrility。 But now I'm telling you。That coin 1 is loaded。

 So give you heads with probability1。 Think of this as a coin that only has heads and coin 2。

Is also loaded。 It gives you head to 0。6 probability。 Now， work out for me。



![](img/a93c27f221645a0ab9ba264ca4e04e53_49.png)

![](img/a93c27f221645a0ab9ba264ca4e04e53_50.png)

And at this experiment。What's the probability of seeing tails twice。And the answer is depressing。

 If you once again draw the truthth table， you'll find for the different combinations that if you draw coin number one。

 you'd never see tail。 So this case over here， which indeed has tail tales。With have 0 probability。

 We can work this out probability of drawing the first coin of 0。5。

 but the probability of tails given the first coin must be 0 because the probability heads says 1。

 So 0。5 times 0 times 0。 That is 0。 So the only case where you might see tails tails is when you actually drew coin number 2。

 And this has a probability of 0。5 times the probability of tails。Given that he drew the second coin。

 which is 0。4 times 0。4 again。And that's the same as 0。08， but would have been the correct answer。



![](img/a93c27f221645a0ab9ba264ca4e04e53_52.png)

So the important lessons in what we just learned。 And the key thing is we talked about conditional probabilities。

 We said that the outcome of variable like a test is actually not like a random coin flip but it depends on something else like a disease。

 And we looked at this， we were able to predict what probability of a test outcome。

 even if we don't know whether the person has a disease or not。

 And we did this using the truth table。 And in the truth table， we summarized multiple lines。 So。

 for example， we multiplied the probability of a test outcome condition on this unknown variable。

 whether the person has a disease multiplied by the probability of the disease being present。

 and if we added a second row of the truth table。 where our unobservable disease variable took the opposite value of not disease。

 written this way and looks really clumsy， but that's effectively what we did when we went to the truth table。



![](img/a93c27f221645a0ab9ba264ca4e04e53_54.png)

![](img/a93c27f221645a0ab9ba264ca4e04e53_55.png)

![](img/a93c27f221645a0ab9ba264ca4e04e53_56.png)

![](img/a93c27f221645a0ab9ba264ca4e04e53_57.png)

So we now understand that certain coin flips are dependent on other coin flips。So if God。

 for example， flips the coin of us having a disease or not。

 then the medical test again has a random outcome， but its probability really depends on whether we have the disease or not。

 and we have to consider this when we do probabilistic inference in the next unit。

We're going to ask a real question。 Sa we really care about whether we have a disease like cancer or not。

 What do you think the probability is。Given that， our doctor。Just gave us a positive test result。

 And I can tell you， you will be in for a surprise。



![](img/a93c27f221645a0ab9ba264ca4e04e53_59.png)