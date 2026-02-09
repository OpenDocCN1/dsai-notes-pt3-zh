# 约翰霍普金斯大学数据科学课程6：《统计推断课程（约翰霍普金斯大学）》｜statistical-inference｜ - P2：1_02 01 概率简介.zh_en - GPT中英字幕课程资源 - BV1oG41197es

![](img/c5ddf585786be6eebe896dff61cb25ef_0.png)

Hi and welcome to the class on probability as part of the statistical inference class in the Cose of data Science series。

 my name is Brian Kaffho， and this class is co talk， my coinstructors， Jeff Lee and Roger Pg。

 we're all in the Department of Biostatistics at the Bloomberg School of Public Health。



![](img/c5ddf585786be6eebe896dff61cb25ef_2.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_3.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_4.png)

In this lecture， I'm going to cover probability at a very basic level just enough for what we need in the data science specialization。



![](img/c5ddf585786be6eebe896dff61cb25ef_6.png)

I have a more in depth treatment in my mathematical Biosstatistics bootc series。



![](img/c5ddf585786be6eebe896dff61cb25ef_8.png)

You can watch them on a YouTube playlist anytime you'd like。

 and then the course is offered about every two months on Coursera。

 and I give the link here In addition， the course notes are on GitHub。



![](img/c5ddf585786be6eebe896dff61cb25ef_10.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_11.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_12.png)

Let's talk about probability。 So given a random experiment， say， for example， Ro a die。

 a probability measures a population quantity that summarizes the randomness。



![](img/c5ddf585786be6eebe896dff61cb25ef_14.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_15.png)

I want to emphasize this wordpop here What this means in the di roll context is that we think of it as an intrinsic property of the die。

 not as something that is a function of a simple set of fixed roles of the die。

 so when we talk about probability， we're not talking about something that is in the data that we have but as a conceptual thing that exist in the population that we would like to estimate。



![](img/c5ddf585786be6eebe896dff61cb25ef_17.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_18.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_19.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_20.png)

So let's be specific about the rules that probability has to follow so called probability calculus。



![](img/c5ddf585786be6eebe896dff61cb25ef_22.png)

First of all， probability operates on the potential outcomes from an experiment， for example。

 when you roll a die， you could get a one or you could say the role was in the set one or two or the role was an even number。

 246 or the role was an odd number， 135 and so on。

![](img/c5ddf585786be6eebe896dff61cb25ef_24.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_25.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_26.png)

So the probability is a function that takes any of these sets of possible outcomes and assigns it a number between0 and 1。



![](img/c5ddf585786be6eebe896dff61cb25ef_28.png)

You have to have the rule that the probability that something occurs， in other words。

 that you roll the die and you get a number must be one。

And then the probability of the union of any two sets of outcomes that have nothing in common must be the sum of their respective probabilities。

 So， for example， take， for example， when I roll the die。



![](img/c5ddf585786be6eebe896dff61cb25ef_30.png)

One possible outcome is that I get a one or a two。 Another possible outcome is that I get a three or a four。

 those two sets， one and two， and the other set，3 and four are mutually exclusive。

 They cannot both simultaneously occur。

![](img/c5ddf585786be6eebe896dff61cb25ef_32.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_33.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_34.png)

The probability of the union that I get a one， a two。

 a three or a four is the sum of the two probabilities。

 the sum of the probability that I get a one or a two plus the sum of the probability that I get a three or four。

 it turns out that these simple rules are all that are necessary to generalize to all the rules that we think probability should follow and this was discovered by the Russian mathematician Kmorov。



![](img/c5ddf585786be6eebe896dff61cb25ef_36.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_37.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_38.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_39.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_40.png)

Here are some of the rules that probability must follow， some of them I stated already。

 and some of them are consequences of what I stated already。



![](img/c5ddf585786be6eebe896dff61cb25ef_42.png)

The first is the probability that nothing occurs is zero so you have to roll the die。

 something has to occur， you have to get a number， and that's similarly related to the probability that something occurs that you do get a number is a one。



![](img/c5ddf585786be6eebe896dff61cb25ef_44.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_45.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_46.png)

Something that we intuitively seem to know is the probability of something is one minus the probability that the opposite occurs。

 so the probability of getting an even number when I roll the die is one minus the probability of getting an odd number because the odd numbers are the opposite of getting an even number in the context of a die。



![](img/c5ddf585786be6eebe896dff61cb25ef_48.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_49.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_50.png)

The probability of at least one of two or more things that cannot simultaneously occur。

 we call stats of things that cannot simultaneously occur mutually exclusive is the sum of their respective probabilities。

 This was part of the basic definition that we outlined in the previous slide。



![](img/c5ddf585786be6eebe896dff61cb25ef_52.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_53.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_54.png)

Another consequence of our probability calculus， if the event A implies the occurrence of the event B。

 then the probability of A occurring is less than the probability that B occurs。

 And this is kind of a tongue twister to say， and it seems a little bit conceptually hard。 However。

 if we draw Venn diagram， it becomes very simple。 The event A lives inside of the event B。

 So when we talk about the probability of A。 we talk about a number assigned to this circle A。

 And we talk about B。 we talk about the probability assigned to this circle that includes the area of A。

 So it would make sense that the probability of B was larger than the probability of a。



![](img/c5ddf585786be6eebe896dff61cb25ef_56.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_57.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_58.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_59.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_60.png)

So I think we intuit this very easily， for example， the probability that we get a1。

 the set A is less than the probability that we get a one or a two， the set B。



![](img/c5ddf585786be6eebe896dff61cb25ef_62.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_63.png)

Then this final bullet point is very useful for any two events。

 the probability that at least one occurs is the sum of their probabilities minus their intersection Again。

 this becomes very easy to visualize with a Venn diagram here we have the set A and we have the set B if we add their two probabilities you see that we've added the intersection in twice once when we added in A and once when we added in B。

 since we've added it in twice if we want the probability of the union we need to subtract it out once。



![](img/c5ddf585786be6eebe896dff61cb25ef_65.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_66.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_67.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_68.png)

The result of this rule is to say that you can't just add probabilities if they have a non trivial intersection。



![](img/c5ddf585786be6eebe896dff61cb25ef_70.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_71.png)

And we'll give an example of that in a second。The National Sleep Foundation reports that around 3% of the American population has sleep apnea。



![](img/c5ddf585786be6eebe896dff61cb25ef_73.png)

They also report around 10% of the North American European population has restless leg S。

Let's assume for the sake of argument that these are probabilities from the same population。



![](img/c5ddf585786be6eebe896dff61cb25ef_75.png)

Can we just simply add these probabilities and conclude that about 13% of people have at least one sleep problem of these sorts in this population？



![](img/c5ddf585786be6eebe896dff61cb25ef_77.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_78.png)

So the answer is no， the events can simultaneously occur and so are not mutually exclusive。

 we think that there is a nontrivial component of the population that has both sleep apnea and restless leg syndrome。



![](img/c5ddf585786be6eebe896dff61cb25ef_80.png)

So to elaborate， let's let A be the event that a person drawn in this population has sleep apnea and B be the event that they have restless leg syndrome。



![](img/c5ddf585786be6eebe896dff61cb25ef_82.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_83.png)

Here we think this intersection is non trivial。 and so if we were to add the two probabilities。

 we would believe we will have added it in twice and it would need to get subtracted out to find the probability of the union。



![](img/c5ddf585786be6eebe896dff61cb25ef_85.png)

![](img/c5ddf585786be6eebe896dff61cb25ef_86.png)