# 图宾根大学《概率和统计机器学习｜Tubingen Probabilistic and Statistical Machine Learning 2020》中英 p50 -50-Part 47 - ML and Society_ Formal approaches to fairness.zh_en -BV1gso5YGE4s_p50-

![](img/c2eaeddd7e46763e38a3380e48c3d729_0.png)

In the last part of the lecture we have seen that more or less all applications of machine learning that we can think of when machine learning is being deployed in a context of society are biased in one or the other way and now we want to discuss what are the different sources where can all these bias come from because it's important to understand first of all where does the bias come from to then later on develop some tools where we at least might be able to reduce a bit of the bias in the machine learning applications。



![](img/c2eaeddd7e46763e38a3380e48c3d729_2.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_3.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_4.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_5.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_6.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_7.png)

The first source of bias is data and measurement。

![](img/c2eaeddd7e46763e38a3380e48c3d729_9.png)

And the first source of unfairness that I want to mention is there are two notions of unfairness which come from minorities in the data。

 so if you have a population which consists of a large majority and then a small minority。

 it often can happen that this minority is not represented well in your data。

 and there are two different reasons for this。

![](img/c2eaeddd7e46763e38a3380e48c3d729_11.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_12.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_13.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_14.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_15.png)

The first of all is simply because the minority is so small if you try to measure the test accuracy of a system。

 this minority might simply be drowned in this small fraction where results are not accurate so consider you have a population consisting of 1% maybe this a particular disadvantaged people and you want to make sure that your classification algorithm doesn't isn't unfair to these disadvantaged people but now it's just 1% of your population and your classification accuracy maybe of the system。

 if you train it on the rest of the population is I don't know。

 92% now if it's completely inaccurate on this1 percent minority you maybe have an accuracy from 91 instead of 92% so it's just 1% that goes down and this is something that is hard to measure data so it could be that your whole system is completely wrong on this minority。

😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_17.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_18.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_19.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_20.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_21.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_22.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_23.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_24.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_25.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_26.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_27.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_28.png)

You don't even realize it because this minority is so small。So。

 this is one thing to keep in mind if you have a minority。

 you might want to test your algorithm independently for this particular minority。😊。



![](img/c2eaeddd7e46763e38a3380e48c3d729_30.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_31.png)

And not just look at the overall accuracy， which is dominated by the majority of the population。



![](img/c2eaeddd7e46763e38a3380e48c3d729_33.png)

The other thing is that these minority groups might even be even I mean they are small already。

 but they might even be underrepresented in relative to the population statistics due to your sampling bias that you might have so it might be that you have a minority that has1% of the population。

😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_35.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_36.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_37.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_38.png)

But in your particular sample， you might maybe it's just 0。

01% of the data because you have so many samples of this population。

 and this can happen for many structural reasons。

![](img/c2eaeddd7e46763e38a3380e48c3d729_40.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_41.png)

Then of course， this problem that I just said before is even worse because in your test data you have not only the small population fraction that corresponds to the size of the population。

 but you might even have a smaller test and a number of test points from this particular population。

😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_43.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_44.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_45.png)

Sampling bias， this is something that you probably would always have。

Your data collection might have demographic， geographical behavioral or temporal biases。😊。

And certain groups will over be over or underrepresented and this essentially it's very difficult at least if the data is not if you don't try to get stratified samples or something like that。

😊，Typically， it's the case that you have these biases。I just want to show you one particular example。

It's again about crime and crime statistics。 So the record of crimes only comes from crimes observed by the police。

 of course， like if a crime happens and nobody notices it， it doesn't enter the statistics。 Now。

 the police departments tend to dispatch more police officers to places where they find that there is a high risk of crime happening in this particular place。

But now， because more police officers on this area。

 they might even observe more crimes in this area because simply there are many more policemen who could observe it。

😊，So and even now， if the police believes theres a certain quarter in the city where theres lots of crimes happening。

 they send more people， they observe more crimes， but it might be the case that in fact there are not more crimes at all in this particular area just because there are more policemen who in principle could watch more of the crimes and get aware of them。

😊，So in this sense you would have as samplingmbling bias which is of course not intended。

 but which can have very strong biases regarding different quos， for example， in your city。😊。

The same happens in many cases， I mean asmbling bias。

 like if you have online customers like you have different customers in the morning than in the evening。

 if I make an evaluation of my lecture in around midterm。

 then the people who have already lost left my lecture because they found it so terrible。

 they are not part of the evaluation anymore， so I think sort of the worst evaluation like the worst parts or the worst comments don't even enter my evaluation anymore。

😊，There are many of these biases or in the compass example， I have mentioned that before。

 like if you want to compute the score of whether someone reoff or not。

 of course you can only observe that if this person has been released。

 so if the person has not been released， we we cannot even measure whether this person would have re offended or not。

There might be also on top of the sampling bias， might be preexisting biases in your data。😊。



![](img/c2eaeddd7e46763e38a3380e48c3d729_47.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_48.png)

And we have seen examples like gender roles in the text。

 if we look at these kind of word embedding examples or in the past hiring data， which might be。



![](img/c2eaeddd7e46763e38a3380e48c3d729_50.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_51.png)

