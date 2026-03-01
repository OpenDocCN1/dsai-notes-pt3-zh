# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p36 35_连续型随机变量.zh_en -BV1r483zbEzN_p36-

。

![](img/71bb99ad405d45458e778fbb867beffc_1.png)

Hello， I'm Dr。 McCll from Johns Hopkins University。

 and today we're going to be talking about continuous random variables。

 So in the previous model module， you were looking at discrete random variables。

 and those were numbers that were countable they might have been infinite but you could count each of the items when you roll a dice。

 how many how many times did you roll a three on a six sided dice after you rolled at time and time and time again。

 you can count those But what about things that you can't count what about numbers like if if I go and run two miles right now and I finish that Ron and I'm at 12 minutes。

 am I really at 12 minutes or am I at 12 minutes in one second or am I at 12 minutes and 00001 milliseconds what is that time you can't really count it because there's this infinite range surrounding that time period of 12 minutes So these are things that are not countable And so with anything dealing with time anything a lot of times we。

We'll use these continuous distributions to approximate， sometimes countable things。

 so there's a lot of applications where we're dealing with distributions random variables where you can't do the counting。

We are going to be talking about。

![](img/71bb99ad405d45458e778fbb867beffc_3.png)

Continuous。Random。

![](img/71bb99ad405d45458e778fbb867beffc_5.png)

Variables。

![](img/71bb99ad405d45458e778fbb867beffc_7.png)

AndI'm going to use the abbreviation for random variables RV is what you'll see me use throughout the lecture just so that we're not confused。



![](img/71bb99ad405d45458e778fbb867beffc_9.png)

![](img/71bb99ad405d45458e778fbb867beffc_10.png)

We talked about this a little bit before。 but if there is a sample space and I think I've used this example with you before when my daughter was around five。

 she I cutter once she took a beanbag chair and she put the beanbag chair there and that she took a stool and she put it on top of the beanbag chair and then she got another chair on top of that And so she's stacking this up to reach a toy on the top shelf。

 and are any of you concerned for my daughter right now， I'm like， Abby。

 you were going to like break your neck， you're going to kill yourself。 And what does she say to me。

 Oh no no no， I've done this before right Well， and she didn't understand the concept of maybe and in that example。

 is there a number， there's not a single number in that in that sample space of events。 In fact。

 if I were to go and use that same analogy where I'm going to go run two miles。

 I there a number involved in whether I ran fast or slow。 No。

 it's actually subjective until I break out the watch and I apply some rule that translates that that event in the real world。



![](img/71bb99ad405d45458e778fbb867beffc_12.png)

![](img/71bb99ad405d45458e778fbb867beffc_13.png)

![](img/71bb99ad405d45458e778fbb867beffc_14.png)

![](img/71bb99ad405d45458e778fbb867beffc_15.png)

![](img/71bb99ad405d45458e778fbb867beffc_16.png)

Onto the number line。 And so what we end up doing is we are a random variable， right is。



![](img/71bb99ad405d45458e778fbb867beffc_18.png)

![](img/71bb99ad405d45458e778fbb867beffc_19.png)

Mapping something that happens in a sample space onto the real number line。

And we can model the frequency of that。

![](img/71bb99ad405d45458e778fbb867beffc_21.png)

With a little F of x。And it might be some sort of。

![](img/71bb99ad405d45458e778fbb867beffc_23.png)

You know， function that we can draw on the lumber line where in my analogy here。

 this x is representing time， but it could represent any number。

 any numerical mapping of some event that happens in the real world right and we kind of understand that this line you know events that you would see if you draw samples from this sample space are going to be more likely to occur here where there's a higher peak and less likely here where there's a valley right so that's how we're kind of interpreting that。



![](img/71bb99ad405d45458e778fbb867beffc_25.png)

![](img/71bb99ad405d45458e778fbb867beffc_26.png)

![](img/71bb99ad405d45458e778fbb867beffc_27.png)

![](img/71bb99ad405d45458e778fbb867beffc_28.png)

![](img/71bb99ad405d45458e778fbb867beffc_29.png)

Okay。And so this function that I've drawn， we call the probability。



![](img/71bb99ad405d45458e778fbb867beffc_31.png)

![](img/71bb99ad405d45458e778fbb867beffc_32.png)

Density。Fangcheng。And the key word here is density。 It's also referenced as a P D。



![](img/71bb99ad405d45458e778fbb867beffc_34.png)

Probability density function。Yep。And probability density function is a little bit like the probability mass function that you saw in discrete random variables。

 but we'll explore some of those differences。

![](img/71bb99ad405d45458e778fbb867beffc_36.png)

So the first thing I'd like to point out is what is the probability？



![](img/71bb99ad405d45458e778fbb867beffc_38.png)

![](img/71bb99ad405d45458e778fbb867beffc_39.png)

Bi。That a random variable x。

![](img/71bb99ad405d45458e778fbb867beffc_41.png)

Equals some specific random variable。 So like this little point right here。



![](img/71bb99ad405d45458e778fbb867beffc_43.png)

![](img/71bb99ad405d45458e778fbb867beffc_44.png)

Is going to be a specific x。 What is the probability that a random variable is exactly that point。

 exactly that point。

![](img/71bb99ad405d45458e778fbb867beffc_46.png)

Well， the probability that it is exactly that point is0。 for the same reason。

 I explained when you're when you're going to run a certain distance。

 you can't run exactly 12 minutes。 you might be a millisecond earlier or a millisecond late in doing that run if I were to look and say。

 hey， I'm going to bring my face half the distance to this marker right。

 and I'm going to do half the distance again， and then half the distance again。

 well I ever reach the marker， Well， not if I keep doing halfs right。

 it can be this infinite infinite half divisions and I'll never actually reach the marker right。

 that's the concept of infinity， So when we're looking at a continuous random variable。

 the probability you get an exact value because there's an infinite number of options around that specific point。

 right Well， the likelihood of landing exactly on there over infinite possibilities infinite in the denominator。

 we know that that probability approaches 0。

