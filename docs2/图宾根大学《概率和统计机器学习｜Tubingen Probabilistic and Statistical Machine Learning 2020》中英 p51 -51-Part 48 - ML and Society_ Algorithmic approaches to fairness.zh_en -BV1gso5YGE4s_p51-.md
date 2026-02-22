# 图宾根大学《概率和统计机器学习｜Tubingen Probabilistic and Statistical Machine Learning 2020》中英 p51 -51-Part 48 - ML and Society_ Algorithmic approaches to fairness.zh_en -BV1gso5YGE4s_p51-

![](img/194337ec1b6613e0e6292ed6c4bc8728_0.png)

So far， we have seen that there are many different notions of by which we can measure the fairness of a certain algorithm。



![](img/194337ec1b6613e0e6292ed6c4bc8728_2.png)

We have also seen that all these notions of fairness are not really compatible with each other。

 but now let's look at the positive side so how much can we try to improve certain notions of fairness if we know about the requirement of fairness from the first play like in the beginning or when we try to solve our problems so what can we do and maybe what are certain what are the different approaches to try to improve the fairness of algorithms which of them work and maybe which of them don't work this is what I now want to discuss in the next part of the lecture。



![](img/194337ec1b6613e0e6292ed6c4bc8728_4.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_5.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_6.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_7.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_8.png)

So it's about technical approaches to improve fairness。



![](img/194337ec1b6613e0e6292ed6c4bc8728_10.png)

In principle， there are three main approaches that are being used or tried to be used to improve the fairness of a certain system。



![](img/194337ec1b6613e0e6292ed6c4bc8728_12.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_13.png)

The first one is you try to use preprocessing to your data。In particular。

 you try to fix all the bias that is inherent in your data because the rational is。

 if there is lots of bias in our data saying this kind of language bias also or employment history。

 then if we don't get rid of this bias it's hard to correct for this hindsight。😊。



![](img/194337ec1b6613e0e6292ed6c4bc8728_15.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_16.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_17.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_18.png)

So that's the first approach。The second approach is in training。

 what you can do is you can try to train a classifier that at the same time is accurate and is fair according to a certain notion of fairness。

😊。

![](img/194337ec1b6613e0e6292ed6c4bc8728_20.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_21.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_22.png)

Which in my opinion is sort of the most promising approach and I will show you how this works。

 but of course it also doesn't work perfectly。

![](img/194337ec1b6613e0e6292ed6c4bc8728_24.png)

And then there's post processing， so if you have already a trained model and maybe it took you a couple of months to come up with a trained model or it's a secret model hidden like by some company but the company doesn't really reveal the algorithm by which it came to that model。

😊。

![](img/194337ec1b6613e0e6292ed6c4bc8728_26.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_27.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_28.png)

Is there anything you can do in hindsight to fix the bias of the algorithm at least a bit？😊。



![](img/194337ec1b6613e0e6292ed6c4bc8728_30.png)

And these are the three different approaches， and we are going to discuss each of them briefly。😊。



![](img/194337ec1b6613e0e6292ed6c4bc8728_32.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_33.png)

The first approach， as I said， is we try to fix the unfairness in the data。



![](img/194337ec1b6613e0e6292ed6c4bc8728_35.png)

So the first naive attempt would be well let's simply remove this unfair like the sensitive attribute from our data and everything is fine so if you want to I don't know predict a credit score。

 simply don't use the raise and everything is going to be fine。😊。



![](img/194337ec1b6613e0e6292ed6c4bc8728_37.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_38.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_39.png)

As we have already discussed， this approach is pretty much impossible because there are so many proxy variables that are highly correlated。

 for example， with the race。😊。

![](img/194337ec1b6613e0e6292ed6c4bc8728_41.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_42.png)

That simply removing the race won't work， the algorithm is simply going to find the next variable that is closely related to the race and use this one。

 so implicitly the race is still being used even though it' is not an explicit variable of your algorithm。

 so this is not going to work。😊。

![](img/194337ec1b6613e0e6292ed6c4bc8728_44.png)

And here I have again the example of the zip code we have seen this before。

 so the zip code might serve as such a proxy and then even if you remove the races。

 your algorithm might still be very unfair with respect to black populations。



![](img/194337ec1b6613e0e6292ed6c4bc8728_46.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_47.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_48.png)