Problematic if because women tended to work less or tend to。

 or the foreign pupils tended to have a lower qualification。 So in this case。

 you have these biases in the past， and it's very hard to get these biases out of the data if you want to apply machine learning。



![](img/c2eaeddd7e46763e38a3380e48c3d729_53.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_54.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_55.png)

Then there is also many sources of unfairness which come from measurement。嗯。

And the problem is or the question we need to ask us is which features do we measure there as a typepo sorry。

 which features do we measure and how do we measure these features？😊。

And this is something that sounds naive， but in fact this is also something that in like sociology or so is being debated quite a lot。

 the way you define features is also a way by which you think about certain categories so for example。

 in the US it's common to collect statistics according to race and typically you get ask for categories like African American。

 Hispanic， Asian and so on。And then their gender category is something like self identified， male。

 self identified female。And the problem is， of course， if you measure these kind of statistics。

 I mean， first of all， people might not answer truthfully， I mean they。I typically don't know。

 I mean， if if someone asks me in a questionnaire to give my raise， I tend not to answer it。

 And if I have to， then maybe I just do a random choice。

There might be categories where people might not even be able to answer truthfully because you're forced to choose a label and none of these labels applies to you。

😊，And performing these categories， they become normative。

 so how we measure a concept changes the way how we think about a certain concept。

And so by selecting the features， we influence the way by which we model the problem， of course。😊。

And sort of this selection of measurements might systematically favor or disfavour certain groups in your population。

 even if you don't desire it， but it simply happens because this way of measurement is unfair to certain parts of your population。

And this is again something that will or will very often happen。

 so you need to think really very carefully about which kind of measurements you take and which kind of biases you might introduce by taking these kind of measurements。

😊，The other thing is not only the measurement of your input features。

 but also the measurement of your target features。

![](img/c2eaeddd7e46763e38a3380e48c3d729_57.png)

So in the end machine learning always tries to optimize a certain criterion。

 you want to learn a function that fits some target variable。



![](img/c2eaeddd7e46763e38a3380e48c3d729_59.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_60.png)

And in a social context， this target value is often not so well defined。 It's difficult。

 How do you measure the thing you want to measure。😊。



![](img/c2eaeddd7e46763e38a3380e48c3d729_62.png)

And often you can't really measure what you interested and you can just choose a very。

 very cost proxy of what you would like to measure。😊。



![](img/c2eaeddd7e46763e38a3380e48c3d729_64.png)

And here are a couple of examples。

![](img/c2eaeddd7e46763e38a3380e48c3d729_66.png)

So for example， you want to evaluate whether somebody should promote， be promoted in his job。



![](img/c2eaeddd7e46763e38a3380e48c3d729_68.png)

So your target variable is sort of a good employee， but how do you measure when is an employee。

 a good employee and if you want to sort of train on past records of your employees how do you I mean you have the data of everybody but how do you define what this target variable is？

😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_70.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_71.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_72.png)

嗯。

![](img/c2eaeddd7e46763e38a3380e48c3d729_74.png)

And in particular， I mean， one thing you could do is you could look at your past data and maybe people have been evaluated by the managers。

😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_76.png)

And then you can take those scores as the proxy， but of course this manager might have had biases at well。

 maybe he didn't like females and there you go all the females have a lower score according to your manager and this bias of course is going to be transmitted to your future data。

😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_78.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_79.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_80.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_81.png)

A hiring example。So you might， instead of relying on a performance reviews for like you want to hire someone for a sales job or promote or whatever。

😊，And instead of relying on reports， you might simply say I take some objective numbers。

 I simply check how many sales did this particular person close。And it sounds very objective。

 but of course， now this depends on the particular circumstances in this customer like and like。

There might be customers who are more responsive than others。

 there might be areas where it's easier to sell things in other areas there might be workplace conditions where it's easy。

 easy to perform well and there might be work conditions so it's very hard to perform well and it's really so for example if you evaluate a school and you want to say this is a good school depending on how many high school degrees sort of come out of the school it of course depends a lot in which area of the city the school is how much money did it receive。

 what is the population in the school， which kind of teachers are going to work in the school so all these things are going to evaluate or。

To enter your your criterion。 So it's really hard to objectively measure what you're really interested in。

Another example， computer vision。There were these systems or I think they are there around still。

 I mean， people played a lot with these kind of computer vision tasks and for example。

 there was a system that was supposed to rank physical attractiveness So you show a picture of a person and you want to say is this person attractive or not。

😊，And now what happened， I mean， the training data typically consisted of you show some。

 you have some pictures and you show them to some human， the human rates。

 the attractiveness on I don't know on a scale from 1 to 10 or so。And this is your training later。

And what happened， most of these people who evaluated this data who generated the strain data were male。

 they were white， and of course what comes out then is that the lighter skin comes out of the system as being more attractive。

😊，But this is， of course bullit it's just because of the way we generated these labels of the target value。

That there is the strong bias。Here's another more thing in health systems。

 so this is a quote I took this sources on the next slide。

 healthal systems rely on commercial prediction algorithms to identify and help patients with complex health needs。

