# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p06 P6 Lec 6-Logistic Regression -BV1Lcnhz1E7P_p6-

Okay， let's get started for today， good to see you all。Showing again your persistence。

 neither hail nor ice nor snow。Can stop us？And。Couple quick announcements。

 I think most of you are aware that homework number three is due Wednesday。

And I hear that all is going well。 People are successfully being able to use the autograde system。

 So if you're having any difficulty with that， be sure to take a look at Piazza。

And the explanations there。We will hand out。The next assignment won't be out until next week， so。

Homework number four will come out on Monday， we're going to do probably a total of roughly seven homeworks I told some of you six earlier in the semester。

 roughly six， we decided to split some of the bigger ones into smaller ones。

So but as you'll notice from the arithmetic， that means most of the homework assignments will happen before the midterm。

And then after the midterm， we'll reduce significantly the rate of homework assignments because we want you instead to be able to work on your projects。

By the end of this week， we'll have a page up on our website。Describing on the idea of the projects。

And as you'll see， we're going to provide a number of data sets that you could choose one of those to work with and if you want to bring your own data。

 you could do that too， but you have to then write up a description of your project and assure us that you actually have the data already。

 you're encouraged to work with some other students。

 so we're thinking of teams of two and three people。To do the projects。 and like I say。

 we'll have more about that by the end of this week。There is a required reading for today。

 which is on our website。 If you go to the lectures tab or the class website。

You'll see this reading you can download it and also as I said in my email yesterday。

 there's another reading which covers the material which we did last week really on maximum likelihood and map estimation you're welcome to take a look at that for both of these if you find any ways to improve it。

 please let me know I'm interested in refining this and making it more useful for other people in the future。

Okay， any questions about logistics before we talk technical？Okay。Let's get started then。嗯。

So we were talking last time about Gaussian naive Bayes。

And I mentioned earlier in the semester they'd have a couple of pictures I carry around in my head。

And so I thought I would share one of the pictures for Gaussian and naive B。As we discussed。

Gausian naive base is just like。Discrete value at naive base， except that we assume the。

X sub Is are continuous variables， and so we have to have some kind of probability distribution that's appropriate。

For characterizing p of x sub I given y。And the reason we call it Gaussian knife phase is we choose a Gaussian distribution to do that。

And so。Here's a， I think， helpful picture。 Let's take a simple example of saying that we're trying to predict a Boolean variable。

 whether somebody plays basketball or not。Based on two continuous variables。

 their height and their machine learning grade。And so because they're continuous variables is kind of handy。

To think of the two dimensional space in which they live。So， let me call this one。X1， that's。Height。

So here be the height of a person。And here's x2。We could call that the machine learning grade。

And so we could plot any given person。 Any given example is a point in this two dimensional space。

If we want to。Train our naive based classifier。 They're basically。

Two kinds of probabilities that we need to。Learn from our training data。

One are just the priors on the。Class。Y equals1 and y equals 0。 Let's assume in this example。

 prior to 05。The other is the probability distribution on， well， each of our two variables。

 height and machine learning grade， conditioned on the value of Y。

 whether you're a basketball player or not。So in this imaginary example， let's suppose that， in fact。

 it's more probable that you're a basketball player if you're。Tall， than if you're short。

And so I could draw。Since I'm going to represent these distributions as Gaussians。

 let's suppose just for the sake of the argument。That I have a Gaussian that looks。Kind of like this。

For。That'll be my Gaussian distribution。 let's say， the probability。On height。Equals。Well， just是。

I'll just say X。I guess I could say x1， given that y equals one。

And I'll have another Gaussian distribution， of course， for the other case。Where y equals zero。

So this could be my probability distribution on height， given that y equals zero。

 given that you're not a basketball player。So these will be the two distributions I'm going to have to learn from training data。

 And as we discussed last time for each of those， I'll have some mean。

To define a normal distribution。I need to have a mean。This will be the mean for x sub1 and mu。呃。

And y equals zero。Here's a different mean。This will be the mean for x sub 1 and y equals 1。Okay。

And so given some training data， we might notice。We might estimate these muse and some sigma as well。

I'll have a sigma here。That characterizes the width of these distributions。

One for the case where y equals 0， another distribution when y equals1。And then similarly， of course。

 I'll have， for my other x sub I， x2， I'll have another pair of Gaussian distributions。

 one conditioned on the assumption that y equals0， one for y equals1。So I could draw those too。

He might look like this。Which one should we make Y I close 0。嗯。

I think if if you're a routine basketball player， you might not be studying quite as much。

So this is the probability of your machine learning grade， given that y equals one。

 given that you are a basketball player。And。Probability of machine learning grade， given that you're。

A total nerd。Allrry。Okay， so those are the distributions that we end up learning。

 these four conditional。Gausians， conditioned。On y equals 1 and 0 plus that prior up in the corner。

Okay， so now here's my space of x's， I could plot any one of us somewhere on this。嗯。

Two dimensional plot。Where is let me ask you a question。The point， where's the。

Combination of x1 and x 2， which is most probable。Given that you are a basketball player。Right。

 so the be at the mean。 So given that you are a basketball player。

 here's the probability of your height。 Well， it looks like your most probable height is this。

Similarly， your most probable machine learning grade is that。 And so if we just connect those。

I'm going to say around here。Would be your most probable。X， meaning x1 and x2， your most probable x。

 given that y equals1， where's the most probable x， given that y equals0？

