# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p16 P16 Lec 16-Adaboost, Margins, Perceptron -BV1Lcnhz1E7P_p16-

Great， so today， we're gonna finish off talking about boosting in particular about other boost。

 And then we'll talk about， we'll start talking about margins， geometric margins。 in particular。

 I'll focus on percept。 And if I time， I'll start talking about kernels。 And next time we'll do SVM。

😊，And actually， all these topics have topics have something nice in common。

 They are all widely used in practice， but also backed up by by solid foundations。 Okay。

 so that's one nice thing I like about these topics。Great， so just a very quickly recap。

 So we discussed about this last time。 So what is boosting is a general method for improving the accuracy of any given learning algorithm。

 And at a high level， it works by creating a series of challenge dataset sets such that even modest performance on these dataset can be venues to produce an overall highly accurate predictor。

😊，and we discussed this detail last time。 and we also discussed adabu。

 which is an algorithm that is widely used in practice and also has been thorough analyzed from a former point of view。

 And in particular， last time we went through the analysis of showing with the training error of ada boost goes quickly to0 as increase the number of rounds of boosting。

 but I also want to talk about generalization guarantees because the story here is particularly interesting。

 Okay， so just a quick recap what adabu does So where it's a boosting procedure。 and in particular。

 adabu does takes input a training set of examples。

 So a set of labeled examples right So this is X here is a feature part of our examples and this is a label part。

 a label part So the input of the algorithm is a fixed set of training examples and also a weak learning algorithm。

Yeah， so we also have an input a procedure on algorithm that is able to produce weak learners or rules of pumps。

 as if this could be， for example， naive based， or it could be some procedure that produces decision stamps。

 which are very simple classifiers。😊，Okay， so the input to the algorithm is basically a set of training examples。

 labeled examples and the weak learning procedure。😊。

And then the output of the algorithms should somehow be a very accurate classifier。

 right as accurate as you want to be。OkayAnd so to do so a what abu does it proceeding round in each round。

 we have a distribution D T over the training set of examples。

 and in each round round our weak learning algorithm of this distribution D in order to get a weak classifier H T and when we use this weak classifiedifier H to then come up with the underlying distribution D to come up with a new distribution。

 a nu distribution for the next round with a distribution D plus one and we went for this D last time and just gonna mean the specific boost has a specific update basically specific way to come up with distribution D plus one and we discuss this last time So this is the formula here but really whatda boost does。

 So it's very simple what does So so the way we create a new distribution D plus one is simply by increasing the weight on the incorrectly classified examples by the current week learner and by decreasing increase the weight on the incorrectly classified examples and decrease the weight on the。

😊，Correctly classified examples， right， So somehow trying to focus on harder examples and more concretely。

 the way it does it。 So itre gonna right。 So if an example is incorrectly classified。

 then we increase its weight in multiplicatively by E to the alpha T or alpha T is appropriately chosen as a function of the error rate of the classified H T。

 And if it's correctlyly classified， we decrease its weight with the same factor。😊，Okay， and right。

 And this is a the rule。 the easy way to remember， it is just basically all we do。

 we create a new distribution to T plus1， but has a property that has exactly half of the weight on the examples on which the previous classifier H T is incorrect and exactly have the half of the weight on the examples on which the previous classifier H T was correct。

😊，Okay， so it's very easy to remember。And that's pretty much the algorithm。 right。

 And when we go for a number of rounds。The other day， when we just output put a classifiedifier。

 which is a weighted majority vote of the weak learners of've generated so far。😊，Right。

 and the strength of the vote also depends on this normal on spectral alpha T。

 but also used the update。Right， and so basically， the more correct。

 the higher the rate of of the hypothesisesis H T。Sorry， the， the higher the accuracy。

 the the weak learner H P， the higher the weighting， the final classifier。But the。