😊，We show that's the authors which are cited on the next slide。

That a widely used algorithm affecting millions of patients exhibits significant racial bias and a given risk score。

Black patients are considerably sicker than white patients。

evidenced by signs of uncontrolled illness， so again。

 so you know what happens here is there is an automatic system and it tries to predict the risk score。

It's a bit like encompassas and now at a given risk score black patients。😊。

The sentences here are considerably sicker than white patients。😊。

So which means that to obtain the same kind of treatment。

 a black patient needs to be even more sick than a white patient before he gets so she gets the treatment。

Remedying this disparity would increase a percentage of black patients receiving additional help from 17% to 46%。

The bias arises because the algorithm predicts health care costs rather than illness and here here we go。

 this is sort of the proxy variable so it's hard to predict illness。😊。

But you can predict the health care costs。But unequal access to care means that we spend less money caring for black patients than for white patients。

Thus， despite health care costs appearing to be an effective proxy for healths by some measures of predictive accuracy。

Large racial biases arise， we suggest that the choice of convenient。

 seemingly effective proxies for ground truth。😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_83.png)

Can be an important source of algorithmic bias in many contexts。



![](img/c2eaeddd7e46763e38a3380e48c3d729_85.png)

So here is see it again here now we have a healthcare system and depending on how you measure the success of your system and which variables you take you come come to completely different conclusions and also different biases。

😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_87.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_88.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_89.png)

So again we are still in the chapter of fairness， it is not a technical requirement but it's one that comes from society and my takeaway is here nothing about fairness is really simple。

 I mean there are these different notions of fairness。

 all of them are not compatible with each other， the data contains errors the target variables contains errors or biases in the measurement and it's really。

 really hard to get these biases out and it's sort of inconceivable to have an application。😊。



![](img/c2eaeddd7e46763e38a3380e48c3d729_91.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_92.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_93.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_94.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_95.png)

That happens in some context of society， which doesn't have any of these biases。



![](img/c2eaeddd7e46763e38a3380e48c3d729_97.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_98.png)

What I want to do now is I want to show you some of the most popular definition for bias machine for in machine learning systems simply so you have seen this definition again I'm going to rely a lot on the book。

 the fairML book， you can read it up more closely if you like again these are just overview slides I simply want you to be familiar with these notions without diving too much into technical issues here。

😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_100.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_101.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_102.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_103.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_104.png)

Okay， what is our setup？Our data consists of features like you describe people， and it's their age。

 the gender if gender is not or。😊，Depending on whether you consider gender as a sensitive attribute or not how many children they have。

 what is the income and so on， so you have features that describe a person or whatever the object is you're currently looking at。

And then you have what is always called in the literature， the protective or the sensitive attribute。

And in my slides， I always call this A。The attribute。

And this could be the one for which you want to correct or want to try to be as fair as possible。

 so you want to be fair with respect to race， for example。

 or fair with respect to gender or some other category that you come up with。

And now depending on the application， this protected attribute can be known or not。

 so in some applications， it is an explicit feature in some others it is not an explicit feature。

Then we assume that we have a true target variable and here we don't really discuss whether this is now a proxy or not we simply I mean for now we simplify the setting and say we can really measure the success of our system and it is being measured by this variable why。

😊，Whats our goal， our goal is to learn a classifier that takes the input。😊。

Both the features and the attract and the sensitive attribute are sometimes also without the sensitive attribute depending on the application。

 so you take the features and you want to predict the outcome。The target very wide。

And now I mean simply to make the exposition on the next slide very simple。

 we always assume that the protected attribute is binary， so male， female， white， black。

 this is of course a strong simplification， but simply it's simpler to treat on the slides。😊。

We also assume that the true outcome is binary， so you admitted to college or you're not。

 you're released or you're not released and so on。😊。

And simply just to recap what in the different examples are these variables to have something in mind when we think about these categories。

 so in the compass example， X are the features of the person。😊。



![](img/c2eaeddd7e46763e38a3380e48c3d729_106.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_107.png)

Say the crime record， the education， whatever like the past historyory of the person。



![](img/c2eaeddd7e46763e38a3380e48c3d729_109.png)

A is the feature whether the person is white or black。

 That's the sensitive attribute that we do not want to use in this case。



![](img/c2eaeddd7e46763e38a3380e48c3d729_111.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_112.png)

Why is the label whether or is the variable that describes whether a person would re offend。

 and here we simply assume we would know the ground truth even though， of course in practice。

 maybe this is hard to know。

![](img/c2eaeddd7e46763e38a3380e48c3d729_114.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_115.png)

And why hat is now the prediction of the system， whether the system thinks that this person is going to reoffend or not。



![](img/c2eaeddd7e46763e38a3380e48c3d729_117.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_118.png)

Again， this is what I want to stress it here once more。

 but then we forget about this in this chapter。😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_120.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_121.png)

Everything here is a very poor proxy， I mean， the actual data X。

By which we describe the person has millions of measurement biases as we outlined before。



![](img/c2eaeddd7e46763e38a3380e48c3d729_123.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_124.png)

The sensitive attributes are often not even known， they might be really defined if it's about gender。

 they might be misreported and they might be simply infer from something else because we don't know it。



