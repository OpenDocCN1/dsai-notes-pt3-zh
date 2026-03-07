# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p58 P58 Recitation 7 Additional practice with graphical models Feb 26 -BV1Lcnhz1E7P_p58-

Okay， so today we're going to talk about。Graphical models a little bit more。 It's going be。

Have some overlap with last week's recitation。 But I felt like since it's sort of important material that it was worth going over some of this independence。

Structure and sort of inference in Bayesian networks again。So basically I'm going to work through。

An extended example using this graphical model that is projected。On the screen。嗯。

So feel free to stop me and ask questions if you're confused about anything。

Why don't you start by sort of looking at that graphical model？And。So basically。

 let's suppose we have these 1，2，3，4 minutess like 7 variables。 And it's this model of how。like。

These two diseases， diseases， flu and dehydration relate to these various other variables。

 including season and then a bunch of symptoms。Right。And。Let's suppose that we also have。A bunch of。

Conditional probability distributions for each of the variables。

 And we'll assume that the variables are all binary for now。

 although in the first thing we're going to do， which is look at， try to like。嗯。

Understand what independencies exist among these variables， the CP。

 the conditional probability tables don't really matter。Okay。So since this is sort of an example。

 feel free to like， I'm going to try to get people to answer a few questions that I ask。Okay。

 so thinking about deseation， baseball， however you like to think about it。Let's start with。

Is season independent of chills？Okay， so we'll give you like。30 seconds to think about it。

 and then someone hopefully will raise their hand。听早。Yeah， so， yeah。 so nothing is observed。

 So I'm just saying， is season independent of chills。 So is it true or false， it。

 I it dependent or not。Depenent right， so it's clear to say like it's not independent。

Okay because in fact， all we can say from this network is that it's not。

 we don't know for sure that it's independent。 We actually don't know if it's dependent or not until we actually see the conditional probability table。

 but from the structure of the network， all we can say is that they're not independent。

 and can anyone point out like a path along which influence can flow from one to the other。Raer。

 can you speak up。Yeah， exactly， okay。Okay， what about if we observe the flu？Cant， can't hear you。

Someone raise their hand。Yeah， so it's independent。😊，So why？Informal？Go back。你同。Yeah， and basically。

The only path from season to chills is directly through flu right。

 so that's the only path we need to look at and we can see that based on the different like three variable structures that we know about and how influence flows through them。

 we can see that if flu is sort of blocked， you can't get from season to chills， right？ok。

But about this one is season independent of headache given that we observe the flu。No， okay， why？Yes。

 exactly， so influence can still flow。Along the path， season through dehydration and headache， right。

 So when we observe flu， one path is blocked， but a second path is still open。

 so they're not independent。Right， okay。What about if we also observe？Dehydration。嗯。😊。

They're independent， yes。So basically that other path that we are relying on is now blocked and there are no other viable paths。

 right？What about this one， are season in nausea independent， given that we observe dehydration？Why。

系啲。Yeah， exactly， okay？What if we also observe？Headache。All right season and nausea independent。Okay。

 yeah。They are， so。So season to nausea。How many different paths are there？1。To。😔。

I sort of see at least like three， right？Three distinct paths。But when you observe。

Dehydration and headache， if you look at every individual path， you find that they're all blocked。

 therefore they're independent， okay。What about this is flu independent of dehydration when you don't observe anything？

H。😊，Why not？ThisSo independent of dehyration。Yep。Well， can influence flow through headache？No。

 because that's a V structure， right， influencelu can only flow through a V structure when the central node is actually observed。

 That's the one that's different from all the others and that you should keep in mind。

 But season is not observed so we can go up through season and back down to dehydration。

 so they're not independent。Okay， same question， but let's as we observe season and headache。

Are they independent， are flu and dehydration independent？No。喂hy。できうか。なんか。RightSo as I said。

 in this special type of structure， when headache is observed。

 that's actually when influence can flow down through headache and back up to dehydration。

 because they have a common child。Yeah。Yeah。