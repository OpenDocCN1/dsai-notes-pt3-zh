# 吴恩达《机器学习工程师的生产实践（MLOps）Machine Learning Engineering for Production》中英字幕 - P31：30_人类水平表现.zh_en - GPT中英字幕课程资源 - BV1pi4y167g5

Some machine learning tasks are trying to predict an inherently ambiguous output。

 and human level performance can establish a useful baseline of performance as a reference。

But human level performance is also sometimes misused let's take a look one of the most important uses of measuring human level performance or HLP is to estimate base error or irreducible error。

 especially on unstructured data tasks in order to help with error analysis and prioritization。



![](img/5a69dcf8724f1e681ef084af684bcd21_1.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_2.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_3.png)

And just to establish what might be possible take a visual inspection task this may have happened to you before。

 but I have gotten requests from business owners saying， hey Andrew。

 can you please build a system that's 99% accurate or maybe 99。

9% accurate So one way to establish what might be possible would be to take a data set and look at the ground truth data。

 say you have six examples where the ground truth label is these and then to ask a human inspector to label the same data blinded to the ground truth label of course。



![](img/5a69dcf8724f1e681ef084af684bcd21_5.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_6.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_7.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_8.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_9.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_10.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_11.png)

And see what they come up with and if they come up with these。

 you would say this inspector agreed to the ground truth on four other six examples。



![](img/5a69dcf8724f1e681ef084af684bcd21_13.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_14.png)

And disagreed on two out of six， and so human level performance is 66。7%。



![](img/5a69dcf8724f1e681ef084af684bcd21_16.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_17.png)

And so this would let you go back to the business owner and say， look。

 even your inspector is only 66。7% accuracy， how could you expect me to get 99% accuracy so HP is useful for establishing a baseline in terms of what might be possible。



![](img/5a69dcf8724f1e681ef084af684bcd21_19.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_20.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_21.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_22.png)

There's one question that is often not us， which is what exactly is this ground truth label。

 because rather than just measuring how well we can do compared to some ground truth label。



![](img/5a69dcf8724f1e681ef084af684bcd21_24.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_25.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_26.png)

Which was probably written。By some other human。

![](img/5a69dcf8724f1e681ef084af684bcd21_28.png)

Are we really measuring what is possible or are we just measuring how well two different people happen to agree with each other？



![](img/5a69dcf8724f1e681ef084af684bcd21_30.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_31.png)

When the ground truth label is itself determined by a person。



![](img/5a69dcf8724f1e681ef084af684bcd21_33.png)

There's a very different approach to thinking about human level performance。

 which I want to share with you in this and the next video。



![](img/5a69dcf8724f1e681ef084af684bcd21_35.png)

Beyond this purpose of estimating Bay error and establishing what's possible using that to help with error analysis and prioritization。

 here are some other uses of human level performance in academia HLP is often used as a respectable benchmark and so when you establish that people are only 92% accurate or some of the number on a speech recognition data set and if you can beat human level performance then that establishes then that helps you to quote proof。



![](img/5a69dcf8724f1e681ef084af684bcd21_37.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_38.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_39.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_40.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_41.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_42.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_43.png)

That your learning algorithm is doing something hard and helps get the paper published I'm not saying this is a great use of HLP。



![](img/5a69dcf8724f1e681ef084af684bcd21_45.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_46.png)

But in academia。

![](img/5a69dcf8724f1e681ef084af684bcd21_48.png)

Showing you can beat HLP， maybe for the first time， has been a tried and true formula。



![](img/5a69dcf8724f1e681ef084af684bcd21_50.png)

For establishing the academic significance of a piece of work and helps with getting something published。



![](img/5a69dcf8724f1e681ef084af684bcd21_52.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_53.png)

We discussed briefly on the last slide what to do if a business or product owner asks for 99% accuracy and if you think that's unrealistic。

 then measuring HLP may help you to establish a more reasonable target there's one other use of HLP that you might hear about then I'll be cautious about which is I've seen many projects with a machine learning team wants to use HLP or beating HLP to prove that the machine learning system is superior to the humans doing the job and as tempting as it is to go to someone and says。

 look， I've proved that my machine learning system is more accurate than humans inspecting the phones or the radiologist reading Xrays or something and now that I've mathematicalmaticly proved the superiority of my learning algorithm you have to use it right I know the logic of that is tempting but as a practical matter this approach rarely works and you also saw last week that。



![](img/5a69dcf8724f1e681ef084af684bcd21_55.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_56.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_57.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_58.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_59.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_60.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_61.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_62.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_63.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_64.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_65.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_66.png)

Businesses need systems that do more than just doing well on average test set accuracy。

 So if you ever find yourself in this situation， I would urge you to just use。



![](img/5a69dcf8724f1e681ef084af684bcd21_68.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_69.png)

This type of logic with caution or maybe even more preferably just don't use this arguments I've usually found other arguments than this to be more effective that working with a business to see if they should adopt a machine learning system。