![](img/c2eaeddd7e46763e38a3380e48c3d729_126.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_127.png)

The classifier is hard to understand。We can't really argue about it。

 And why is' often a poor proxy of the variable we actually want to measure。 So this is all。

 of course， happening in the background。 But for now。



![](img/c2eaeddd7e46763e38a3380e48c3d729_129.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_130.png)

Let's look at the problem。

![](img/c2eaeddd7e46763e38a3380e48c3d729_132.png)

When we forget about these biases and still try to in the optimal circumstances when we know the variables and then there are no measurement biases and so on whether we can then create a fair classifier and if not then we are doomed to do it in this kind of more complicated scenario anyways。

 and if yes it's interesting to see how it works。😊。



![](img/c2eaeddd7e46763e38a3380e48c3d729_134.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_135.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_136.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_137.png)

Now we need to measure the notion of fairness and as we've seen there are many different notions and they are not compatible and this is what I want to show you now。

😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_139.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_140.png)

The first notion of fairness， which is sort of nearly。

 I would always call it an Eve notion of fairness is what is often being called demographic parity。😊。



![](img/c2eaeddd7e46763e38a3380e48c3d729_142.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_143.png)

And in the Ferham L book， it's called Independence。

 but I like demographic par much more and I think it's the more common word for this phenomenon。



![](img/c2eaeddd7e46763e38a3380e48c3d729_145.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_146.png)

Formerally， demographic parity is defined as follows。

The probability to achieve outcome that the system predicts outcome plus one。



![](img/c2eaeddd7e46763e38a3380e48c3d729_148.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_149.png)

If your sensitive attribute is plus 1， should be the same as if the probability that the prediction is plus1 if your sensitive attribute is 0。

😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_151.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_152.png)

So independently of everything else， both groups should have the same rate of success。

 so y equals one is here always sort of one means success for example you are being admitted to college or you are being released from jail。



![](img/c2eaeddd7e46763e38a3380e48c3d729_154.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_155.png)

And now the probability， for example， to be admitted to college should be independent of whether your race is black or white。

 for example。😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_157.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_158.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_159.png)

And here examples is the same so here have the same proportion of males and females should be promoted like if you are in a company and you look at promotion the same number of males and females should be promoted and here I wrote again the variables so the fact whether you're male or female。

😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_161.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_162.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_163.png)

It's not the sensitive attribute A， and whether you promote it or not is the variable Y hat。😊。



![](img/c2eaeddd7e46763e38a3380e48c3d729_165.png)

Or like in this compass example， the same proportion of white and black people should be released on pale。



![](img/c2eaeddd7e46763e38a3380e48c3d729_167.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_168.png)

The definition I have here on this previous slide sort of relies on the fact that we have binary variables。

 you can have a more general definition that also holds in a much more general context。

 and the definition simply says the random variable Y hat and a need to be independent and this is typically denoted by this sort of。

😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_170.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_171.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_172.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_173.png)

Orhogonality sign。 So from a statisticalt or stochastic point of view。

 if you consider these two as random variables， they should be independent according to the definition of two independent random variables。



![](img/c2eaeddd7e46763e38a3380e48c3d729_175.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_176.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_177.png)

Now， this demographic parity assumption or like the whether if you want to go for a demographic parity。

 this is very a very， very strong assumption。😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_179.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_180.png)

Because typically， I mean， if you want to like。

![](img/c2eaeddd7e46763e38a3380e48c3d729_182.png)

Here again we want that these two like the predicted variable and the sensitive attribute is independent and of course you also want that the true variable and the sensitive attribute is sort of like sorry you want that the predicted variable and the true variable are pretty close to each other so it also essentially means this is only going to work if the true variable and this variable A are independent of each other and this is really really a strong assumption。



![](img/c2eaeddd7e46763e38a3380e48c3d729_184.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_185.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_186.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_187.png)

So whenever you have an example。

![](img/c2eaeddd7e46763e38a3380e48c3d729_189.png)

Where you have a correlation between what you want to predict and this attribute that you want to protect。

 then demographic parity is not really going to work well。



![](img/c2eaeddd7e46763e38a3380e48c3d729_191.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_192.png)

And maybe you can try to think about some examples， lean back for a minute。

 try to come up with an example where this is really problematic。



![](img/c2eaeddd7e46763e38a3380e48c3d729_194.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_195.png)

The next notion of fairness is what is called equalized odds。



![](img/c2eaeddd7e46763e38a3380e48c3d729_197.png)

And in the separation book， it's often called in the family book， it's called separation。



![](img/c2eaeddd7e46763e38a3380e48c3d729_199.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_200.png)

And essentially equalized odds are sometimes its also called equalized opportunity if you just consider it in one direction。

😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_202.png)

Essentially you want to say all groups experience the same false positive rate and the same false negative rate。



![](img/c2eaeddd7e46763e38a3380e48c3d729_204.png)

So it's not so much about the absolute number as in demographic parity or the absolute fraction of people who received the good treatment。

😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_206.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_207.png)

But it's about the people who should receive the good treatment， but， in fact。

 don't receive the good treatment。 So in numbers， what you want to have is。