The next problem is that in many cases， the discriminatory features or these bias of the data are even hard to grasp。

 So I mean， there are some， if you look at data sets there like machine learning is all about finding relations between different variables like between input variables into the output variable and there are some relations which we would find highly highly desirable。

 and then there might be other relations which we simply don't want to see。 So， for example。😊。



![](img/194337ec1b6613e0e6292ed6c4bc8728_50.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_51.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_52.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_53.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_54.png)

If you look at a medical example， the fact that smoking， the fact whether you smoke or not。

 is associated with the fact， whether you get cancer or not。

 this is a correlation that we would like to find in our data because there might even be or everybody believes that there is like even a causal relation between these two things。

😊。

![](img/194337ec1b6613e0e6292ed6c4bc8728_56.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_57.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_58.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_59.png)

So this is something the algorithm would be supposed to find whereas there are other patterns like girl like pink and boys like blue clothes。

 this is maybe something that you don't want to find because again it is going to increase gender stereotypes。

 but how should you tell an algorithm and there are millions of feature about a certain person whether if the person wears pink clothes it's like more likely to be a a girl and if the person wears blue clothes it's more likely to be a boy so these kind of things and there are millions of these things in the data。

 so it's really hard to specify all these sources of bias and it's essentially impossible。😊。



![](img/194337ec1b6613e0e6292ed6c4bc8728_61.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_62.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_63.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_64.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_65.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_66.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_67.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_68.png)

And in fact， something I've written here at the bottom of this slide。

 it might even not be that all the humans would agree on which variables or which associations we would like to find and which one we would consider a bias and which ones we would not consider a bias。

😊。

![](img/194337ec1b6613e0e6292ed6c4bc8728_70.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_71.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_72.png)

And if we can't even agree as a human， then it's sort of hard to tell an algorithm。

 but it's supposed to do。

![](img/194337ec1b6613e0e6292ed6c4bc8728_74.png)

Now the next thing you can do is if you say well I can't remove the race for example and then think everything is fine。

 so why don't I simply also remove the zip code and the employment history and the education and all these variables that might be correlated with the race and then I work on all the variables that are remaining to for example predict whether someone is going to pay back a credit or not。



![](img/194337ec1b6613e0e6292ed6c4bc8728_76.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_77.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_78.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_79.png)

Well the problem is that if you do this， it might happen that in many cases you remove many， many。

 many of the important， if not all of the important variables and because it simply might not be true that there is complete independence between what you want to predict and the sensitive attribute and as soon as there is no independence between these two notions whenever you remove all these attributes。

 the classifier is not going to work anymore， you don't achieve high accuracy。

 it might be perfectly fair but the accuracy is so low that you simply are not going to use your classifier anymore。

😊。

![](img/194337ec1b6613e0e6292ed6c4bc8728_81.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_82.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_83.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_84.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_85.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_86.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_87.png)

And this is already the case if you have one sensitive variable。

 if you have even more like gender and race， I mean you're completely doomed Eventually theres no variable left。

😊。

![](img/194337ec1b6613e0e6292ed6c4bc8728_89.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_90.png)

The next problem might be that you might not even have access to the sensitive attribute so you can't even compute the correlation and because maybe someone was careful enough to remove the sensitive attribute at the beginning and then you're left with a data set that doesn't have the sensitive attribute explicitly so what you would need to do to be able to do that you first of all would need to predict the sensitive attribute then compute the correlation between what you predicted it and remove the variables I mean this is going to be a mess and this is of course I mean sort of the last thing you might want to do is someone removes the sensitive attribute and your algorithm as its first step tries to predict the sensitive attribute this is completely stupid so this is going to be a complicated approach。



![](img/194337ec1b6613e0e6292ed6c4bc8728_92.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_93.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_94.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_95.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_96.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_97.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_98.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_99.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_100.png)

Then there are other approaches where you say well maybe the problem is that we have all these feature descriptions and these features of course many of them might be correlated to the sensitive attribute。

 so maybe we should simply use different representations of our data。

 we maybe should not use representation based on features。



![](img/194337ec1b6613e0e6292ed6c4bc8728_102.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_103.png)

But we simply should try to come up with similarity data。 For example。

 you could say I represent my population with a number of prototypes。



