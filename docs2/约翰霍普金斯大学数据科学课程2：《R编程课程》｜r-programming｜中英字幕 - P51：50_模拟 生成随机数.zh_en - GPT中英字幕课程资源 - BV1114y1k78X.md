# 约翰霍普金斯大学数据科学课程2：《R编程课程》｜r-programming｜中英字幕 - P51：50_模拟 生成随机数.zh_en - GPT中英字幕课程资源 - BV1114y1k78X

![](img/392650c66b1bcd251272ad368f2761d8_0.png)

I'm going to talk about simulation in this lecture。

 simulation is a very important topic for statistics and for a number of other applications。

 so I just want to introduce some of the functions in R that can be useful for doing simulation。

 So there are a couple of functions that are available for the simulating numbers or variables from given probability distributions。

 probably the most important of which is the normal distribution。

 and so we can generate variants from the normal distribution。



![](img/392650c66b1bcd251272ad368f2761d8_2.png)

![](img/392650c66b1bcd251272ad368f2761d8_3.png)

![](img/392650c66b1bcd251272ad368f2761d8_4.png)

![](img/392650c66b1bcd251272ad368f2761d8_5.png)

![](img/392650c66b1bcd251272ad368f2761d8_6.png)

By specifying a mean and the standard deviation for that distribution and then calling the R norm function。

 So the R norm function will simulate normal random variables from a distribution that has given mean the standard deviation So there are corresponding functions for for the normal distribution that can be used to evaluate the probability density to evaluate the cumulative distribution function and for also for evaluating the quantile function。

 So another function for generating random variables is the R poise function or which generates poisson random variables from a poisson distribution with a given rate And so。



![](img/392650c66b1bcd251272ad368f2761d8_8.png)

![](img/392650c66b1bcd251272ad368f2761d8_9.png)

![](img/392650c66b1bcd251272ad368f2761d8_10.png)

![](img/392650c66b1bcd251272ad368f2761d8_11.png)

![](img/392650c66b1bcd251272ad368f2761d8_12.png)

![](img/392650c66b1bcd251272ad368f2761d8_13.png)

![](img/392650c66b1bcd251272ad368f2761d8_14.png)

![](img/392650c66b1bcd251272ad368f2761d8_15.png)

So there are a number of functions for generating random variables from the standard probability distributions。

 and you can use these to run simulations。

![](img/392650c66b1bcd251272ad368f2761d8_17.png)

![](img/392650c66b1bcd251272ad368f2761d8_18.png)

So probability distribution functions there are basically four functions associated with them。

 And so for any given distribution like the normal distribution。

 there will be a function that starts with the D a function that starts with an R of the P and a Q。

 So be four different functions for each distribution。

 So we've I've already mentioned that there's the R norm function So the R norm function is for generating is for random number generation。

 there's a D norm function which evaluates the density of the probability distribution for a given mean and standard deviation。

 there's the p norm function which evaluates the cumulative distribution and there's a Q norm function which evaluates the quantile function。

 So every distribution has of these four types of function。 So for the。😊。



![](img/392650c66b1bcd251272ad368f2761d8_20.png)

![](img/392650c66b1bcd251272ad368f2761d8_21.png)

![](img/392650c66b1bcd251272ad368f2761d8_22.png)

![](img/392650c66b1bcd251272ad368f2761d8_23.png)

![](img/392650c66b1bcd251272ad368f2761d8_24.png)

![](img/392650c66b1bcd251272ad368f2761d8_25.png)

![](img/392650c66b1bcd251272ad368f2761d8_26.png)

![](img/392650c66b1bcd251272ad368f2761d8_27.png)

![](img/392650c66b1bcd251272ad368f2761d8_28.png)

Gamma distribution， there will be a D gamma and R gamma， P gamma and a Q gamma function。

 and for the Poisson distribution， there's the R， D P po and Q po functions。



![](img/392650c66b1bcd251272ad368f2761d8_30.png)

![](img/392650c66b1bcd251272ad368f2761d8_31.png)

So working with the normal distribution requires these four functions， so I mentioned there's D norm。

 p norm Q norm and R norm， and you can see that each take a number of different parameters。

 all of the functions require that you specify the mean and the standard deviation because that's what specifies the actual probability distribution。

 if you do not specify them the default values are a distribution a standard normal distribution which has mean zero and standard deviation 1。



