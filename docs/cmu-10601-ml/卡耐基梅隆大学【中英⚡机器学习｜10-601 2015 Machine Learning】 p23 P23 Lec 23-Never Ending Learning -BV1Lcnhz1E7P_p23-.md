# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p23 P23 Lec 23-Never Ending Learning -BV1Lcnhz1E7P_p23-

close to my heart， never ending learning， it's actually a research direction that I'm engaged in and so I'd like to talk about that today and as you'll see it touches on several of the topics that we've covered during the course and then Wednesday we're going to talk about neural networks and deep learning so that's the plan for this week。

So never ending learning here's the idea。 actually， by the way。

 these are all people involved in the project， including people like Gabu here and many other interesting people。

😊，Professor William Cohen， who teaches the big data machine learning course。

 which you might want to take， or some of you are taking。 this semester is involved。

Professor Eteanhushka， who is a professor in Brazil。

 but comes and hangs out with us every January because he loves Pittsburgh winners so much。

And number of other people。Involved in the project。And here's the idea。

 The idea is think about what we've talked about in this class on machine learning。Mostly。

 we've talked about。Well， the primary topic we've talked about is really function approximation。

Given training examples of input and output of some function。

We want an algorithm that can guess what that function is in a way that accurately extrapolates to new examples that we didn't train it on。

And we talked about logistic regression。 We'll talk about neural nets。

 We talked about linear regression。 We talked about decision trees， support vector machines。

 lots of ways of doing this。Now， here is the observation that got me started down this path。

 I was talking with my mother。And explaining to her that I work in machine learning。

And she said fine， she's a very smart person， but she's not a computer scientist。

 and so she asked me， what do you do and so I started telling her about these function approximation problems and she said to me。

I watched you grow up， that's not learning。😊，So she's right， as mothers often are。

And so here's the thesis that underlies this research。We'll never really understand learning。

In computers that' in people。Until we can build machines that like you and I。

Learn many different things。Over a long period of time with very diverse experience。For example。

 we learned to crawl， and we learned to walk， then we learned to ride a bicycle。In parallel to that。

 we learn to count， then we learn to add， then we learn algebra。

Then we learn graphical models in parallel with that。

 we learn how to pick up stuff in later physics and we get synergy between all these things in very interesting ways。

 right that calculus course you were taking helped you learn physics and vice versa。😊，We're。

Different kind of learning machine than the kind we primarily talk about when we talk about。

A program to estimate one function， given input and output examples of the F function。And so。

 and furthermore， we do become better learners over time。

 We don't just become better estimators of the output of the function。 given the input。

 We also become suddenly capable of learning material that years ago， we weren't。

Even in a position to learn。So the question， the brain teaser。

 the theme of this research question is what would it take to build a computer program that like us learns for years and gets better in these various ways？

So we don't know the answer to this question。But I think it's an important question for the field。

You think about just the evolution of the field of machine learning from decade to decade。

 And it's only about。Well， I seeve， the earliest interesting work I know is the work on perceptrons and the work that Art Samuels did building a checkers program that learned to play。

Checkers better over time。 That was late 50s。 So the field is about 55 years old now。

And if you go forward another 20 years， I think。The field will grow and hopefully grow in a way that we can take on these kind of problems。

So， so that's my motivation。 So what are we doing about this？ Well， we don't know the answer。

 but we thought we would pick a case study and try to build a computer program that learns for years。

 and the task we chose for this case study was to learn to read the web。So reading the web。

 really reading。Not just。You give me a search key and I return the page。

 but really read and understand as you and I would。Computers can't do that today。

 And so we thought it was a challenging enough problem to。Warrant years of learning。And so here。

 here's the way we set up the problem。 First of all。

 the task for the program is to run 24 hours a day forever。And then each day do two things。

Extract more facts from the web。Structured facts from that unstructured text that's out there。

To populate a growing knowledge base， which is currently about 90 million beliefs。

 We'll look at that。And number two， each day， it also， this is just as important。

 should learn to read better than it could yesterday。Meaning it should。If we send it back to this。

 if it has learned to do better today than yesterday， the evidence for that would be。

That we could send it back to the same text that looked at yesterday。

 and it should be able to extract more facts more accurately today if it had learned to read better。

Yes， that's the way。We set up the task， make sense。And then what's the input to the program。 Well。

 there's the input。 We define an initial ontology， which means categories。

 a set of category predicates and relation predicates we want the system to learn about。For example。

 we told that we wanted to learn about people and athletes and sports teams and which athlete plays on which sport team and so forth。

嗯。We give it for each of those predicates， a dozen labeled examples。

So if we say we're interested in sports teams， then we give it a dozen noun phrases that refer to sports teams。

 Pittsburgh pirates。New York Yankees， Pittsburgh Steelers， that's it。And then， the web。

And occasional interaction with human。Trainers。And I'll say more about that。Okay。

 so there's the task。So as you can see， we've kind of set this up as a challenge to ourselves。

To try to build a computer program that can keep getting better。Over time。All right。

 So where are we today， Well， the system， we call it Nell， never ending language learner。

Has been running since January 2010。 We just had its fifth birthday， big party。

And it currently has a knowledge base that it has extracted。

With about 90 million beliefs and probabilities， confidences associated with each of those。

 plus for each of those， a pointer back to the source， the text from which it，Obtain that belief。

It is learning to read， It is a better reader this today than it was a year ago。

 and it was better than than a year before。It's also learning to reason to do inference over the knowledge base that it has built。

 and it's learning to make up， extend the ontology。By making up new predicates。

 new categories and relations that we didn't give it。

But which is part of its learning tasks is to expand its representation， yes。反都个。Like our week。

So no nothing do like that。Something like you say we have a meta analysis。 what does that mean？

Any my approach。リザです。Thisn't the most effective on China。啊。Yeah， that's good。 And yeah。

 part of what makes us good learners is we can kind of go meta， self reflect。

 strategize that this isn't working。 Maybe I should。Talk to the TA。

N is not very good at that at the moment。 So I think that's one of the self reflection and more targeted。

Use of time。Is one of the areas where。Nell is pretty impoverished， actually。

 but that's a great area for。I see。