![](img/5a69dcf8724f1e681ef084af684bcd21_71.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_72.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_73.png)

The problem with beating human level performance as proof of machine learning superiority。



![](img/5a69dcf8724f1e681ef084af684bcd21_75.png)

Is multifold beyond the fact that most applications require more than just high average test accuracy。



![](img/5a69dcf8724f1e681ef084af684bcd21_77.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_78.png)

One of the problems with this metric is that it sometimes gives a learning algorithm an unfair advantage when labeling instructions are inconsistent。

 let me show you what I mean if you have inconsistent labeling instructions so that when an audio clipse says oh nearest gas station。



![](img/5a69dcf8724f1e681ef084af684bcd21_80.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_81.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_82.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_83.png)

Let's say， 70% of laborers。

![](img/5a69dcf8724f1e681ef084af684bcd21_85.png)

Use the sleepinging convention。And 30% of laborers。



![](img/5a69dcf8724f1e681ef084af684bcd21_87.png)

Use this labeling convention neither one is the superiors transcript to the other。

 both seem completely fine， but just by luck of the draw， 70% of labelers choose the first one。

 30% choose the second one so if the ground truth is established by a labeler maybe just a labeler with a slightly bigger title。

 but really by one labeler。

![](img/5a69dcf8724f1e681ef084af684bcd21_89.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_90.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_91.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_92.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_93.png)

Then the chance that two random laborers will agree。



![](img/5a69dcf8724f1e681ef084af684bcd21_95.png)

Will be。0。7 squared plus 0。3 squared。

![](img/5a69dcf8724f1e681ef084af684bcd21_97.png)

Which is 0。58。So if you had two labelers use the first convention， there's a 0。

7 square chance of that， or if both of your random labelers use the second convention， there's a 0。

3 squared chance of that， then the two of them will agree。

 so the chance of two labelers agreeing is 0。58 and in the usual way of measuring human level performance。

 you will conclude that human level performance is 0。58。



![](img/5a69dcf8724f1e681ef084af684bcd21_99.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_100.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_101.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_102.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_103.png)

But what you're really measuring is the chance of two random labels agreeing this is where a machine learning algorithm has an unfair advantage。



![](img/5a69dcf8724f1e681ef084af684bcd21_105.png)

I think either of these labeling conventions is completely fine。

 but if the learning algorithm is a little bit better at gathering statistics of how often ellipses versus commas are used in such a context。

 then a learning algorithm may be able to always use the first labeling convention because it knows that statistically it has a 70% chance of getting it right if it uses ellipses or dot dot dot。

 so a learning algorithm will agree with humans 70% of the time。



![](img/5a69dcf8724f1e681ef084af684bcd21_107.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_108.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_109.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_110.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_111.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_112.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_113.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_114.png)

Just by choosing the first laing convention， but this 12% improvement in performance。

 whereas human level performance is 58%。

![](img/5a69dcf8724f1e681ef084af684bcd21_116.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_117.png)

And your learning algorithm is 12% better is 0。70 this 12% better performance is not actually important for anything between these two equally good slightly arbitrary choices the learning algorithm just consistently picks the first one so it gains what seems like a 12% advantage on this type of on this type of query but is not actually outperforming any human in any way that a user would care about and one side effect of this is that。



![](img/5a69dcf8724f1e681ef084af684bcd21_119.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_120.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_121.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_122.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_123.png)

If your speech reation task has multiple types of audio， for some， there's this dot dot。

 dot or ellipses versus calm ambiguity and the learning algorithm does 12% better on this。



![](img/5a69dcf8724f1e681ef084af684bcd21_125.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_126.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_127.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_128.png)

If your're learning algorithm make some more significant errors on other types of input audio。

 then when is performance。

![](img/5a69dcf8724f1e681ef084af684bcd21_130.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_131.png)

Where it actually does worse could be averaged out by queries like these where kind of fake looks like it's doing better and this will therefore mask or hide the fact that you're learning algorithm is actually creating worse transcripts than humans actually are and what this means is that a machine learning system can look like it's doing better than HLP。

 but actually be producing worse transcripts than people because it's just doing better on this type of problem which is not important to do better on while potentially actually doing worse on some other types of input audio。



![](img/5a69dcf8724f1e681ef084af684bcd21_133.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_134.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_135.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_136.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_137.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_138.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_139.png)

![](img/5a69dcf8724f1e681ef084af684bcd21_140.png)

Given these problems with human level performance， what are we supposed to do。

 measuring human level performance is useful for establishing a baseline using that to drive error analysis and prioritization。

 but using it to benchmark machines and humans sometimes runs into problematic cases like this。

I found that when my goal is to build a useful application， not publish a paper， you publish a paper。

 let's prove we can outperform people that helps published paper。

 but found that when my goal is to build a useful application rather than trying to beat human level performance。

 I found that is often useful to instead try to raise human level performance because we raise human level performance by improving label consistency and that ultimately results in better learning algorithm performance as well。

😊，Let's take a deeper look at this in the next video。