![](img/392650c66b1bcd251272ad368f2761d8_33.png)

![](img/392650c66b1bcd251272ad368f2761d8_34.png)

![](img/392650c66b1bcd251272ad368f2761d8_35.png)

![](img/392650c66b1bcd251272ad368f2761d8_36.png)

![](img/392650c66b1bcd251272ad368f2761d8_37.png)

For the D norm function you can evaluate the density and there's iss an option that allows you to evaluate the log of the density。

 Most of the time when you evaluate the density function for a normal distribution you're going to want to use the log of that value but the default is false for the p norm function and the Q norm function there' also an option to evaluate it on a log scale but another option is evaluate is whether or not you want to evaluate the lower tail of the distribution So the lower tail which is the default if you can think if you look at the probability distribution。

 it's the part that goes to the left it's the lower tail if you want to evaluate the upper tail sometimes you want to do this then you want to say lower tail equals false and that will evaluate the upper tail of the distribution finally for R norm there's only two parameters mean the standard deviation and then n which is the number of random variables that you want to generate。

 So if n is 100 you'll get a vector of 100 numbers that are drawn from the。



![](img/392650c66b1bcd251272ad368f2761d8_39.png)

![](img/392650c66b1bcd251272ad368f2761d8_40.png)

![](img/392650c66b1bcd251272ad368f2761d8_41.png)

![](img/392650c66b1bcd251272ad368f2761d8_42.png)

![](img/392650c66b1bcd251272ad368f2761d8_43.png)

![](img/392650c66b1bcd251272ad368f2761d8_44.png)

![](img/392650c66b1bcd251272ad368f2761d8_45.png)

![](img/392650c66b1bcd251272ad368f2761d8_46.png)

![](img/392650c66b1bcd251272ad368f2761d8_47.png)

![](img/392650c66b1bcd251272ad368f2761d8_48.png)

![](img/392650c66b1bcd251272ad368f2761d8_49.png)

![](img/392650c66b1bcd251272ad368f2761d8_50.png)

Normal distribution。

![](img/392650c66b1bcd251272ad368f2761d8_52.png)

So just to be more explicit， if phi is the cumulative distribution function for the standard normal distribution。

 then p norm is equivalent to phi and Q norm is equivalent to the inverse of phi。



![](img/392650c66b1bcd251272ad368f2761d8_54.png)

![](img/392650c66b1bcd251272ad368f2761d8_55.png)

![](img/392650c66b1bcd251272ad368f2761d8_56.png)

So just quickly， if you want to generate some random normal variants you can just call Rnome and pass an integer。

 which is the number of variables you want to generate so here I'm passing 10 and you can see that the vector that's produced will be random normal numbers which have mean0 and standard deviation 1 if I wanted to generate a vector that had mean 20 and standard deviation 2 I just need to specify that explicitly in my call to R norm so here this vector has are 10 random normal normal random variables and there mean is roughly 20 and their standard deviation is 2。



![](img/392650c66b1bcd251272ad368f2761d8_58.png)

![](img/392650c66b1bcd251272ad368f2761d8_59.png)

![](img/392650c66b1bcd251272ad368f2761d8_60.png)

![](img/392650c66b1bcd251272ad368f2761d8_61.png)

![](img/392650c66b1bcd251272ad368f2761d8_62.png)

![](img/392650c66b1bcd251272ad368f2761d8_63.png)

![](img/392650c66b1bcd251272ad368f2761d8_64.png)

![](img/392650c66b1bcd251272ad368f2761d8_65.png)

So when anytime you simulate random numbers from any distribution for any purpose。

 it's very important that you set the random number generator seed and this can be done with the set dot seed function So what's important to know is that on computers when you generate random numbers the numbers are not actually random but they appear random and that's the important thing and so the idea is that if you wanted to generate the same set of random numbers again。

 you could if you wanted to because the numbers are not actually random theyre called they're what are called pseudoran numbers And so here I'm setting the seed to be one so the seed can be any integer you want you just pass it an integer and that's the seed So here I'm going to set seed equal to1 and then I'm going to generate five random normal random variables。



![](img/392650c66b1bcd251272ad368f2761d8_67.png)

![](img/392650c66b1bcd251272ad368f2761d8_68.png)

![](img/392650c66b1bcd251272ad368f2761d8_69.png)

![](img/392650c66b1bcd251272ad368f2761d8_70.png)