![](img/194337ec1b6613e0e6292ed6c4bc8728_105.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_106.png)

And then I represent each person or each point as a weighted linear combination of these kind of prototypes。



![](img/194337ec1b6613e0e6292ed6c4bc8728_108.png)

And then I train my algorithm on top of that。

![](img/194337ec1b6613e0e6292ed6c4bc8728_110.png)

In order to， hopefully， because then there is nothing， I'd only have a distance function。

 and maybe this distance function is not so much related to the sensitive attributes。



![](img/194337ec1b6613e0e6292ed6c4bc8728_112.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_113.png)

But it is not going to work in。 I mean， there are a number of papers which suggest that it is not going to work in most cases。

 and I think one of the problems is already which kind of distance function are you going to use and the distance function implicitly might already encode again sort of the sensitive attributes。



![](img/194337ec1b6613e0e6292ed6c4bc8728_115.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_116.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_117.png)

So for example， it might be that even though you didn't intend that black people happen to be very similar to each other and white people happen to be very similar to each other。

 but there's no similarity between them and then there you go。

 I mean the algorithm is going to be biased again。

![](img/194337ec1b6613e0e6292ed6c4bc8728_119.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_120.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_121.png)

Okay， so in my opinion， so this was all about this preprocessing。

 I am not very confident that preprocessing can really help， I mean maybe it can help a tiny bit。

 but as far as I can see in most applications this preprocessing is not going to be the solution to unfair machine learning algorithms。

😊。

![](img/194337ec1b6613e0e6292ed6c4bc8728_123.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_124.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_125.png)

The next thing you can do is you can say， well maybe I can't remove the unfairness in the data。

 but I can force my algorithm to find solution， find a solution that is fairer。

 maybe more fairer than the most accurate solution so I sort of drive it towards solution that might be a bit less accurate but more fair in the end。

😊。

![](img/194337ec1b6613e0e6292ed6c4bc8728_127.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_128.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_129.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_130.png)

And so here we are in a standard supervised machine learning setup， so we want to learn a function。

 we have a certain risk function that we want to learn and so this is according to a certain loss。😊。



![](img/194337ec1b6613e0e6292ed6c4bc8728_132.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_133.png)

Over some function space like the standard kind of setup， we might have a regularizer if we want。

 so we are in the standard supervised classification setup。😊。



![](img/194337ec1b6613e0e6292ed6c4bc8728_135.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_136.png)

And now， additionally。We have another criterion， which is the fairness of our classifier。😊。

And now for simplicity， simply assume we have two sensitive groups called a equals 0 and a equals 1。

😊。

![](img/194337ec1b6613e0e6292ed6c4bc8728_138.png)

And say assume we are after demographic parity， you can do the same game with all the other notions of fairness。

 but let's in order to be concrete， make it for demographic parity。

 So now what you do is you define the unfairness of a certain function。😊。



![](img/194337ec1b6613e0e6292ed6c4bc8728_140.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_141.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_142.png)

By simply measuring these probabilities that are supposed to be equal and you check the difference so a demographicparity says no matter whether a is plus1 or a is0 you would have the same would like to have the same probability that the outcome is a certain event like positive or negative or like if you have a score。

😊。

![](img/194337ec1b6613e0e6292ed6c4bc8728_144.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_145.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_146.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_147.png)

Then the that if the， the function is positive， for example， if that's your positive class。



![](img/194337ec1b6613e0e6292ed6c4bc8728_149.png)

And now you measure the probability that it happens for， say。

 the white population and the probability that it happens for the black population。

 you take the difference， and this is by which you measure the unfairness。

 So 0 would mean it's completely fair and the more it deviates from 0。

 the unfair your classifier is going to be。😊。

![](img/194337ec1b6613e0e6292ed6c4bc8728_151.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_152.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_153.png)

And now you sort of okay and this was defined on the true population now you define the empirical version of this unfairness which now doesn't look at the true variables but at the ones that you can measure on your sample。

😊。

![](img/194337ec1b6613e0e6292ed6c4bc8728_155.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_156.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_157.png)

So you look at all people who have population like sensitive attribute A being in plus one or a being in zero。

 you measure how often is it the case that these populations。



![](img/194337ec1b6613e0e6292ed6c4bc8728_159.png)