![](img/c2eaeddd7e46763e38a3380e48c3d729_209.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_210.png)

So you have again the sensitive attribute， a is 0 or a is 1。😊。



![](img/c2eaeddd7e46763e38a3380e48c3d729_212.png)

And now you look at， for example， the population that should that for which a true label is。



![](img/c2eaeddd7e46763e38a3380e48c3d729_214.png)

Plus one， for example， this is the population。

![](img/c2eaeddd7e46763e38a3380e48c3d729_216.png)

For which some ground truth knowledge would tell you if you had it。

 that this is a person who would be successful in your college。



![](img/c2eaeddd7e46763e38a3380e48c3d729_218.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_219.png)

And now you want that among all so among all white people。😊。



![](img/c2eaeddd7e46763e38a3380e48c3d729_221.png)

That for which the ground truth would be that they are successful in college。

 but which are being rejected from college because your predictor is zero。



![](img/c2eaeddd7e46763e38a3380e48c3d729_223.png)

The probability that this happens should be the same if you're not white but black。😊。



![](img/c2eaeddd7e46763e38a3380e48c3d729_225.png)

So you look at the population for which the true value is would be successful。😊。



![](img/c2eaeddd7e46763e38a3380e48c3d729_227.png)

But then for whom you predict to be unsuccessful， so this is a false negative rate and you want that this rate is like if you know split this rate between say black and white population。

 you want that this rate is the same。

![](img/c2eaeddd7e46763e38a3380e48c3d729_229.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_230.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_231.png)

And the same the other way around， if you predict that someone would be successful。

 even though that person is not successful in ground truth， this is a false positive。😊。



![](img/c2eaeddd7e46763e38a3380e48c3d729_233.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_234.png)

And again， the rate of the false positives should be the same in both populations。



![](img/c2eaeddd7e46763e38a3380e48c3d729_236.png)

Sometimes it's the case that and this is sorry， so taken together these two things are called equalized odds。

😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_238.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_239.png)

Sometimes you only care about the positive case and then it's often called equalized opportunities。

 so you want to have to say the white and the black population。

 if you're capable of surviving your college education then you should also be admitted and if that's not the case that's bad and so you want to have that white and black people have the same opportunity sort of。



![](img/c2eaeddd7e46763e38a3380e48c3d729_241.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_242.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_243.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_244.png)

And that's why it's called this way。

![](img/c2eaeddd7e46763e38a3380e48c3d729_246.png)

And here I have again the examples of how these variables might be defined among the students who have the potential to achieve a master's of science degree so the true label is plus one。

 so this is sort of the ground truth potential that of course you don't know。😊。



![](img/c2eaeddd7e46763e38a3380e48c3d729_248.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_249.png)

The likelihood to be accepted to the masters program。

 so being accepted is the variable y hat equals 1 that's your prediction should be the same for male and female so that's encoded by being0 or a being 1。

😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_251.png)

And tears again， the same for the compass example among the people who do not reoffend the likelihood to be released on bail should be the same both for white and black people。



![](img/c2eaeddd7e46763e38a3380e48c3d729_253.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_254.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_255.png)

Again， you can have a more general definition if you don't have binary variables。



![](img/c2eaeddd7e46763e38a3380e48c3d729_257.png)

It's now conditional independent statement， so you say conditionally on the random variable by。😊。



![](img/c2eaeddd7e46763e38a3380e48c3d729_259.png)

The two random variables， Y， hat and A should be independent of each other。



![](img/c2eaeddd7e46763e38a3380e48c3d729_261.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_262.png)

This is another notion that sounds pretty good。

![](img/c2eaeddd7e46763e38a3380e48c3d729_264.png)

There is one thing that might be a bit disappointing here so assume few we would have a perfect classifier that always predicts a perfect label。

😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_266.png)

So this would mean that both the false negative and the false positive rate would be0。😊。

Then of course， this classifier is perfectly fair according to this definition。



![](img/c2eaeddd7e46763e38a3380e48c3d729_268.png)

This is of course， a consequence of the definition， and it makes perfect sense。😊。



![](img/c2eaeddd7e46763e38a3380e48c3d729_270.png)

But soon， it makes you wonder。

![](img/c2eaeddd7e46763e38a3380e48c3d729_272.png)

Whether this is really the notion of fantasy want， at least in certain applications。But still it's。

 I mean， we have now seen predictive parity， we have seen equalized odds。

 and there are simply two different notions of fairness。😊。



![](img/c2eaeddd7e46763e38a3380e48c3d729_274.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_275.png)

Now we look at predictive parity。In the firm airbook， this is called sufficiency。



![](img/c2eaeddd7e46763e38a3380e48c3d729_277.png)

So the predictive paric criterion is yet another one。

 So you see in all this definition it's all about which variables do I put in the condition and which are the variables I actually look at。

😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_279.png)

And predictive parity now looks at the following， the probability that the ground truth， for example。

 of that the ground truth is that someone is capable of going to college。😊。



![](img/c2eaeddd7e46763e38a3380e48c3d729_281.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_282.png)

Under the condition。That， for example， the person' is white and。



