# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p15 P15 Lec 15-Boosting -BV1Lcnhz1E7P_p15-

So。I guess I hope you guys had a good break。 We had the exams gra back。

 You can pick them up as you exit。嗯。So I guess we'll continue with the course。 And today， actually。

 we're going to go back。 So in the last couple of lectures。

 we've seen a little bit of semiupervised learning and unsupervised learning。 Today。

 we're going to go back and talk about supervised learning。 And actually。

 we're going to talk about one of the most。😊，Interesting paradigm in machine learning Let me boosting。

Okay， and what is boosting just at a very， very high level。

 What boosting is Boosing is a general method for improving the accuracy of any given learning algorithm。

And again， at a very， very high level， it works by creating a series of challenge data sets such that even more performance on this dataset sets can then be used to produce an overall highly accurate predictor。

😊，And actually， this is one of my favorite topics to teach because first of all。

 boosting any particular one of the specific algorithms here， a boosting these variations。

 So this algorithm is one of the top 10 algorithms in machine learning。

 So it's something that you guys should really know about。 Okay。

 so it's very useful in practice has been widely used。 So that's one nice thing。

 But a second interesting thing。 And it's equally important。

 actually turns out that we know a great deal about a boost from a formal point of view。😊。

And in fact， the boosting approach， as you see my lecture。

 boosting as an approach was developed originally as a way to answer some deep theoretical question concerning the intrinsic vnerability of supervised learning。

 Okay and then through some series of algorithmic refines send out to be one of the most so let's one of the most practical algorithms in machine learning so I think this is a very interesting example of where some deep fury question can lead to very practical algorithms。

😊，So that's why I really like it。All right， and so here is actual right in terms of readings。

 so actually I posted I will post online a link to the Rob Shapiier's overview on boosting and theyre also linked to one of these surveys。

 NIPS I guess might be something like Nps or stick survey audit on the topic okay so actually Robs tutorials on the topic are widely used by people for developing where slides for lectures and of course I did the same。

😊，Okay， so。I guess thank you Rob。Co， alright。 So that's the tutorial。 These are the readings。

 and now。😊，In terms of the plan for today， I'm just going to stop you a little bit of motivation when I'm going to give a brief a little bit。

 a very， very brief history， because it's important。To know how things developed。

 And then I'll just spend most of the lecture on discussing adabu。Which is， as I mentioned。

 super well studied in both theory and practice， Su。

 both from a theoretical and practical point of view。Okay。

 and for so boosting itself works for more than general。

 more more for more than binary classification。 But for simplicity for the lecture today。

 I'm just gonna focus on binary classification。 But many of these things can be extended to multiclass and so on。

😊，Okay。Great， so let me start with a little bit of motivation。 Okay。

 so let's imagine that just here is an example。 So imagine that we are trying to write a computer program to help us decide which email messages are spam and which are important one of our classic problems problems that we think about。

 right now， for this type of problems by now， know after a midter and after half of the class。

 I'm sure that you guys know that could the primary learning algorithms。

 you could try to use knife base or we could try to use logistic aggression or your favorite algorithm。

 So there are many algorithms we could try to use right And so for those algorithms like knife based or logistic aggression what we do we take a large set of emails。

 a large set of email messages as spam or not。 and into those algorithms and we know that if large is large enough。

 according to the generation guarantees we talked about in the course。

 will be guaranteed to output a hypotheses but as well a new examples that come from the source。

 So we are guaranteed。😊，To output a hypothesis that has good generalization error。

 If the training set was large enough in size。 Okay， so in office by now。Okay， this is one， I mean。

 really the standard approach。 One of the standard approaches in machine learning， okay。Now。

 here is a very different approach。 So here is the the basic idea behind boosting。 Okay。

 so say that for this problem for spin detection problem， for whatever reason。

 we think it's hard to just at once in one shot， find a highly accurate prediction role。Right。

 and let's say， that for this problem， I mean， it's obvious that for example， for this problem。

 it is much easier to come up with simple rules of harm with weak learners， right。

 to rules of harms that are far from being highly accurate， but are， that are very， I mean。

 that are correct， reasonably often， but do better very no guessing。Okay。

 so here is an example for the spa detection problem。 So here is an example of such's your rule。

 right， So for example， if the phrase by now appear in the message when we predict spam。Okay。

