# 卡耐基梅隆【中英⚡高级机器学习｜10-715 2015 Advanced Introduction to Machine Learning】 p14 P14 Directed Graphical Models _14_ - Machine Learning 10-715 Fall 2015 -BV1hiWnzQERQ_p14-

O。So today we're going to do graphical models and。Here's the most important question that we want to answer。

 who came first the chicken and the egg， but okay， so this sounds like totally corny and stupid。

What you should， however， remember is that this is exactly the type of reason you want to avoid in graphical models。

Aid。Well， you know， if you have like a。Dirctor the arrow here in a directed arrow there and you get this nice loop。

 and then you can employly philosophers for centuries to reason about it。

 and you're not going to make very good progress here。

 and the reason is that actually this director graphical model as it stands is bogus。

 so never ever have loops。So if。Somebody ever。Later on。

 at some point we need to maybe work in industry， tries to convince you that such a design is a good idea。

 Yeah， at least you'll have a very nice counter example。Yeah， unfortunately， been there done that。嗯。

So let's start with something a little bit simpler first。

So this is about a simpler graphical model as you could want it。 I mean， actually。

 there's one simpler one where you have one cause and one effect， but fine， okay。

So let's try to figure out whether you need to be smart or strong to graduate， right？I mean。

 given that you guys are all PhD students， you very clearly fall into the Bray category， but okay。

 let's not talk about PhDs， but just graduation， maybe with the bachelor's。

And let's assume that maybe there are more people in general who are strong than smart。 okay。

 so let's make it 1 on 20% respectively。And will。The thing is being smart or being strong helps you to graduate so I've just made up those entirely random numbers here where I just claim that well if you have neither of those redeeming qualities then you only have a 10% chance of graduating。

 whereas if you're strong then well maybe you get the sports scholarship and you graduate。

 if you're smart likewise， if you have both well it helps you a little bit right？

So the question therefore then is。Well， you know。If somebody graduates， what can I say about。

 you know， whether he's strong or smart， right？So。Let's just。Now make up some table， right？So。

You know， assuming。Being strong and smart， you those two things occur independently of each other。

So then this is the distribution of events， of people who are。

Neither and who are both and well these respectively and you get them by just multiplying 0。1 or 0。

9 respectively with 0。2 and 0。8 respectively right so this table is all clear。I know this is very。

 very basic， but we'll actually get to see a whole bunch of surprising effects as we go through it。

So I think it's important to follow this through， okay？So our joint model over strength。

Brains and graduation。Therefore， would be a very simple model where I have， you know。

 the independent。Events for strength and price。And then the outcome of graduation given strength and brain。

This is the joint probe distribution。So I've totally made this up。Okay。

 so now let's see what happens。Is everybody cool with that basic setup？So now。Okay。

 this is just the joint distribution， right？So let's say if you neither smart nor strong。

As in if you're dumb and wimpy， well， that occurs with probability 0。9 times 0。8。Right。

 because with 90% probability year dumb， with 80% probability here wimpy。

 so multiplying those two out， well the majority of people。A Dman wimpy， okay？

AndI know it's not politically correct， whatever。嗯。Flip it the other way around is political correct。

 Okay， fine chances that you are exceptionally both physically and also mentally， well it's 0。

1 times 0。2， so that's 0。02。Right。Of course we are all in the roomor， right？Now。And that's just。

 you know， what you have for the rest。嗯。So now if I want to figure out something like。

 suppose that somebody graduates， what are。You know， what's the distribution of it being strong and。

You know， brainy。系。So first the first thing that I do is I multiply this previous table with that one。

 right， so I get these numbers。So flipping back so you can easily see what happened。

 multiply the left pointwise to the right。 So this is dot star Matlap， if you will。

So we get those numbers。Okay。Now these are basically the probabilities for the triple of events。

 namely dumb Wiimpy and graduated。You know， that's 7。2% of people。You know， managed to get this。And。

 you know， strong， smart and graduated，s 1。8%， and then there's you know 14。4 and 6。4% respectively。

Who managed to get through with one of those two abilities？So now I can ask the question， you know。

 given that somebody graduated。What are the chances that he has？Any of those qualities， right。

And so now all we have to do is this is simply based rule。So we。Basically。

 take the joint distribution。And divide by the sum。Over AC and B。

So I just integrate those two variables out。In other words。

 that this matrix divided by the sum of all the entries of this matrix。系。

Is that step clear for everybody？Sorry for going through that very， very slowly， but。

It's fairly fundamental。 and we will then afterwards make this way more complicated。Okay。

 so we do this。Now we've renormalized to one。And lo and behold。

 these are the probabilities that we see now。Okay， so given graduation。

 these are the probabilities that people are strong and smart。

The first thing to notice in this case is that。Now， all of a sudden。

 these variables are no longer dependent on if are no longer independent， right， before that。

 smart and strong were independent random variables。Conditioned on the fact that somebody graduated。

 they are no longer there。I think there was a question。 Okay， sorry。嗯。Any questions about that？

So it's kind of funny where we have independent random variables。We observed the joint outcome。

And all of a sudden， these independent random variables are no longer independent。

 conditioned on the outcome。So sometimes people write independence as follows。A， independent B。

 you write this as such，Now。I may have A and B independent on each other， but I'll get the case at a。

It's not independent， given C。吓。So， this is。Slightly counter intuitive， but。

We'll see a lot more of those cases。嗯。And。Yeah， the。

correspondingorresponding graphical model is this one here。So when people draw graphic models。

They shade the vertices solid， if they're observed。

And they are hollow if they're not observed this is。Com andly what's done。

Sometimes people write them with an extra solid circle and leave them hollow。

 but this is the more common way。So that's just a nice way of sometimes， you know。

 getting the idea of a graphical model across much more easily， because if I write this， right？

Then this is a lot harder to parse from this picture。Okay。

So I can obviously do a few more things with this so I can ask， you know。

 what are the chances that somebody is smart if you graduate， somebody that is。

 you know athletic if you graduate。Or then I can ask， you know， things like， what are the chances。