![](img/c2eaeddd7e46763e38a3380e48c3d729_284.png)

The system predicted that the person is going to be successful in college。



![](img/c2eaeddd7e46763e38a3380e48c3d729_286.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_287.png)

This would be the same as if you just exchange the white to the black label。



![](img/c2eaeddd7e46763e38a3380e48c3d729_289.png)

For all， for all values， y。So if the prediction of the system is why？😊。



![](img/c2eaeddd7e46763e38a3380e48c3d729_291.png)

Then the probability that the true value is y should be the same for white and black people。😊。



![](img/c2eaeddd7e46763e38a3380e48c3d729_293.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_294.png)

Again， you can write the definition which is more general。

 which means now now you have a different conditional independent statement。

 now you condition on the predicted variable and you want that the true variables independent of the sensitive attribute。



![](img/c2eaeddd7e46763e38a3380e48c3d729_296.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_297.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_298.png)

This is essentially the first point of view in the compass statement。

 it is sort of if the compass system predicts the score Y hat。

 the likelihood to actually reoffend would be the same for black and white。😊。



![](img/c2eaeddd7e46763e38a3380e48c3d729_300.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_301.png)

There is a slightly more general notion which is very closely related to this one。

 and this notion is called calibration。😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_303.png)

And that's something that is。

![](img/c2eaeddd7e46763e38a3380e48c3d729_305.png)

That is not only used in machine learning， but that's used in many different fields of science。

 or in social science and so on whenever you sort of try to come up with course。

 you call this course calibrated if they sort of predict the correct probabilities and here is the definition。



![](img/c2eaeddd7e46763e38a3380e48c3d729_307.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_308.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_309.png)

So assume， as score， is supposed to predict a certain probability。

 say the probability that a sudden person we offend。



![](img/c2eaeddd7e46763e38a3380e48c3d729_311.png)

And then we say that this score satisfies calibration by group。



![](img/c2eaeddd7e46763e38a3380e48c3d729_313.png)

If for all score values， y and for all sensitive groups A， we have the following property。



![](img/c2eaeddd7e46763e38a3380e48c3d729_315.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_316.png)

The prediction that the system predicts square y。

![](img/c2eaeddd7e46763e38a3380e48c3d729_318.png)

And then the probability that the true score is actually y。😊。



![](img/c2eaeddd7e46763e38a3380e48c3d729_320.png)

Should be why。So you predict the correct probability and if you evaluate it sort say in a simulation。

 if you say the probability is 30% that someone is going to reoffend and you sort of take an average over 5 million people and you check whether they did reoffend。

 you should see 30% of the people。😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_322.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_323.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_324.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_325.png)

And this should hold independently of why， but of course and this is sort of the calibration and the group aspect is here that this should also hold for each group separately。

 not only for the overall group but for each group separately。😊。



![](img/c2eaeddd7e46763e38a3380e48c3d729_327.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_328.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_329.png)

Okay， now you can prove there are certain relationships between predictive parity and calibration in simple cases when everything is binary and so on。

😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_331.png)

These are sort of nearly the same， but it's not always their are more complicated relationships if you want to look it up。

 you can see like look at the FerM mail， but also here's a paper where this is being discussed。



![](img/c2eaeddd7e46763e38a3380e48c3d729_333.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_334.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_335.png)

When you look at different notions of fairness and in particular。

 if you consider running evaluations of fairness of your algorithm。

 you might always want to consider two extreme cases。



![](img/c2eaeddd7e46763e38a3380e48c3d729_337.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_338.png)

To sort of naive classifier us and evaluate their fairness。

 because this is always a baseline that you might want to look at。



![](img/c2eaeddd7e46763e38a3380e48c3d729_340.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_341.png)

The first。Based and you should check is the constant classifier。

 so you simply admit everybody to college， no matter what the features are。

 no matter what the gender is， no matter what the race is， you admit everybody to college。



![](img/c2eaeddd7e46763e38a3380e48c3d729_343.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_344.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_345.png)

So you。This should be why hat。 Sorry， you say why hat should be one for no matter what the input is。



![](img/c2eaeddd7e46763e38a3380e48c3d729_347.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_348.png)

And then in particular， it should again read by head。

 the output why head is independent of everything else。 And then you have。



![](img/c2eaeddd7e46763e38a3380e48c3d729_350.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_351.png)

You have that this classifier is maximally fair， it satisfies demographic parity and equalized opportunity。

😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_353.png)

And you should always。Of course this is an naive way of achieving a fair classifier。

 the question and practice is of course because this classifier probably would have very bad accuracy because it simply admits everybody no matter whether the person would be capable to go to college or not。

 and this is of course not what you want the is really bad here but fairness is perfect。😊。



![](img/c2eaeddd7e46763e38a3380e48c3d729_355.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_356.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_357.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_358.png)

And so whenever you come up with an algorithm that is supposed to generate a fair classifier。

 you should compare to this classifier so what is the notion of fairness that you can achieve and what is the accuracy that you would get in this particular case and now if your algorithm is just slightly more accurate than this one but less fair then maybe it' is really not what you want to have。

😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_360.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_361.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_362.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_363.png)