Weak rule， like a rule of farm， reasonablea rule。Here another example is if the phrase。

 say goodbye to death appeared in your message， when again predicts man。Okay。

 so these are very simple rules that we could come up with very easily， right， And， you know。

 obviously， again， they are very far from being accurate。

 but they do something better better not guessing。Okay， and obviously。

 we are very far from being accurate because， for example。

 these rules do not tell us anything about messages。 They do not contain。

 say phrases like by now or say goodbye， goodbye to death， right。

 So they only only apply to a small subset of the emails。 But again。

 they are better than right nowm guessing。😊，Okay， they are very easy to come up with。Okay。

 so now this is the key insight behind boosting。 So the key insight behind boosting is that in many of the problems。

 it is often quite easy to come up with simple rules of farm that are better random guessing。

 Okay and then what boosting does。 So when boosting is based on this observation what boosting is a meta procedure that takes seen an algorithm that is able to find weak learners that is able to find rules of farm And then somehow boosting is able to produce a highly accurate rule by calling the weak learner repeatedly on several very cleverly chosen dataset sets。

😊，Okay， so this is boosting at the high level。 What boosting does in a nutshell。Okay， so for example。

 for the span detection problem。 So say that， you do have a weak learner algorithm。

 So we have an algorithm that can generate reasonable rules of harm。 Okay。

 so for the span detection problem with this thing we do， for example。

 you could first call this algorithm on the whole subset of the emails that we have available。

 And then we get a weak rule like H one like the one that I had on the previous slide。😊。

If the phrase say goodbye to your death appears in the message Juniper spa。 Yeah。

 so we could first get a weak rule H1。 And then well do this week rule H1 to then somehow come up with a second subset of email messages。

 But we then fit in the weak learning algorithm， which will then give us a second rule of thumb H2 and so on。

 repeat this a number of times， right？ And then at the end，ll get a number of weak rules。

 And then the end， well combine these weak rules。😊，Into hypothees。

 that hopefully will be much more accurate。so it's the boosting approach basically texting is at a high level。

 texting an algorithm that is able to produce simple rules that are better when on guessing。

 and then what the boosting would do boosting would then produce a series of cleverly chosen subsets or distribution of the examples and then would call the weak learning algorithm on those series of cleverly chosen subsets to produce a series of weak learning weak weak hypotheses which then in the end would combine in a way that hopefully lead to a highly accurate hypotheses。

 yes。😊，What do you mean by makeup precision？Okay， so， I'll come back to this later in the course。

 It's like， you'll see， we can use any weak learning algorithm。 Okay。

 so it's a It's more than a specific algorithm。 Okay。

 so so maybe you should we will talk about this a bit later。 I mean。

 I call it meta procedure just because I mean， it's just a termin issue just because it's very generally。

 give me your favorite weak learning algorithm。 I can just turn it into youll see in a second into something very highly accurate。

😊，Yeah， that's what I mean。 It's just。I'm trying to emphasize that It's very general。Good。Alright。

 And so that's boosting。 And now， okay， of course， in order again。

 while still staying at a high level， become more concrete soon。

 but still staying at a high level for this approach to even have any chance to work。

 we need to be able to answer two very important questions。

 Okay and question number one is how to choose this set of examples to give to the weak learning algorithm in round。

 right， how to choose the challenge data sets to fit into into the weak learning algorithm。

 That's question number one。 and question number two is how to combine。 So。

 once we get this weak learning， once get this weak rules， how to combine them， you know。

 to lead to a more accurate rule， to high accuracy rule。😊。

And these are the two key questions to think in mind to keep in mind as we go for the lecture。

 And again， this is very very high level without going into any precise details， I we just mentioned。

 but typically what we do when we do boosting for the first question。

 which is how to choose which examples to fit to the weak learning algorithm for the next round for the first question。

 typically what we do we somehow concentrate on the hard examples。

 we concentrate on the examples but the previous rules got wrongly it's very natural right to focus our attention。

 Why what we don't know yet。 so that's typical。😊。