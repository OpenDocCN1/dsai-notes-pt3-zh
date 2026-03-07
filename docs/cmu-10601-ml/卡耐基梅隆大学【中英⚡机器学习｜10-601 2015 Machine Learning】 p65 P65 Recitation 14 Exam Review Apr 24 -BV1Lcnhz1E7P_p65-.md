# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p65 P65 Recitation 14 Exam Review Apr 24 -BV1Lcnhz1E7P_p65-

Okay， let's start。I think this is maybe our final recitation so I wanted to have a final exam practice for you guys so basically this is how it's going to run I'm going present a question read it over for you guys and try to read it through clarify some details maybe and then I'll give I hope you guys brought some maybe pencil and paper to write on I'll give you maybe two or three minutes depending on how the question is to try to solve it and then I'll go over the solution asking you guys maybe some people to contribute answers or maybe voting on which answer we think is correct for if there's a few options。

😊，This is just kind of a collection of questions that we covered in the class that might be kind of similar to some of the stuff that you'd get on the final exam。

 so hopefully it's a decent assortment of things。Okay。Let's get to our first question。

 start off talking a little bit， just some probability， talking about conditional independence。

So let's suppose you've got variables， A， B， C， and D。

And you want to show that A is independent of B and C given D。

 so A is conditionally independent of B and C， given D。

Show that this implies that A is conditionally independent of B， given D。

So if you guys want to start， I'll just give you a couple minutes to try to solve that one out and we'll go through the math。

Okay， so just going through the solution to this guy。 So we want to show that。

That A is conditionally independent of B， given D， right。So basically we want to show the following。

Probability of A， comm B， given D。Is equal to the probability of A。Givenive D， times of probability。

Of B given D， right， Because this is the definition of， of conditional independence。

 So how can we do that， We really want to use the the hypothesis here that A is conditionally independent of B and C given D。

 So we can start out by writing the left hand side here。As the following。Okay。

So we can take a sum overs。And then do probability of A， comma B， comma C。Givenive D。

 so this is just a marginalization of the C variable and then based on our hypothesis that A and B is independent of C given D。

 we can write the following as a product of two terms， so we take the sum over C。

Let me take the product probability of a comma B。Given D and the probability of C， given D。Actually。

 did we say A is independent B and C。Yeah， A is independent B and C。Wron way， probably is。A given D。

And a probability of B and C gudy？Now note that probability of a given D doesn't depend on C。

 which we take the sum over here， so we can bring that outside the sum。

 so we just have probability of a given D multiplied by the sum over C of this last term。

Probability of B， comm C， givendy。Now， just like we marginalize over C to get the equience between these two。

 we can now we're marginalizing over C over this smaller joint probability。

 so this equals what we want， which is probability of A given D。Times probability of。B给问啲。こう。

So how you show that。just looking at it intuitively， it's kind of useful to know this that if。

One random variable is conditionally independent on say two others。

 then that means it's conditionally independent on either of them，So moving on to the next question。

 we're going to go into Bay nets a little bit。By networks okay so for each of the following pairs of BayE networks in this figure and I've got two on the next page so we'll go through these two first and then when you guys are finished working on we'll go to the next slide you want to determine if the two Bay nets are equivalent so namely if they have the same set of independence and conditional independence assumptions。

😊，If you decide that the two basesnets for A， B， C and D are equivalent。

 state one independence or conditional independence assumption that they both share。

 if you decide that they're not equivalent， state one independence or conditional independence assumption that one satisfies but not the other。

 so go ahead and start working on that。

![](img/c0bf186df505945e2d94266154e8383e_1.png)

Anybody want more time， or you guys mostly got these？Show of hands more time。 No， okay， Okay。

 so who thinks for part A， the two networks are equivalent。 show of hands。Be a good问。

Sees about half the people raised here， okay who thinks that the two networks are not equivalent？

Okay， a few people raise hand， Okay， for the people who think they're equivalent。

 can I get some explanation？😊，Any of you guys over here？多し。Independent to city。Okay， y。In both cases。

Okay， that's good， so yeah the answer is yes， they are equivalent and that's pretty much right if you condition on B。

 then it blocks A and C， so they're independent and if you don't condition on anything。

 then all the guys are dependent on each other。😊，Okay， what about for the second one。

 who here thinks that the two networks are equivalent？Okay。

 nobody who thinks that they're not equivalent。Awesome， and somebody who thinks are' not equivalent。

 can you tell me why？Just shout it out or raise your hand。Mmhmm。

You say independent given B in the first one， right？Mmhm。😊，Yeah that right that's right。

 yeah so the key thing here that you got to look for these head to head。

 so when you've got A and C are both pointing to B， so when you observe B。

 it causes a dependency between A and C， so that's the key thing that's not shared by the first one。

😊，Okay， so let's go on to the next two， I'll give you guys another。

Yops another minute for these guys，s okay。Same thing。 We want to know。

 are these two networks equivalent。 these are a little bit harder。 And if so， an example of of aal。

 you know， conditional dependency that they share or if not。

 an example that one has and the other does not have。You guys think you got it。

 you want a little more time to think about it。Okay， let's talk about it。

 so who thinks the for part C， who thinks these two networks are equivalent？Okay， see a few hands。

 nice， who thinks that they're not equivalent？Equivalent， okay。

 the answer is that they're equivalent。 actually， does anyone have an example of。😊，Yeah。

 an example of conditional dependencies that they share。

 they want to say somebody who raised their hand for equivalence。Yeah， actually。

 this is the same two。Sure。That's right， and that's true both in the。Sees not。Okay， right。

If C is not given， yep， exactly because you have a head to head on C。

 so that means that D is independent of both A and B when you don't observe C， right？So part D。

 who thinks that they're equivalent？Equivalent one take， who thinks that they're not equivalent？Okay。

 looks like most people。 So for people， the answer is are they're not yeah， they're not equivalent。

 And so for people who think they're not， does someone have a good example。

 maybe somebody else from over here of， of what conditional depend Penency one has that the other one does not have。

Sa嘅。B and D， independent， given A。Right in the first one。And not in the second one。 That's true。

 You can also say， I mean， a。Doesn't affect things so much。

 You can also say independent or conditional on nothing。

 that same thing holds B is independent of D in the first one and not the second one。

 but you're right。 also independent or conditional on me。 Okay， nice work， guys。

 Let's go to the second。Now our next question。So Markov blankets。

 do people here remember the definition of a Markov blanket？If remember or do not remember？Okay。Well。

 I could say it really quickly。 It basically gives the answer。

 I forgot if we went over in detail in the class， but it's a terminology that's useful。

 but sometimes we don't explicitly call it a Markov blanket。

 but I'll just say it Markov blanket are the parents。

 the children and the children's other parents for a given set of notes。😊，So with that in mind。

 the first question is asking， what's the Markov blanket of the set A comma S of notes？

So based on my definition I just gave there， can you guys go ahead and write down mark of the set of nodes that are in the Markov blanket of Acom S。

Parents， children and other parents of the children。And if somebody has a。