The other extreme case is if you sort of that's the negative extreme case if you predict the sensitive attribute。

 so say you have a certain application but let's try to predict what is the sensitive attribute from your data。



![](img/c2eaeddd7e46763e38a3380e48c3d729_365.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_366.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_367.png)

So essentially Y hat， so again it should be Y hat， why hat needs to be one exactly if and only if a is one。



![](img/c2eaeddd7e46763e38a3380e48c3d729_369.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_370.png)

So then the output of y is identically with the sensitive attribute and then this classifier is maximally unfair。



![](img/c2eaeddd7e46763e38a3380e48c3d729_372.png)

Both with respect to demographic parity and equalized opportunity。



![](img/c2eaeddd7e46763e38a3380e48c3d729_374.png)

And so as I said， whenever you sort of play with algorithms and try to evaluate fairness and accuracy use these two extreme cases simply to get a feeling for what are these numbers like how much does it mean to be very fair or very accurate？

😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_376.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_377.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_378.png)

No， the。Annoy thing about all these notions of fairness is that there are a number of impossibility results。

And intuitively all these results say you can't have fairness with respect to all these criteria at the the same time。

 have I mean unless you have trivial data， but as soon as your data is non trivialal。

 typically when you satisfy one of these fairness notions。

 you cannot satisfy the other fairness notions。😊，And here I simply want to give you the statements。

 you can read it up in the Ferm L， for example， if you wander in the papers that are being cited on the next couple of slides。

😊，So， for example。Assume that the sensitive attribute and the true variable y are not independent of each other。

 then a demographic parity and equalized odds cannot both hold at the same time。😊。

Or assume why binaryry a is not independent of y and y hat is not independent of y。

Then demographic parity and predictive parity cannot both hold。

The third one assume that all events in the joint distribution of a。

 the predicted variable y hat and the true variable y have positive probability。

And assume that a is not independent of y， then equalized odds and predictive parity cannot both hold at the same time。

One more， assume y is not independent of A and assume Y had a binary。



![](img/c2eaeddd7e46763e38a3380e48c3d729_380.png)

With a non zero false positive rate， then predictive parity and equalized odds cannot hold。



![](img/c2eaeddd7e46763e38a3380e48c3d729_382.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_383.png)

And again， as I said， you can look in the firm air or use this paper by Kleinback at all about inherent tradeoffs in the fair determination of risk cause。



![](img/c2eaeddd7e46763e38a3380e48c3d729_385.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_386.png)

There's much more literature on this。 The bottom line from a Earth is simply。



![](img/c2eaeddd7e46763e38a3380e48c3d729_388.png)

Someone needs to decide which notion of fairness we want to achieve， and we can only have one notion。

 but not the other notion。

![](img/c2eaeddd7e46763e38a3380e48c3d729_390.png)

As a side remark， the same might hold if you have several sensitive attributes， so if you have。

 for example， gender and race and you want to be fair to all of them。

 that's probably also problematic。😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_392.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_393.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_394.png)

There are even more notions of fairness， which I simply want to touch upon without giving a formal definition because they are more involved。

 There is what is called individual fairness。

![](img/c2eaeddd7e46763e38a3380e48c3d729_396.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_397.png)

And there you don't talk about groups of people so you don't say female versus male also。

 essentially you talk about individual and the notion says that two individuals who are similar should receive a similar treatment。

😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_399.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_400.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_401.png)

And there's a series of papers by people who try to promote this individual fairness。



![](img/c2eaeddd7e46763e38a3380e48c3d729_403.png)

In practice again， it's very hard to use because it starts already with the question what is a notion of similarity and depending on which notion of similarity you use。

 you end up with completely different notions of fairness and this is true both in the input space and in the target space。

 so it's really not so obvious in my opinion。

![](img/c2eaeddd7e46763e38a3380e48c3d729_405.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_406.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_407.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_408.png)

There' is another notion that is even a bit more involved and I don't want to discuss it in depth because it requires much more background knowledge on causality。

 so there is what is called counterfactual fairness。😊。



![](img/c2eaeddd7e46763e38a3380e48c3d729_410.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_411.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_412.png)

And sort of here just a couple of examples， essentially it computes what the distribution of any of the variables would have been had certain other variables been different other things being equal。

 So for example， if a certain person had been black instead of white but everything else would have been similar。

 what would have been the outcome。

![](img/c2eaeddd7e46763e38a3380e48c3d729_414.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_415.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_416.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_417.png)

Or here you could ask what an individual I have graduated if this individual hadn't had a job。😊。



![](img/c2eaeddd7e46763e38a3380e48c3d729_419.png)

And so you can ask and counterfual that counterfactual always means you try to generate data that is actually not the true data。

 it's counterfactual， it's against the fact so in fact something else has happened but you argue what would have happened if this feature would have been different and then you can build up a notion of fairness on these kind of counterfactual statements and it uses lots of the framework of causality so if you're interested in there's lots of papers on this here is one where you can start reading there might be many more。



![](img/c2eaeddd7e46763e38a3380e48c3d729_421.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_422.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_423.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_424.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_425.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_426.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_427.png)

