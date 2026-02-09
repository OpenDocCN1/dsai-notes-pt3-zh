# 约翰霍普金斯大学《数据科学：统计和机器学习｜Data Science： Statistics and Machine Learning》中英字幕 - P2：1_02 01 概率介绍.zh_en - GPT中英字幕课程资源 - BV1jsAAeNE3k

Hi and welcome to the class on probability as part of the statistical inference class in the Coserated Day of Science series。

 my name is Brian Kaho， and this class is co talk， my coinstructors， Jeff Lee and Roger Pang。

 we're all in the Department of Biostatistics at the Bloomberg School of Public Health。



![](img/05c0db18de9621f0cde11840d88bd5d8_1.png)

In this lecture， I'm going to cover probability at a very basic level just enough for what we need in the data science specialization。

I have a more in depth treatment in my mathematical Biosstatistics bootcamp series。

You can watch them on a YouTube playlist anytime you'd like。

 and then the course is offered about every two months on Coursera and I give the link here In addition。

 the course notes are on GitHub。

![](img/05c0db18de9621f0cde11840d88bd5d8_3.png)

Let's talk about probability。 So given a random experiment， say， for example， Ro a die。

 a probability measures a population quantity that summarizes the randomness。

I want to emphasize this wordpop here What this means in the di roll context is that we think of it as an intrinsic property of the die。

 not as something that is a function of a simple set of fixed roles of the die。

 so when we talk about probability， we're not talking about something that is in the data that we have but as a conceptual thing that exist in the population that we would like to estimate。



![](img/05c0db18de9621f0cde11840d88bd5d8_5.png)

So let's be specific about the rules that probability has to follow so called probability calculus。

First of all， probability operates on the potential outcomes from an experiment， for example。

 when you roll a die， you could get a one or you could say the role was in the set one or two or the role was an even number。

 24，6 or the role was an odd number， 135 and so on。

So the probability is a function that takes any of these sets of possible outcomes and assigns it a number between0 and 1。



![](img/05c0db18de9621f0cde11840d88bd5d8_7.png)

You have to have the rule that the probability that something occurs， in other words。

 that you roll the die and you get a number must be one。

And then the probability of the union of any two sets of outcomes that have nothing in common must be the sum of their respective probabilities。

 So， for example， take， for example， when I roll the die。



![](img/05c0db18de9621f0cde11840d88bd5d8_9.png)

One possible outcome is that I get a one or a two。 Another possible outcome is that I get a3 or a4。

 Those two sets， one and 2， and the other set，3 and 4 are mutually exclusive。

 They cannot both simultaneously occur。The probability of the union that I get a one， a two。

 a three or a four is the sum of the two probabilities。

 the sum of the probability that I get a one or a two plus the sum of the probability that I get a three or four。

 it turns out that these simple rules are all that are necessary to generalize to all the rules that we think probability should follow and this was discovered by the Russian mathematician Kmorov。



![](img/05c0db18de9621f0cde11840d88bd5d8_11.png)

Here are some of the rules that probability must follow， some of them I stated already。

 and some of them are consequences of what I stated already。

The first is the probability that nothing occurs is zero， so you have to roll the die。

 something has to occur。 you have to get a number， and that's similarly related to the probability that something occurs that you do get a number is a one。



![](img/05c0db18de9621f0cde11840d88bd5d8_13.png)

Something that we intuitively seem to know is the probability of something is one minus the probability that the opposite occurs。

 So the probability of getting an even number when I roll the die is one minus the probability of getting an odd number because the odd numbers are the opposite of getting an even number in the context of a die。

The probability of at least one of two or more things that cannot simultaneously occur。

 we call sets of things that cannot simultaneously occur mutually exclusive is the sum of their respective probabilities。

 This was part of the basic definition that we outlined in the previous slide。



![](img/05c0db18de9621f0cde11840d88bd5d8_15.png)

Another consequence of our probability calculus， if the event A implies the occurrence of the event B。

 then the probability of A occurring is less than the probability that B occurs。

 And this is kind of a tongue twister to say， and it seems a little bit conceptually hard。 However。

 if we draw Venn diagram， it becomes very simple。 The event A lives inside of the event B。

 So when we talk about the probability of A。 We talk about a number assigned to this circle A。

 And we talk about B。 We talk about the probability assigned to this circle that includes the area of A。

 So it would make sense that the probability of B was larger than the probability of a。



![](img/05c0db18de9621f0cde11840d88bd5d8_17.png)

![](img/05c0db18de9621f0cde11840d88bd5d8_18.png)

So I think we intuit this very easily， for example， the probability that we get a1。

 the set A is less than the probability that we get a1 or a two， the set B。



![](img/05c0db18de9621f0cde11840d88bd5d8_20.png)

Then this final bullet point is very useful for any two events。

 the probability that at least one occurs is the sum of their probabilities minus their intersection。

 Again， this becomes very easy to visualize with a Venn diagram here we have the set A and we have the set B if we add their two probabilities。

 you see that we've added the intersection in twice once when we added in A and once when we added in B。

 Since we've added it in twice if we want the probability of the union。

 we need to subtract it out once。The result of this rule is to say that you can't just add probabilities if they have a non trivial intersection。

And we'll give an example of that in a second。

![](img/05c0db18de9621f0cde11840d88bd5d8_22.png)

The National Sleep Foundation reports that around 3% of the American population has sleep apnea。



![](img/05c0db18de9621f0cde11840d88bd5d8_24.png)

They also report around 10% of the North American and the European population has restless leg S。

 let's assume for the sake of argument that these are probabilities from the same population。

Can we just simply add these probabilities and conclude that about 13% of people have at least one sleep problem of these sorts in this population？



![](img/05c0db18de9621f0cde11840d88bd5d8_26.png)

So the answer is no， the events can simultaneously occur and so are not mutually exclusive。

 we think that there is a nontrivial component of the population that has both sleep apnea and restless leg syndrome。



![](img/05c0db18de9621f0cde11840d88bd5d8_28.png)

So to elaborate， let's let A be the event that a person drawn in this population has sleep apnea and B be the event that they have restless leg syndrome。



![](img/05c0db18de9621f0cde11840d88bd5d8_30.png)

Here， we think this intersection is non trivial。 And so if we were to add the two probabilities。

 we would believe we will have added it in twice， and it would need to get subtracted out to find the probability of the union。



![](img/05c0db18de9621f0cde11840d88bd5d8_32.png)