# 约翰霍普金斯大学数据科学课程6：《统计推断课程（约翰霍普金斯大学）》｜statistical-inference｜ - P6：5_03 02 贝叶斯规则.zh_en - GPT中英字幕课程资源 - BV1oG41197es

![](img/aa1aee68378eed9c9328c7cc054ae49a_0.png)

Perhaps one of the most famous uses of conditional probability is so called Bay's rule；

 This rule was named after a Presbyterian minister named Thomas Bays。

 who had his work published posthumously。

![](img/aa1aee68378eed9c9328c7cc054ae49a_2.png)

B's rule allows us to reverse the role of the conditioning set and the set that we want the probability of。

 so imagine in the event that we want the probability of B given A。



![](img/aa1aee68378eed9c9328c7cc054ae49a_4.png)

When we have or can easily calculate the probability of A given B。

 well Bay's rule says you can do that， you can relate B given A to A given B。

 but you need some other information， you need the probability of B marginalized over A。

 and this is quite useful in the sense of diagnostic test and we'll go over some examples here in a minute。



![](img/aa1aee68378eed9c9328c7cc054ae49a_6.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_7.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_8.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_9.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_10.png)

So let's talk about conditional probability in the context of diagnostic test。

 one of the most important examples of conditional probability and Bay's rule。

 let's let plus and minus be the be the event that the test is positive or negative。

 let's think of a test for a disease so plus being that the test says the person has the disease and minus being saying that they don't and then let's let D and D complementment be the event that the person either does or does not have the disease respectively。



![](img/aa1aee68378eed9c9328c7cc054ae49a_12.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_13.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_14.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_15.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_16.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_17.png)

Then the sensitivity is the probability that the test is positive。

 given that the subject actually has the disease， this would be a marker of a good test you would want the sensitivity to be high。



![](img/aa1aee68378eed9c9328c7cc054ae49a_19.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_20.png)

The specificity is the probability that the test is negative given that the subject does not have the disease。

 probability minus given D complement。

![](img/aa1aee68378eed9c9328c7cc054ae49a_22.png)

Again， you want the specificity to be high for a test to be good。



![](img/aa1aee68378eed9c9328c7cc054ae49a_24.png)

And notice in the development of diagnostic tests， these things are at least conceptually attainable。

 there's of course a lot of difficulties in finding good sensitivity and specificity estimates。

 but for example， in an HIV blood test you could take people who you know to have the disease and apply the diagnostic test to that blood you could also take people who you knew。



![](img/aa1aee68378eed9c9328c7cc054ae49a_26.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_27.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_28.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_29.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_30.png)

For sure did not have the disease， and you could apply the diagnostic test to the blood samples from those subjects。



![](img/aa1aee68378eed9c9328c7cc054ae49a_32.png)

If you happen to have a positive test， the number that is most of concern to you is the probability of having a disease given that positive test。

 the so called positive predictive value。

![](img/aa1aee68378eed9c9328c7cc054ae49a_34.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_35.png)

If you have a negative test， you're interested in the probability of not having the disease given that negative test。

 the so called negative predictive value。

![](img/aa1aee68378eed9c9328c7cc054ae49a_37.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_38.png)

We might say in the absence of a test， we might say the probability of having the disease is the so called prevalence of the disease。



![](img/aa1aee68378eed9c9328c7cc054ae49a_40.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_41.png)

Let's go through an example， a study comparing the efficacy of HIV test reports on an experiment which concluded that the antibody tests have a sensitivity of 99。

7 and a specificity of 98。5， so these are kind of made up numbers so don't think of these as cardinal truths about antibody tests for HIV。



![](img/aa1aee68378eed9c9328c7cc054ae49a_43.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_44.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_45.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_46.png)

Suppose that a subject from a population with a 0。1% prevalence of HIV receives a positive test result。



![](img/aa1aee68378eed9c9328c7cc054ae49a_48.png)

What is the associated positive predictive value？

![](img/aa1aee68378eed9c9328c7cc054ae49a_50.png)

So mathematically we want the probability of disease given a positive test result。

 given the sensitivity and the specificity and the prevalence P of D 。001。



![](img/aa1aee68378eed9c9328c7cc054ae49a_52.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_53.png)

So let's plug directly into Bay's rule， we want probability of disease given a positive test result。

 that's the probability of the positive test result。

 given disease times the probability of disease divided by this denominator right here。



![](img/aa1aee68378eed9c9328c7cc054ae49a_55.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_56.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_57.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_58.png)

And again。It's not immediately clear where the numbers from the problem are coming from here。

 but let's just note that the probability of a positive test result given that the person does not have the disease is one minus the probability of a negative test result given that the person does not have the disease or that's one minus the specificity and the probability of disease complement is one minus the probability of disease Now we've rewritten it only in terms of things that we know and we can just plug in the numbers and get 6% as our probability。



