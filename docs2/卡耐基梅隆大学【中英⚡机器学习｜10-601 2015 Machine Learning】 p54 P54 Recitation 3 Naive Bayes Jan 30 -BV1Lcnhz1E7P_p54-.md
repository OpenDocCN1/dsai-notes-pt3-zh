# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p54 P54 Recitation 3 Naive Bayes Jan 30 -BV1Lcnhz1E7P_p54-

So。Today， we're going talk about naive base， because that's what we've been talking about in class。

 And that's what your next homework， which is a programming assignment is about， so。

Feel free to stop me at any point。 If you have questions。 Im mostly gonna be sort of like。

Going over what we covered in class， with hopefully maybe a little slower。

 so I'm happy to stop and answer your questions。Okay。So night base。Is a classifier， right？

 And the goal of a classifier is usually to。Learn a model。That can predict some label Y。Given。

Usually some set of features， which we'll call X， right？Where x is usually a vector。

 it can be more than one featured， right。嗯。And。So often in a classifier。

 the model that we want to learn is。The probability of y given x or the probability of our label。

 given our features。 So， for example， if we're trying to。You know。

 build the document classifier where we want to determine。

Are these documents about science versus about？You know， history， then we want to predict。The label。

 science versus history， given a bunch of features which we extract from the document， right？

And so there are different ways to learn this distribution， probably of Y given X， but one。

 which is the approach that naive Bayase takes， is to model both。Probability of x given y。And。

The probability of why。And then use Bayes rule to calculate。Probably Y given X from those two things。

 but。In order to sort of specify our model， we have to specify these two。Distributions。

 and then from there we can calculate probability of Yga X， right？And。As we'll see next week。

 you actually don't always have to directly model the distribution of the features。

 This probability of X given Y。 There are some other classifiers that sort of take a different approach。

And just sort of。Model probability of wgonex directly。 But in9ive phase。

 we don't model probability of wgonex directly。We sort of specify distributions for these two things。

And then from there， we can calculate。Probably why I give an X。

Does anybody have questions about that？Okay。Great。So。As I said before， X。Is usually a vector。

 which means it' you have multiple features， right。So let's assume we have n features。

And let's assume for simplicity that we just have a binary classifier， right。

 So why can either take on value 0 or1，2 different possible labels。

So the probability of y is pretty simple， right， usually be like a Bnoulli distribution where the probability that y equals 1 is given by P and the probability that y equals 0 is given by 1 minus P。

嗯。But what does the distribution of x given Y look like？Well。

 the problem is that if you have a whole bunch of features。

 then this can be a pretty complex distribution with a ton of parameters， right。

So as we talked about in class， if。Let's say each of your featuress XI is Bnoulli。

And you have n features， then in order to specify a probability of x given Y。Well， let's say x1。

Through XN。How many parameters do you need？Well， you need specifically two。Times 2 to the n -1。

 right？ So this is order of 2 to the n parameters。So。How do we get around this naive B。

 we make a simplifying assumption of conditional independence。

 and that helps us vastly reduce the number of parameters we need to model this probability of X given Y distribution。

So I'll go over that in more detail， but。But， basically。

Once we use the conditional independence assumption。

 we end up being able to model probability x given Y with only two n parameters。

 which is just order N。So we have a much simpler distribution that we need far fewer parameters in order to specify。

嗯。Okay， so let's go over a quick example of conditional independence so that you guys sort of get the intuition of why this is a reasonable assumption to make。

Over here， actually。Let's do thisす。Okay， so let's say your label。Is。

Let's see you're trying to predict whether it's winter or summer， right， So your label could be。

 is it winter or just we can write winter。First summer。So this is your why。Okay。

 and then let's say you have two features。So feature one is。Sort of the temperature outside。

But we'll sort of discretize that and sort into hot and cold。 So， you know， if it's above。You know。

60 degrees will say it's hot。 And if it's below 60 degrees we' say it's cold。 Our second feature。

 let's say， is。Whether or not it's sunny outside。Okay， so winterverse summers Y is your label。

 Hot versus cold is your first feature。 So we'll call this X1。

 and then Sunnyverse overcast is your second feature。😊，So we'll call this x2， okay？And basically。

 when you're training a classifier， what you're going to be given is a bunch of data。 So basically。

 a bunch of。Instances with each values for each one of these variables， X1 x2 Y， right。

 And maybe there'll all be like different days throughout the course of a year， right， So like。

 for each day， you'll have， was it hot， hot or cold。

 Was it sunny or overcast and was it winter or summer， Let's forget about， you know。

 fall and spring for now。And。Ultimately， what you want to do is be able to predict whether it's winter or summer。

 given a new set of features， right， So if you don't know why。

 can you train a model that can predict Y， given X 1 and X 2。So in naive days。

We're going to make this assumption that x1 and X2 are independent given y。 Okay。

 And so you might ask， why does that make sense？ So let's think about it for a minute。First。

 let's think about whether X 1 and X2 are marginally independent。

 So if we don't condition on the season at all。Is the temperature outside and whether it's sunny or overcast。

 are they independent or not。嗯。You think about it logically for a minute。Not really。

 because if you think about the general season， you might notice that。It tends to be correlated。

 right， Maybe sunnier days tend to be warmer， and colder days tend to be more overcast。

But if you think about it a little more carefully， the reason for that might just be that in winter。

 it tends to both be colder and it tends to be more overcast than in summer。

 So there just happen to be a lot of days in winter that are both。Coldder and overcast。

 And there happened to be more days in summer that are both warmer and sunnier。

But there might not be like a direct， say， causal relationship between those two things。

 because you could have。Cold， sunny days in winter and warm overcast days in summer。

 It's just that there might not be that many of them just due to the fact that summer tends to be。

Warmer and also tends to be subier。Okay， so marginally， they might not be independent。

 but let's say we condition on why。 So what does that mean First。

 we restrict ourselves to just looking at。Y equals zero， so let's say that's winter。

So we only look at the days with label y equals 0。Now， maybe in winter， what we notice is that。Yeah。

 there might be a lot of cold days， and there might be a lot of。Overcast days。

But maybe they're no longer correlated， right。And similarly， if you just look at y equals1。

Which is summer。You might notice the same thing that。

Even though there might be a lot of hot days and there might be a lot of sunny days。

