# 吴恩达《自然语言处理｜natural language processing》中英字幕 - P66：16_计算概率.zh_en - GPT中英字幕课程资源 - BV1Hc5ezDEWQ

![](img/35e7650f1feabce140be2c3b7896e9fe_0.png)

Hi again。You'll now learn how to compute the probabilities for your transition and emission matrices。

 given the corpus， youll be able to populate these two matrices。 Let me show you how you can do this。

Let's start with how to populate the transition matrix。

 which holds all the transition probabilities between states of your Markov model。 First。

 let's explore how to calculate the transition probabilities on a conceptual level using this very small training corpus as you can see the associated part of speech tags are depicted by the background color to calculate the transition probabilities。

 you actually only use the parts of speech tags from your training corpus so to calculate the probability of the blue part of speech tag transitioning to the purple one you first have to count the occurrences of that tag combination in your corpus。

Which is 2。 The number of all tag pairs starting with a blue tag is 3 for this corpus， at least。

So two out of three tag sequences in your training corpus start with the blue parts of speech tag。

 In other words， the transition probability for a blue tag following a purple one is2 out of3 more formally in order to calculate all the transition probabilities of your markov model you'd first have to count all occurrences of tag pairs in your training corpus I'll define this as the function C of the tags ti-1 comma T which returns the count for the tag T-1 followed by the tag T in your training corpus Next。

 you calculate the probability of a tag T following another tag T-1 as P of T given T-1 This is count of T-1 comma T in the numerator which is the number of occurrences of ti-1a T in the。

Divided by the sum of all occurrences of the tag T -1 together with all the other tags Tj this will become more clear in the following slides。

 I'll write this as P for the probability of T I given T -1 this probability is given by the total number of times tag T I occurred after tag T-1。

 which is given by the function counts of T comma T-1 in the numerator。

And then divided by the number of total occurrences of the tag T I-1， given by the function。

 count of T-1 in the divisor So say you want to train a model for haiku。

 a type of short Japanese poetry。 your training corpus will be the following Haiku from iszra pound written in 1913 in the programming assignment you will be given a prepared corpus here。

 youll make some changes to the corpus in order to calculate the correct probabilities consider each line of the corpus as a separate sentence。

 First， as they start token to each line or sentence in order to be able to calculate the initial probabilities using the previous defined formula。

 Then Trans all words in the corpus to lowercase。 So the model becomes case in sensitive。

 the punctuation you should leave intact。 because it doesn't make a difference for a toy model。

 and there aren't tags for different kinds of punctua。Included here。

 So there you have it a nicely prepared corpus。 You learned how to calculate the probability of a tag showing up after another tag。

 You saw how you can get the counts， and then you can use those counts and transform them into probabilities。

 This is useful because it allows you to populate your transition matrix。

 This is what you' will be learning next。😊。

![](img/35e7650f1feabce140be2c3b7896e9fe_2.png)