![](img/aa1aee68378eed9c9328c7cc054ae49a_60.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_61.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_62.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_63.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_64.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_65.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_66.png)

So in this population， a positive test result only suggests a 6% probability that the subject has the disease。



![](img/aa1aee68378eed9c9328c7cc054ae49a_68.png)

So in other words， the positive predictive value is 6% for this test。



![](img/aa1aee68378eed9c9328c7cc054ae49a_70.png)

The low positive predictive value in this case is largely due to the low prevalence of the disease。



![](img/aa1aee68378eed9c9328c7cc054ae49a_72.png)

However， imagine in the process of counseling this person about their positive test result。



![](img/aa1aee68378eed9c9328c7cc054ae49a_74.png)

The counselor learned that the subject was an intravenous drug user that routinely had intercourse with an HIV infected partner。



![](img/aa1aee68378eed9c9328c7cc054ae49a_76.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_77.png)

They would assume that the relevant prevalence for this person was much higher。

 and thus the positive predictive value was much higher。



![](img/aa1aee68378eed9c9328c7cc054ae49a_79.png)

I want to now distinguish between the component that is dependent on this prevalence and the component that。



![](img/aa1aee68378eed9c9328c7cc054ae49a_81.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_82.png)

Is what I would describe as the objective evidence of the positive test result。

 and that's what the diagnostic likelihood ratios are and that's what we'll cover next。



![](img/aa1aee68378eed9c9328c7cc054ae49a_84.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_85.png)

Here， I just give the formula for the positive predictive value again as it's plugged into Bay's rule。

 And remember， this formula then only depends on the sensitivity 1 minus the specificity and the prevalence of disease。



![](img/aa1aee68378eed9c9328c7cc054ae49a_87.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_88.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_89.png)

We can do the exact same thing for one minus this probability。

 one minus the positive predictive value， which is the probability of not having the disease given a positive test result。

 and you get this formula to the right。

![](img/aa1aee68378eed9c9328c7cc054ae49a_91.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_92.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_93.png)

Notice that the denominator is identical in either of the two probabilities。



![](img/aa1aee68378eed9c9328c7cc054ae49a_95.png)

And the numerator changes。

![](img/aa1aee68378eed9c9328c7cc054ae49a_97.png)

So if we were to divide these two equations， we get the following。



![](img/aa1aee68378eed9c9328c7cc054ae49a_99.png)

The probability of disease， given a positive test result divided by the probability of not having the disease。

 given a positive test result。 Whenever you take a probability and divide it by 1 minus that probability。

 you get the so called odds。 So here on the leftmost side。

 we have the odds of disease given a positive test result。 And on the rightmost side。

 we have the odds of disease in the absence of the test result。



![](img/aa1aee68378eed9c9328c7cc054ae49a_101.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_102.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_103.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_104.png)

Here， this factor in the middle is the diagnostic likelihood ratio of a positive test result。

 So the equation is the pret odds of disease times the diagnostic likelihood ratio equals the post test odds of disease。

 So in other words， the diagnostic likelihood ratio of a positive test result is the factor by which you multiply your odds in the presence of a positive test to obtain your post test odds。



![](img/aa1aee68378eed9c9328c7cc054ae49a_106.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_107.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_108.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_109.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_110.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_111.png)

So let's go through our example， suppose that a subject has a positive HIV test。

 if we calculate using our sensitivity and specificity from before。

 the diagnostic likelihood ratio works out to be 0。997 divided by 1 minus 0。

985 which works out to be 66。

![](img/aa1aee68378eed9c9328c7cc054ae49a_113.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_114.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_115.png)

In other words。No matter what your pretest odds are。

 you multiply them times 66 to obtain your postt odds， or in other words。

 the hypothesis of disease is 66 times more supported by the data than the hypothesis of no disease。



![](img/aa1aee68378eed9c9328c7cc054ae49a_117.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_118.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_119.png)

Now， if the pretest odds are very small， then still multiplying them by 66 will result in a still small number。

 though 66 times larger。

![](img/aa1aee68378eed9c9328c7cc054ae49a_121.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_122.png)

Let's just very quickly go over an instance when a subject has a negative test result in using the DLR minus。

 so in this case the DLR minus from the sensitivity and specificity given before is 0。003。



![](img/aa1aee68378eed9c9328c7cc054ae49a_124.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_125.png)

So therefore， your post test odds of disease in the light of a negative test result is now 0。

3% that of the pretest odds of the disease， or in other words。

 the hypothesis of disease is supported 0。003 times that of the hypothesis of the absence of disease given the negative test result。



![](img/aa1aee68378eed9c9328c7cc054ae49a_127.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_128.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_129.png)

![](img/aa1aee68378eed9c9328c7cc054ae49a_130.png)