诶。

![](img/194337ec1b6613e0e6292ed6c4bc8728_161.png)

That is that。That these are unfair， and then that's your unfairness crition。

 So here's parent this is missing。 I'm sorry。

![](img/194337ec1b6613e0e6292ed6c4bc8728_163.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_164.png)

And now you can pose a certain optimization problem which now has two objective I mean there are two ways to do that The first one is this one where we say you want to minimize the standard regularized risk subject2 the unfairness being below a certain threshold so you simply say and this is now society tells you we are only willing to tolerate an unfairness with respect to demographic parity for example by I don't know10% so for example the number of male and female people who are being promoted shouldn't be different by more than 10%。



![](img/194337ec1b6613e0e6292ed6c4bc8728_166.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_167.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_168.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_169.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_170.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_171.png)

Then this is your tower， and this is a constraint that you add to your optimization problem。😊。

The other way I think it's not on the slide is， of course you could also add the unfairness as a regularizer itself。

 so you could have another trade of constant new times unfairness of F and then try to optimize all cr at the same time。

 so then you have not only two objectives namely small empirical risk and good regularization or small complexity of your function。

 but the third criterion would then be good unfairness like being fair。



![](img/194337ec1b6613e0e6292ed6c4bc8728_173.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_174.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_175.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_176.png)

Now maybe you might want to think about it for a second whether this is now a simple optimization problem or not。



![](img/194337ec1b6613e0e6292ed6c4bc8728_178.png)

And the answer is pretty obvious， it is a difficult optimization problem because this unfairnness criterion here is something that is discrete。

😊，So you simply count how many white and black people， for example， get the credit。

 this is a discrete variable， so the unfairness is something more is discrete and this is always hard to optimize。

😊。

![](img/194337ec1b6613e0e6292ed6c4bc8728_180.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_181.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_182.png)

And now the question sir， I mean， so far， everything， I think was pretty obvious。

 This is sort of what everybody would write down。 And now the question is。

 how can you do that now in practice。And the standard solution that has been promoted in many publications already is to use a convex relaxation。

😊，And try to。 So instead of this unfairness criterion。

 you come up with a relaxation that leads to a complexve problem。😊。

And then you solve the convex problem， and you're happy。

Now what we found in an ICML paper this year is that in fact many of these approaches the problem while you can solve the optimization problem or easier because the problem is maybe convex。

😊，The actual fairness criterion that you get out of these things is often very bad， as well。

This is what we in fact showed in our paper we then suggested some other way for which I don't think this is really the end of the story by which you sort of get guarantees on the fairness but then the downside of our approaches we don't get any guarantees on the accuracy anymore so now there are some algorithms that achieve a good accuracy but maybe are unfair we now can present an algorithm that is really fair but we cannot really at least guarantee the accuracy and onprac you can play with all these approaches。

😊，I think neither our paper nor any of the other papers so far is the end of the story。

But at least to me， it sounds like this is the most promising approach to sort of drive algorithms towards a fair solution。

If you want to look at some references there below here。

Now the third thing that you can do is you can try to fix models in hindsight。

 so the scenario is now we have maybe a company that trains a classifier。

 say the Shufa in Germany that sort of predicts does credit score assessment。😊，But the way it trains。

 the classifiers kept private。 So I'm sure that the sher would never ever tell us how they come up with their score。

 whether you are eligible for a credit or not。And similarly， for the compasst core， I mean。

 I don't see that this is going to be make made public。

So but now assume the situation we have this private sort of system。

 that trains the machine learning algorithm， and we find it to be unfair and we think maybe we can post process it at least a bit so that the results become a bit more fair。

So we want to fix it in hindsight。And now， what are our options。

So essentially we only get access to what is the prediction of the classifier and the sensitive attribute we might not even see the input data because its again private knowledge of this company。

😊，So essentially we only and if everything is binary。

 we essentially have two values for y hat plus 100。

 and we have two values of the sensitive attribute plus 100。

 And now the question is can you can you sort of。😊，Fix something in hindsight。

And so this is of course a very naive situation and there might be more cases which are intermediate between knowing nothing and knowing everything。

 but this is the extreme case where you only see the predicted output。😊，And the question is。

 can you construct a derived classifier that takes simply Y head and A's input and produces a new output and this new output is called Y tilde。