![](img/71bb99ad405d45458e778fbb867beffc_48.png)

![](img/71bb99ad405d45458e778fbb867beffc_49.png)

![](img/71bb99ad405d45458e778fbb867beffc_50.png)

![](img/71bb99ad405d45458e778fbb867beffc_51.png)

![](img/71bb99ad405d45458e778fbb867beffc_52.png)

![](img/71bb99ad405d45458e778fbb867beffc_53.png)

So because I can't evaluate the probability of being an exact value like you can in a probability mass function。



![](img/71bb99ad405d45458e778fbb867beffc_55.png)

![](img/71bb99ad405d45458e778fbb867beffc_56.png)

I now need to use intervals in order to assess probability。 So what I' will do is I'll say， well。

 what's the probability on between A and B somewhere in that interval？



![](img/71bb99ad405d45458e778fbb867beffc_58.png)

![](img/71bb99ad405d45458e778fbb867beffc_59.png)

Well， and what that essentially does is if I draw these。



![](img/71bb99ad405d45458e778fbb867beffc_61.png)

Lines and I'm looking at the probability of being between A and B。

 I'm looking at well what's the likelihood I'm in this shaded region right so I'm basically taking the area under this density function between the interval A to B is what I'm doing。



![](img/71bb99ad405d45458e778fbb867beffc_63.png)

![](img/71bb99ad405d45458e778fbb867beffc_64.png)

So we evaluate probability over these intervals， and that's really exciting because it allows us to use calculus。

 So the probability that a is less than or equal to x。😊。



![](img/71bb99ad405d45458e778fbb867beffc_66.png)

![](img/71bb99ad405d45458e778fbb867beffc_67.png)

![](img/71bb99ad405d45458e778fbb867beffc_68.png)

Less than or equal to B is going to be equal to the integral from a to B of f of x。



![](img/71bb99ad405d45458e778fbb867beffc_70.png)

DX， and that's just saying the area from under the curve from A to B along that interval。



![](img/71bb99ad405d45458e778fbb867beffc_72.png)

![](img/71bb99ad405d45458e778fbb867beffc_73.png)

Okay。Again， it's equivalent to the probability mass function。 but in the PMF， you actually had a box。

 right， You actually had， know， a PMF looked like like this， right， if this was a PMF。



![](img/71bb99ad405d45458e778fbb867beffc_75.png)

![](img/71bb99ad405d45458e778fbb867beffc_76.png)

![](img/71bb99ad405d45458e778fbb867beffc_77.png)

You would have a box here， a box。

![](img/71bb99ad405d45458e778fbb867beffc_79.png)

Something like that， and you could say， well， hey， what's the probability that I actually had this value of x？



![](img/71bb99ad405d45458e778fbb867beffc_81.png)

Right， and you could look and say， well， what's the probability that falls under that mass， right。

 or if I had an interval of A to B， I could then just sum。



![](img/71bb99ad405d45458e778fbb867beffc_83.png)

Over this interval of x being an A to B of the probability of x。



![](img/71bb99ad405d45458e778fbb867beffc_85.png)

And I could add these masses together and I could estimate what the probability is in that interval。

 Well， I don't have any mass， right， the probability of any of those things is zero you know for getting a single point。

 so I have to take this interval。

![](img/71bb99ad405d45458e778fbb867beffc_87.png)

![](img/71bb99ad405d45458e778fbb867beffc_88.png)

![](img/71bb99ad405d45458e778fbb867beffc_89.png)

Now there's a few important principles when we're dealing with a probability density function or a PDF so a function。



![](img/71bb99ad405d45458e778fbb867beffc_91.png)

![](img/71bb99ad405d45458e778fbb867beffc_92.png)

![](img/71bb99ad405d45458e778fbb867beffc_93.png)

Is a PDF。

![](img/71bb99ad405d45458e778fbb867beffc_95.png)

If。And only if。We have these conditions one。

![](img/71bb99ad405d45458e778fbb867beffc_97.png)

The integral from negative infinity to infinity。

![](img/71bb99ad405d45458e778fbb867beffc_99.png)

has to equal  one right basically that saying something has to happen and you can't have probability than more than one right the sum。

 the area under the curve of a probability density function is equal to one。



![](img/71bb99ad405d45458e778fbb867beffc_101.png)

![](img/71bb99ad405d45458e778fbb867beffc_102.png)

![](img/71bb99ad405d45458e778fbb867beffc_103.png)

The other thing， we've already said this， but the probability that a random variable equals a specific number in this case A。



![](img/71bb99ad405d45458e778fbb867beffc_105.png)

![](img/71bb99ad405d45458e778fbb867beffc_106.png)

Is equal to， as we are looking at what is the probability between a and A at one specific point would be equivalent to this integral from A to A。



![](img/71bb99ad405d45458e778fbb867beffc_108.png)

Regardless of whatever function you choose， you'll see that that equals zero。And then third。

 the third issue is third。The requirement is that f of x has to be greater than or equal to  zero。



![](img/71bb99ad405d45458e778fbb867beffc_110.png)

For all x， so this curve can never drop below the x axis you can never have a negative value。



![](img/71bb99ad405d45458e778fbb867beffc_112.png)

，So these become the three requirements that are necessary for a probability density function。

 and this is how we understand probabilities for continuous random variables。



![](img/71bb99ad405d45458e778fbb867beffc_114.png)