![](img/392650c66b1bcd251272ad368f2761d8_71.png)

![](img/392650c66b1bcd251272ad368f2761d8_72.png)

![](img/392650c66b1bcd251272ad368f2761d8_73.png)

![](img/392650c66b1bcd251272ad368f2761d8_74.png)

![](img/392650c66b1bcd251272ad368f2761d8_75.png)

And so here I've got my five normal random variables they have mean zero and standard deviation 1。

 If I generate another5， you'll see that the vector is totally different because it's another random sample of5 however if I reset the seed to be one and I draw five again you'll see that they're exactly the same as the first five that I drew So anytime so when you set the seed。

 it kind of sets the sequence of random variabless that's going to occur and if you reset the seed。

 you kind of set the sequence to go back to where you started and then it will continue to generate random variables from there So this is important because it allows for you to reproduce a random numbers that you generate now that might sound strange because why would you want to generate the same random numbers twice but in many applications you do want to generate the same random numbers twice so that people can reproduce what you've done in particular if there are some errors or problems in what you've done。

 you want to be able to to kind go back to the exact situation that produced。



![](img/392650c66b1bcd251272ad368f2761d8_77.png)

![](img/392650c66b1bcd251272ad368f2761d8_78.png)

![](img/392650c66b1bcd251272ad368f2761d8_79.png)

![](img/392650c66b1bcd251272ad368f2761d8_80.png)

![](img/392650c66b1bcd251272ad368f2761d8_81.png)

![](img/392650c66b1bcd251272ad368f2761d8_82.png)

![](img/392650c66b1bcd251272ad368f2761d8_83.png)

![](img/392650c66b1bcd251272ad368f2761d8_84.png)

![](img/392650c66b1bcd251272ad368f2761d8_85.png)

![](img/392650c66b1bcd251272ad368f2761d8_86.png)

![](img/392650c66b1bcd251272ad368f2761d8_87.png)

![](img/392650c66b1bcd251272ad368f2761d8_88.png)

Those problems so whenever you do a simulation， you always want to set the random number seed so that you can go back and get the same results。



![](img/392650c66b1bcd251272ad368f2761d8_90.png)

![](img/392650c66b1bcd251272ad368f2761d8_91.png)

So I've demonstrated how to generate normal random variables。

 but of course you can generate random variables from other probability distributions。

 so the Poisson distribution is of course very popular here I'm generating a 10 poisson random variables with a rate of 1 and so of course Poisson data are going to be integer here I'm generating a 10 poisson random variables with the rate of  two so you can see they're slightly larger and then here I'm generating 10 random variables poisson random variables with the rate of 20。



![](img/392650c66b1bcd251272ad368f2761d8_93.png)

![](img/392650c66b1bcd251272ad368f2761d8_94.png)

![](img/392650c66b1bcd251272ad368f2761d8_95.png)

![](img/392650c66b1bcd251272ad368f2761d8_96.png)

![](img/392650c66b1bcd251272ad368f2761d8_97.png)

![](img/392650c66b1bcd251272ad368f2761d8_98.png)

And so so for the Poisson distribution， the mean is going to be equal to the rate so you can see that roughly in each of these three cases。

 the mean is roughly equal to the rate that I specified I could also evaluate the cumulative distribution function for the Poisson distribution So here'm in this first example I want to know what is the probability that a Poisson random variable is less than or equal to 2 if the rate is 2 and so this is the probability is 0。

67 roughly if I want to know what's the probability that a poisson random variable with rate2 is less than 4。

 less than or equal to 4 you can see the probability is getting bigger and here I can see the probability that a Poisson random variable is less than 6。

 less than or equal to 6 and it's very close to1。

![](img/392650c66b1bcd251272ad368f2761d8_100.png)

![](img/392650c66b1bcd251272ad368f2761d8_101.png)

![](img/392650c66b1bcd251272ad368f2761d8_102.png)

![](img/392650c66b1bcd251272ad368f2761d8_103.png)

![](img/392650c66b1bcd251272ad368f2761d8_104.png)

![](img/392650c66b1bcd251272ad368f2761d8_105.png)

![](img/392650c66b1bcd251272ad368f2761d8_106.png)

![](img/392650c66b1bcd251272ad368f2761d8_107.png)

So the cumulative distribution allows you to evaluate these probabilities。



![](img/392650c66b1bcd251272ad368f2761d8_109.png)