😊，That is fairer。And so what you can do is now you can define these quantities P。



![](img/194337ec1b6613e0e6292ed6c4bc8728_184.png)

YA， which is the probability that your new score is1。



![](img/194337ec1b6613e0e6292ed6c4bc8728_186.png)

Given that the old score has a certain value and the old sensitive attribute has a certain value and you can look at these scoress for all of values of Y and A。

😊。

![](img/194337ec1b6613e0e6292ed6c4bc8728_188.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_189.png)

And now you can construct and can try to construct a post process why tilda， like taking why taking。



![](img/194337ec1b6613e0e6292ed6c4bc8728_191.png)

I can't market taking Y head and A is input the condition here， produce a new classifier。

 a new output。😊。

![](img/194337ec1b6613e0e6292ed6c4bc8728_193.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_194.png)

嗯。For which the probabilities are in such a way that the singer can be considered to be fair。



![](img/194337ec1b6613e0e6292ed6c4bc8728_196.png)

And you can do that， there is an approach that's been described in the reference that Im going to have on the next slide。



![](img/194337ec1b6613e0e6292ed6c4bc8728_198.png)

It is a linear program， this is easy， you can solve that and then there is going to be a solution and the solution is going to use randomization。

😊。

![](img/194337ec1b6613e0e6292ed6c4bc8728_200.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_201.png)

So in the end， for a certain part of the population。

 you simply use a randomized prediction with a certain probability。

 and then the final result is fair。😊。

![](img/194337ec1b6613e0e6292ed6c4bc8728_203.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_204.png)

Obviously what happens at the same time is that the accuracy of the classifier decreases because at least you can I mean at least theoretically you can think about the scenario that this company that generated this hidden kind of model spend a lot of time on getting the best accuracy and now you're going to change the classifier it's very likely that the accuracy goes down and not up so you are going to decrease the accuracy but you' are going to increase the fairness of your system。

😊。

![](img/194337ec1b6613e0e6292ed6c4bc8728_206.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_207.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_208.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_209.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_210.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_211.png)

Now you can also do that if the function you want to predict is not just a binary label。

 but it's something kind of like a continuous variable， a continuous score。😊。



![](img/194337ec1b6613e0e6292ed6c4bc8728_213.png)

嗯。

![](img/194337ec1b6613e0e6292ed6c4bc8728_215.png)

And then for example， you need to look at the ROC curves of the classifiers and I'm aware that in this lecture we haven't really defined the R ROC curves yet this is going to happen in the next couple of lectures。



![](img/194337ec1b6613e0e6292ed6c4bc8728_217.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_218.png)

But if you know it or like at the end of the semester， come back to this lecture and look at it。

 So here the R O C curve， you check the R O C curve of the two classifier one for the for one population。

 a equal0 and the one for the other population in the place where these two R O C curve。😊。



![](img/194337ec1b6613e0e6292ed6c4bc8728_220.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_221.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_222.png)

Match is， of course， a place where you have the same kind of true。

 true negative true and false positives true false positives， false negatives and so on。 couple of。



![](img/194337ec1b6613e0e6292ed6c4bc8728_224.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_225.png)

Varis， and then this is what you're going for。

![](img/194337ec1b6613e0e6292ed6c4bc8728_227.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_228.png)

If the cars do not intersect there are still ways you can do that if you want to do and then you need to use a randomized predictor again and you can look at this paper it's this one here by Margaretitz Har Eric Priceze and Art about equality of opportunity in Europe's 2016。



![](img/194337ec1b6613e0e6292ed6c4bc8728_230.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_231.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_232.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_233.png)

So what we have seen so far is we have looked at the three different ways we just looked at the groups of approaches by which you can try to improve the fairness to recap it was we changed by preprocessing we tried to make the data more fair。

 by training we tried to achieve a classifier that in the first place already achieve a certain notion of fairness。



![](img/194337ec1b6613e0e6292ed6c4bc8728_235.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_236.png)

In proposed processing， we might be able to again remedy some fairness or bring some more fairness into the algorithm at the cost of a higher accuracy of a lower accuracy。

😊。

![](img/194337ec1b6613e0e6292ed6c4bc8728_238.png)

And this last sentence at the cost of accuracy， this is now what I briefly want to discuss in tradeoffs。

