# 杜克大学《R语言数据分析（R语言、概率与数据入门，推断统计，线性回归与建模）｜Data Analysis with R》中英字幕 p23 23_06_05_贝叶斯推断示例.zh_en -BV1Cf421q7mU_p23-

American Cancer Society estimates that about 1。7% of women have breast cancer。Susan G。

 Coman for the Cure Foundation states that mammography correctly identifies about 78% of women who truly have breast cancer。

An article published in 2003 suggests that up to 10% of all mammograms are false positive。

These probabilities are， of course， estimates as they're very difficult to calculate precisely。

 but we're going to take these as givenons for this example。As usual。

 let's first parse through the percentages we' given。

The probability of having breast cancer is estimated to be 0。017。The probability of testing positive。

 given that somebody has breast cancer is 0。78， and the probability of testing positive。

 even though somebody does not have breast cancer is 0。10。

Prior to any testing and any information exchange between the patient and the doctor。

 what probability should a doctor assign to a female patient having breast cancer？

Since we don't know anything about this patient's medical history。

 our best bet is to treat them like a randomly chosen person from the population。

 hence we would set this probability at 。017。This is the prior probability we assign to a patient having breast cancer before we collect data on them。

 in other words， before we test them。When a patient goes through breast cancer screening。

 there are two competing claims patient has cancer or and patient doesn't have cancer。

 if a mammogram yields a positive result， what is the probability that patient has cancer？

If we think about this imp probabilityability notation。

 we're being asked to find what is the probability of breast cancer。

 given that the patient tested positive and earlier on we were provide the reverse of this probability positive given breast cancer and when we have the conditions reversed we know that a probability tree might be useful in our calculations。

 so let's start building that there are two competing claims patient has breast cancer or patient does not have breast cancer the probability of having breast cancer are prior is 0。

017 so the probability of note having breast cancer is going to be the complement of that one minus0。

017。983。If a patient has breast cancer， there are two possible outcomes they might test positive or they might test negative。

 The probability of testing positive when the patient has breast cancer is 0。78。

 the probability then of testing negative when the patient has breast cancer is going to be the complement of 0。

780。22。Similarly， when a patient does not have breast cancer， there are two possible outcomes。

 testing positive or negative probability of testing positive。

 even though the patient does not have breast cancer is the 0。10 that we were given earlier。

 so the accuracy rate of the test when the patient does not have breast cancer， or in other words。

 the probability of testing negative， given no breast cancer is going to be the complement of 0。100。

90。We know that we're given that the patient has tested positive。

 so really we're only interested in the first and the third branch here。

 so we don't even have to worry about the other branches because we know the patient we're interested in doesn't come from the act of the population that tested negative。

First， we're going to want to find the joint probabilities the probability of breast cancer and positive is the product of 0。

017 and 0。78， that's 0。01326， and the probability of no breast cancer and positive is the product of the probabilities in the two branches leading up to that 0。

0983。We are asked for the probability of breast cancer given positive。Using Bays theorem。

 this is going to be the probability of breast cancer and positive。

 divided by the probability of testing positive。The numerator is simply coming from our top branch and the denominator。

 the probability of testing positive， is going to be the sum of breast cancer and positive。

Or no breast cancer and positive。 Since these are two disjoint outcomes。

 we add the two probabilities when we're saying， or this gives us about a 12% rate。 This。

 remember is what we call our posterior probability。 Initially， we had given a 1。

7% chance to this patient having breast cancer because we knew nothing about them。

 Then we tested them。 and they tested positive。 So now we have this additional information about the patient。

 Now， after data collection。 The probability that we're assigning to this patient having breast cancer is slightly higher。

 It's a 12%。Since a positive mammogram doesn't necessarily mean that the patient actually has breast cancer。

 the doctor might decide to retest the patient， what is the probability of having breast cancer if the second mammogram also yields a positive result？

Once again， we run through our probability treat to competing claims breast cancer and no breast cancer。

 However， what has changed now is that this patient is no longer a nobody from the population。

 We've tested them once， and they tested positive。 So we have some additional information about them。

 and we should update our prior with this additional information。 In other words。

 we plug in the posterior from the previous iteration。 the previous test to be our new prior。

 and therefore， the probability of not having breast cancer is updated to be the complement of this 88%。

Next， we can run through our tree again。 remember nothing about the test has changed。

 so the probability of testing positive， given a patient has breast cancer is still 78% and the probability of testing negative。

 given the patient has breast cancer is still 22% Similarlyly with the lower branch。

 nothing about the test is changed So the conditional probabilities of testing positive or negative。

 given the patient does not have breast cancer is still 10% and 90% respectively。 Once again。

 we're only interested in the branches where the patient has tested positive because we're saying that the second mammogram also yielded a positive result。

 we can multiply through the branches is to find our joint probabilities。

 and these are going to change a little bit because our starting probabilities。

 the probabilities in the first branch has changed and this time our probability of having breast cancer and testing positive is higher。

At 。0936 and our probability of no breast cancer in positive is 0。088。🎼In this example。

 we have reviewed a Bayesian approach to statistical inference， which involves setting it prior。

 collecting data， obtaining a posterior， and updating the prior with the posterior from the previous step。

 In addition， we got some practice working with conditional probabilities。

 probability trees and the Bay theorem in general。

![](img/cc04f06477af420ea5a196c92e0dc83b_1.png)

![](img/cc04f06477af420ea5a196c92e0dc83b_2.png)