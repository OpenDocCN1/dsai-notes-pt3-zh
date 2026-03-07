# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p13 P13 Lec 13-Graphical Models III -BV1Lcnhz1E7P_p13-

Get started for today。Quick announcement， i'm sure you all know this。

 but just to make sure nobody sleeps through the midterm next Monday， it will be next Monday。

 it'll be right here in class。It's a closed book， but as I mentioned last time you can bring a one page set of notes of anything you like。

 yes。Oh， oh， I'm sorry。This is important。Noon。对。Thank you。

I guess I made this one up too early in the morning。Thank you。 We will start at noon。

And it'll cover all the material and people have asked me， oh， but what'll be on the midterm。

 just the normal stuff that is， we're going to cover all the all the things that we think were most important and that we're most basic and we're not actually trying to make up really tricky。

 weird questions about the fivemin discussion that we had on Tuesday， April you know。

 we're not going to do that。 We're interested in testing whether you know the basics of the course。

 so。A good way to study， by the way， is just to get together with some of your colleagues in the course and ask each other questions that you think might be the kinds of questions that we would ask if we were going to test whether you understood the material。

Okay。Thank you for this correction。So today， I want to continue on base nets and。

Get to a very interesting new learning algorithm。But just to kind of remind you， base network。

 as we've said several times， is simply a。Graphical notation for representing joint probability distributions。

 and how to。Factor them into the product。Of a set of terms， one for each random variable。And。

Factors this way。So we've said that many times， what you should know most importantly about bay nutsts is this。

How you actually represent them， how they do define the joint distribution。

Note that you can calculate everything else from that because as we said in lecture two of the course。

 if you actually have the joint distribution over a set of variables。

 you can calculate the probability， conditional probability of any subset of them。

 given any other subset。Or just the flat out marginal probability of any one or any set of them。

So since base nets are simply a representation of the joint distribution。

That statements holds as much for Bay nets as it held for。The case in lecture too。

 we were just talking about having a table。You I remember we had poor people and people who worked a lot of hours and male and female people。

 and then we had just that big table。You should know how to read off conditional probabilities。

 I'm sorry， not conditional probabilities， but conditional inencies that are implied by that graph。

Okay， so today I want to talk a little bit about inference。

 but then mostly about using inference to do a very interesting kind of learning that we haven't yet discussed。

In general， when I talk about inference in base nets， what I mean is given a base net。

And an arbitrary question of the form， well， what's the probability of this subset of variables taking on these values。

 given this subset of variables has that set of values？

Then the inference problem is to answer arbitrary questions of that form。

And it turns out that in general， this is an NP complete problem。

 meaning that the cost of actually calculating that。Of course。

 you can always calculate it because the base net does represent a joint distribution。

Over the random variables。So the answer is there， but the cost can be exponential in the number of variables。

One way to see that is remember our default method for calculating any probability term is just to look at the table of the joint distribution。

 and of course there can be an exponential number of rows。In that table。

 exponential in the number of variables。In even the simple case we talked about in lecture two。

 we have those three variables， male， female， hardworking， not hard work many hours， work few hours。

 wealthy and not wealthy。And with those three boolean variables。

 we had eight rows in our joint distribution corresponding to the eight joint assignments。

So even with Boolean variables， we'll have two to the N rows exponential and。呃。

For just Nbuolean variables。 And so if we have to resort to that。

General method of counting up the rows in the joint distribution。Then。

You can see that that would end up being exponential。But in some cases。

 some of those questions are tractable depending on the question you ask and the form of the BNe graph。

We'll take a couple looks at this today。Because of that。

 it turns out another kind of general technique。 there are really two general fallback techniques for doing inference in bay nets。

 One is to figure out the joint distribution table from the bay net and then count up the Rosion need。

The other is fu Monte Carlo methods， where we actually just generate。

Samples of the joint distribution。Put another way， we generate fake data。

That we generate from the base net。In a distribution that followed of。Fake data that。

Is drawn from that joint distribution， and we'll talk about that in a minute。

But those are kind of the two back。Fall back general ways of doing inference。

 And then there are a lot of more specialized techniques， for particular。Basenet。

Graph structures that you might have。It's also a set of methods which we won't talk about in this course called variational methods。

 which allow you to。Tably compute proximate solutions to some of these inference problems and so if you're interested in this sort of thing。

 you might want to take the graphical models course that's offered in the machine learning department as a follow up once you finish this course you have the prerequisites to take that course。

 so if you're interested you can take an entire semester on basement。Okay。

 so let's just look at a couple。Inference questions just to make sure we're all on the same page。

Here's Bnet similar to the one that we talked about last time。It says if you have the flu。

 five random variables here， and that having a sinus problem could depend on whether you have the flu or an allergy and having a headache or a a nose runny nose could depend on whether you have a sinus problem。

Okay， so。If we have that。Problem， and you should know the answer to this immediately。

If I just want to know given that phase net。What's the probability of this particular joint distribution。

 and here I'm using little letters to represent the values of the random variables which are represented by big letters。

嗯。So how， how would I calculate the probability of those five variables taking on these five little。

Little variable values。You should know this。Right， I just look up。

I use the factorization that I get right， so I look at the probability that。

The F will take on the value， little F。And that's right there in the conditional probability table associated with this random variable。

 there's conditional probability distribution there， I just read that off。

And then similarly for allergy。And then similarly for what's the third one？Right。

 it's S given F and a。Because that's the factorization implied by this space。And then finally。

 the probability that headache will have。This value， given。Whatever the value s is。And。没有。

And the probability that I'll have n given S。Okay。That's a pe。Okay。

 so that's just what we talked about last time。 you can calculate easily。