But welana would have。Okay， in any case， okay， good。 So that's the a boost。 It's very， very simple。

 We just proceeding around in each round。 They have a current distribution about the set of training samples。

 We run our weak learning algorithm。 We get a weak classifier。

 and then we use a weak classifier and the current distribution to come up with a new challenge distribution by simply making sure that under the distribution D plus。

 we have half of the weight on the examples on which the current week learner is incorrect。

 and half of the weight and the examples on which the current week learner is correct。😊，Okay。

 and then we combine at the end of the day， all the weak learn generated now a majority vote。

 weight majority vote。Okay， when we want guys can see the we discuss this the algorithm is really simple。

 It's easy to code。 It' has no parameter to tune。 It's very fast， and it's also very general。

 We can use as a black box， any of our favorite simple algorithms， yeah。😊。

Can you tell the reason behind getting half enough。Yeah， so I discussed this last time。

 So the reason was a little bit technical。 So， right， okay， I guess the reason was， okay。

 So I guess I don't have the。 Let me see if I can recover。

 So the reason is basically when we analyze the training error rate。

 We argue that the training error rate actually， let me see if I can use mine。😊，My back movies。嗯。

Right， so first of all， O， so I guess， so last time we discussed， for example， several reasons。 Okay。

 why not， I guess we already went through this， Why not put all the weight right in V under E T plus1 or to put all the weight on the examples on which H T is incorrect。

 right， to discuss this。 And the answer is。If we， if we do so and you might not give anything new to us。

 right， Because it can always， if we put all the weight on the examples on which H T was incorrect。

 the weak learn will give us back the opposite of H T will add no new information。 Okay。

 so we cannot do something so aggressive So somehow we have to mix a little bit We have to give under plus1 examples on the previous the current classifier is correct and incorrect。

 we want nonetheless have significant fraction on the incorrect ones。 Now。

 why did we put half and half， well， because actually， when we went for the analysis。

 let me actually， maybe I'll do it here。 So when we went for the analysis， Yeah this is good。

 So we notice that like the number of misclassification。 So or the error rate。

 the empirical error rate of a boost， right， So the empirical error of the final classifier。😊。

We notice that is upper bonded by M times the product of the normalization factors， right。

 So if we go back here， we have to create this distribution Dp plus one， as we said。

 we increase the weight on the incorrectly classified examples we multi fashion。

 we decrease the weight on the correctly classified examples。 But then we have three normalmalize。

 right So is a normalization factor。 but make sure that everything sums up to one right and we want further the analysis last time and we concluded by doing analysis that the empirical error rate of the final classified is upper bond by M times the product of the normalization factors。

 Now， in order to make sure that this we want to decrease as quickly as possible， right。

 we want to to drive this to0 as soon as we can。 and the analysis showed us when we compute the normalization factors。

 But if we peak if we can the distribution D plus1 in the way we put half the weight on the correctlyly classified examples by H and have to to the incorrectly classified example by H。

 we're gonna get that this is when this were gonna go as quickly to0 as possible。😊。

So for what choice of， of the way to construct this， the distribution plus one。

 this upper bound on the error rate goes to 0 as quickly as possible。Yeah。

To get the lowest rate or the fastest， the fastest right， the fastest decrease。 Right， So actually。

 let actually go to the next slide。 So as we argued， right， So went't through this proof actually。

 right， So in order we proved last time， right， but basically。

 the the empirical error rate of the final classifier decreases exponentially fast。😊，So if gamma。

 so let's say， say gamma t the edge of is the edge of a random guess of the classifier H T around T right。

 then we argued that we want to improve this。 But the pretty rate of the final classifier is upper 1 by e to a -2 sum over t of gamma t squared。

 right， And if all gamma t are lower money by single things constant gamma。

 it can be simplified to look like this。😊，Right， and actually， the way you prove。

 we prove this is right we had as an intermediate step。

 We argued that the empirical rate of the final classifier is upper bound by this product zeroization factors。

 And for web choice of the way of the update。😊，We got the， the fastest。So， it's a technical reason。

That is not hard because we did everything in one。Yes。Okay， so， okay。

 so that's exactly what I'm to talk about today。 Okay， so right， so this is what okay。

 so it went formally right， then it approved last time this the statement about the empiricalicular rate of the final classifier output bad that boost after three round。

 right， and say well basically， but after three rounds of boosting the empiricalicular error rate is upper bound by e to the minus2 gamma square t。

 So decreases exponentially fast， right。😊。