😊。

![](img/194337ec1b6613e0e6292ed6c4bc8728_240.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_241.png)

There is an obvious tradeoff between accuracy and fairness because fair classifiers。

 they try to optimize two different objectives。 they try to optimize the fairness of a classifier。

 and they try to optimize the accuracy。

![](img/194337ec1b6613e0e6292ed6c4bc8728_243.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_244.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_245.png)

And of course， like if you try to optimize both。

![](img/194337ec1b6613e0e6292ed6c4bc8728_247.png)

Then in principle， the accuracy would only be able to be to go down。

 So because if you just look at the accuracy， you find the best most accurate classifier。

 if you now say this is unfair to choose somebody else， it's very likely that the accuracy goes down。

 at least it never would go up， but very likely it would go down。



![](img/194337ec1b6613e0e6292ed6c4bc8728_249.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_250.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_251.png)

And so there is a choice that you have to make make you have to choose how much accuracy are you willing to give up。



![](img/194337ec1b6613e0e6292ed6c4bc8728_253.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_254.png)

By increasing the fairness。And this sounds very abstract but choice of accuracy accuracy might mean you give a credit to someone who might not be able to pay it back and this might be a disaster of that family。

 you might admit someone to college who in the end might not be able to get a degree which is also a disaster for this person。

 so it's not just about this abstract notion of a accuracy。

 it is really there are societal costs to these kind of things。



![](img/194337ec1b6613e0e6292ed6c4bc8728_256.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_257.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_258.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_259.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_260.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_261.png)

But there are other societal benefits in the sense that you have more fairness。



![](img/194337ec1b6613e0e6292ed6c4bc8728_263.png)

And now again there is no unique solution to this， need to be you need to as the one who designs like as the one who like who implements the system。

 not the machine learner， but the ones who use the system in the end sort of need to have a feeling for how much accuracy can you give up。

😊。

![](img/194337ec1b6613e0e6292ed6c4bc8728_265.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_266.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_267.png)

嗯。For the fairness that you came。 And this is， of course， it's， again。

 one of these sort of nearly impossible things to do。 How you， how should you sort of。



![](img/194337ec1b6613e0e6292ed6c4bc8728_269.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_270.png)

Come up with a trade off here， it just but I think what happens here is it just pinpoint very clearly what the problems are。

😊。

![](img/194337ec1b6613e0e6292ed6c4bc8728_272.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_273.png)

And what are the things that you would need to be able to solve if you want to have at least like a perfect criterion to define your your how accurate your classifier and how fair your classifier is supposed to be I think it just highlights how difficult this whole field is because this is something。



![](img/194337ec1b6613e0e6292ed6c4bc8728_275.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_276.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_277.png)

That so far we have never been able to solve by other means that machine learning and also machine learning is not going to solve it。

 but it makes some of these questions a bit more explicit。😊。



![](img/194337ec1b6613e0e6292ed6c4bc8728_279.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_280.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_281.png)

One insight that has also been made a couple of points is that fair classifiers might require randomizations。



![](img/194337ec1b6613e0e6292ed6c4bc8728_283.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_284.png)

We have seen， for example， this example where we tune class arts and hindsight that this if you want to achieve fairness here。

 it only works via randomization， but now this is again such one of these things if you have a theoretically result that tells you the only way to achieve a fair classifier in the scenario is to use a randomized classifier。

 so it makes random decision at least on a certain part of the population。

 this is something that keeps you thinking， so there might be some application where it's maybe not so important。

😊。

![](img/194337ec1b6613e0e6292ed6c4bc8728_286.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_287.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_288.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_289.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_290.png)

I don know you tax company and the question is which of your taxpayers are you going to check and you might have a random assignment whom you're going to check maybe then you have bad luck and your tax declaration is being checked but maybe that's not such a bad thing。

 but assume I mean you make the decision on whether someone is going to be released from jail in a randomized way。

 I mean this is something that you would never ever be able to justify from an ethical principle。

 you simply cannot use a randomized class in such kind of scenarios。



![](img/194337ec1b6613e0e6292ed6c4bc8728_292.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_293.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_294.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_295.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_296.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_297.png)