Now we have seen a couple of criteria there are many criteria and here is just a table that I took from the firmM L book and there exists many。

 many more criteria and this is not for you to read it just to show there are many criteria。😊。

And they also， depending on the on the community in which these criteria have been defined。

 they also have different names。 So， for example， here you have。Lots of definitions which all。😊。

Correspond to what in in the firm L book is called independence， and it's called Sta parity。

 group fairness， demographic parity， conditional， Sta parity， Darlington criterion4 and so on。

 So there are lots of names for the same criteria。嗯。And depending on your source。

 these names are all different。 So currently the literature is really a bit of a mess。

so whenever you read a paper on fairness， you first of all need to figure out what is the exact notion of fairness they use in this paper and how does it relate to your map of what are the different notions of fairness。

 what is your name for this notion of fairness sort of to get a feeling for what is going on here。

So the bottom line， I've said this often now， but I want to repeat it once more。

 this one unique fairness criterion simply does not exist。



![](img/c2eaeddd7e46763e38a3380e48c3d729_429.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_430.png)

Fairness is a concept that comes from society and it cannot always be computed in a satisfactory manner by statistical criteria so what we tried here is we define all these notions of conditional independence for example where you have certain variables and another variable to condition on this variable and then these other two variables are independent this is of course a crude approximation of what as a society we might consider fair。



![](img/c2eaeddd7e46763e38a3380e48c3d729_432.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_433.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_434.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_435.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_436.png)

And statistics can only contribute so much to a certain discussion。

 and there might be many other things that we would not be able to capture at all in this kind of statistical concepts。



![](img/c2eaeddd7e46763e38a3380e48c3d729_438.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_439.png)

Each of these criteria has some applications where it's really plausible that this is a desirable criterion but each of these criteria also has a lot of seriousbox drawbacks and fails to capture important aspects of some other problems and if you like to know more I mean I think we already get got a gist here in the past discussion we had you can look the firm air for more discussion or even more literature。

😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_441.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_442.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_443.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_444.png)

This all on the negative side， on the other side， something that I always like to point out is what are we going to compare to？



![](img/c2eaeddd7e46763e38a3380e48c3d729_446.png)

Like we build a system that decides whether someone is going to stay in jail or not。



![](img/c2eaeddd7e46763e38a3380e48c3d729_448.png)

But now we compare to the system where a judge simply decides on whether someone is going to stay in jail or not。

 and of course， I mean， the judge also has his or her biases and might not be free of biases and different judges have different biases and some judges might have very strong biases and some might have biases。

 which you would maybe call more moderate。

![](img/c2eaeddd7e46763e38a3380e48c3d729_450.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_451.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_452.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_453.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_454.png)

But it's inconceivable to have a person here which doesn't， who doesn't have any biases。



![](img/c2eaeddd7e46763e38a3380e48c3d729_456.png)

So the baseline we compare to is always people。People as decision as the ones who decide and they are unfair as well。

 And so I think it's often in this debate about fairness， it's often。



![](img/c2eaeddd7e46763e38a3380e48c3d729_458.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_459.png)

Important to keep that in mind and to say， yes， maybe a certain algorithm is unfair with in some respect。



![](img/c2eaeddd7e46763e38a3380e48c3d729_461.png)

But maybe it would interest be interesting to compare at least the unfairness of a certain judge or like this other system。

 or like if it's about this employment agency in Austria。

 how unfair are the people who work in this employment agency and maybe the fairness of the two systems is not even very different from each other or maybe we could design a system for which we think that might be at least fairer than some of the humans who are sitting there would do these decisions。

 but of course this is nothing that's obvious。

![](img/c2eaeddd7e46763e38a3380e48c3d729_463.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_464.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_465.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_466.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_467.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_468.png)

And this is sort of its sort of summarized on this slide。

 I find this interesting because what happens now is we have， I mean。

 we have at least discrete crude definitions of fairness。😊。



![](img/c2eaeddd7e46763e38a3380e48c3d729_470.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_471.png)

And this is something that didn't really， I mean as you have seen， it existed in the literature。

 but maybe people weren not so aware of it。😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_473.png)

And now you can start to compare these technical systems to human systems and I mean， if you wanted。

 you could now start to design studies like how biased is now a certain judge in accord。

 so it's the bottom line which I can't really mark here。



![](img/c2eaeddd7e46763e38a3380e48c3d729_475.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_476.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_477.png)

Or like you can look at past decisions in certain circumstances and you can now try to quantify the unfairness in the same way as you quantify the unfairness of a certain machine learning algorithm。



![](img/c2eaeddd7e46763e38a3380e48c3d729_479.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_480.png)

And then you can start comparing it if sort of for different notions of unfairness。

 the humans tend to be even more unfair than the algorithm then maybe you're good because the algorithm is at least a bit better than the humans。

 even though it might not be perfect。

![](img/c2eaeddd7e46763e38a3380e48c3d729_482.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_483.png)

But this is something I find interesting it opens the door to a discussion that I think would not have been possible a couple of years ago。

😊。

![](img/c2eaeddd7e46763e38a3380e48c3d729_485.png)

![](img/c2eaeddd7e46763e38a3380e48c3d729_486.png)