But you would need to do it in certain scenarios if you wanted to have a a fair classifier。

 so again you have sort of this tension between what society finds acceptable and there are many different things that come from society。

 society tells you your classifier should be fair but it should not be randomized and then we can say。

 well sorry but we we can't satisfy all these requirements at the same time you need to decide and then we are going to try to do it。

😊。

![](img/194337ec1b6613e0e6292ed6c4bc8728_299.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_300.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_301.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_302.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_303.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_304.png)

Another thing that I want to mention here， only briefly。😊。



![](img/194337ec1b6613e0e6292ed6c4bc8728_306.png)

Just so you' are aware of it is that whenever you do make this kind of even try to make fair classification。

 there are lots of feedback loops when you apply machine learning systems in society。😊。



![](img/194337ec1b6613e0e6292ed6c4bc8728_308.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_309.png)

And there is， for example， something that is often called selffulfil predictions and I've made the example already before。

 suppose you have a predictive policing system and it says in this area I believe that there is more crime is going to happen so you put more policemen in these areas and then they're going to observe more crimes simply because there are more policemen now the statistics get updated the statistics found that there even more crimes in this particular area so you send more policemen and you observe more crimes and the dramatic thing is because these systems are being used continuously this also enters your data so when you train next year you will see that in this particular area where you hit these many policemen already the crime rate even increased so you' are going to send even more policemen。

😊。

![](img/194337ec1b6613e0e6292ed6c4bc8728_311.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_312.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_313.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_314.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_315.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_316.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_317.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_318.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_319.png)

And you can see where this is heading， so even though in the beginning there might have been no difference in the crime rate in these different areas of your city。

😊。

![](img/194337ec1b6613e0e6292ed6c4bc8728_321.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_322.png)

Simply by using。A machine learning tool。

![](img/194337ec1b6613e0e6292ed6c4bc8728_324.png)

You start all of a sudden inducing biases and these biases can be increasing due to feedback loops。



![](img/194337ec1b6613e0e6292ed6c4bc8728_326.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_327.png)

And there are other mechanisms by which this can happen。

 this is simply something to be very aware of that by using machine learning tool。

 you generate the data that is going to be used next year as your training data。

 and this is of course not independent from the tool that you've used in the last year。😊。



![](img/194337ec1b6613e0e6292ed6c4bc8728_329.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_330.png)

And so this is simply something to keep in your mind when you talk about biases in machine learning。

 this is a very strong。

![](img/194337ec1b6613e0e6292ed6c4bc8728_332.png)

ASo of biass as well that can really have bad effects。



![](img/194337ec1b6613e0e6292ed6c4bc8728_334.png)

Yeah， I've already mentioned this one here。 again， you can look at some papers。

 there's lot of literature on this。

![](img/194337ec1b6613e0e6292ed6c4bc8728_336.png)

![](img/194337ec1b6613e0e6292ed6c4bc8728_337.png)

So what is the final discussion？Fair。I mean， this is not a topic that is new。

 fairness has been a long debate in ethics in sociology in many fields。

 whenever it comes to decisions and to something that affects humans。

 there is lots of discussion there's also a social choice and so on so many fields even in computer science that deal with different notions of fairness。

😊，Like from a theoretical point of view。Or from a technical point of view， even。

My take on this is there's not going to be a technical solution for this problem of fairness。

There are many different decisions you need to take。

 many different also requests that come from society。

And different requests and different decisions would lead to different solutions。

These solutions might have different a curacies。 they might have many many of these solutions might differ in many different ways and in the end。

There is no technical solution to decide which one is best in the end society has to decide it。嗯。

My take is also that most of these issues in the end cannot be fixed by technical solutions。

You can make your algorithm a bit fairer， but it's not going to be completely fair in the end even if you fix one notion of fairness。

 say you want to achieve demographic parity， if you try to junior algorithm in such a way that it's really fair according to demographic parity。

 your accuracy is going to be so low that nobody is going to use that algorithm。And again。

Here society has to decide what are the tradeoffs that it， whatever it is， finds acceptable。

I think what our role is here is to really explain that all these trade offs。

 what are all the variables that are important and sort of outline like scenarios maybe you say if this is your scenario this would be my solution。

 if this is your scenario this would be my solution。

 this would be the consequences and now again we can keep on deciding which solution would be the most preferable one in the very end。

😊。