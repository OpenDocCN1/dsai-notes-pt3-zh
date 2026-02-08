# 宾夕法尼亚大学《因果推断速成课程｜A Crash Course in Causality》中英字幕 - P5：05_01_05_因果效应.zh_en - GPT中英字幕课程资源 - BV1Ft42137BF

This video is on causal effects。Here we're going to more formally define what we mean by causal effects。

 and in particular， we'll discuss two types of causal effects。

Average causal effects and the causal effect of treatment on the treated。

So we're going to formally define them using statistical notation， potential outcomes。

 so this video is going to be a little more technical。

And then we're also going to spend some time focusing on the difference between conditioning on a variable or variables versus manipulating or setting variables so first we're going to talk about hypothetical worlds and average causal effects so let's begin by thinking of some population of interest which we're depicting just with a circle so this circle is everybody you're interested in or it's representing a whole population of people that you're interested in so it's。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_1.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_2.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_3.png)

It's sort of your target of interest。If you're interested in you know people who have diabetes and what treatment is better than your population would be the population of diabetics this circle represents the whole population that you're interested in and now we're going to think about hypothetical worlds so remember with potential outcomes we were thinking about hypothetical worlds and hypothetical interventions and so we're still thinking about that now so we're not really。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_5.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_6.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_7.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_8.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_9.png)

Thinking about data yet， this is we're just imagining what we would ideally like to see。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_11.png)

So what we would ideally like to see is。

![](img/8c7596c226dd43f1be35a79d7ea6e9db_13.png)

2 worlds， two hypothetical worlds。 So World one， with which is depicted by this grayish circle。

 is that everyone in our population gets treatment A equals 0。 So treatment A equals 0 could be。

 It actually could be no treatment。 It could be。

![](img/8c7596c226dd43f1be35a79d7ea6e9db_15.png)

It could be a placebo， whatever you imagine。But we're picturing now this is a world where our entire population。

 every single person。Got treatment equals 0 versus some other hypothetical world where everyone received the other treatment a equal 1。

 So we're depicting that with this light blue circle。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_17.png)

But the most important thing here is that these are World one and World I have the exact same people。

 it's the same population of people， but in one case， we do one thing to them and another case。

 we do another。 And then if we were able to observe both of these worlds simultaneously。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_19.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_20.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_21.png)

We could collect the outcome data。From everyone in the populations。

 and then we could take the average value。

![](img/8c7596c226dd43f1be35a79d7ea6e9db_23.png)

So I say mean of y in one in World one and mean of y in World two。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_25.png)

And then that difference would be the average causal effect。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_27.png)

And。So this is what we mean by an average causal effect。So。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_29.png)

It's an average in the sense that it's a mean， and it's a population sort of level average causal effect。

 It's over the whole population。We're saying， what would the average outcome be if everybody got one treatment versus if everybody got another treatment？

Of course， we're not。 in reality， we're not going to see both of these worlds。

 but this is what we want。 This is this is。

![](img/8c7596c226dd43f1be35a79d7ea6e9db_31.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_32.png)

What's what we define as the average causal effect。 this is what we would like to see。

 and this is what we're hoping to estimate， and we can define that more formally using statistical notation。

 So here the E refers to expected value and that also means that's the mean and。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_34.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_35.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_36.png)

Here， we're then taking the average of difference of these two potential outcomes。

 So remember why superscript1 is a potential outcome。If treated with equal1。

And y superscript 0 is a potential outcome if created with a equals 0。

 And so then we could take the average difference of that。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_38.png)

To get an average causal effect。

![](img/8c7596c226dd43f1be35a79d7ea6e9db_40.png)

So this quantity， this average causal effect， is the average value of y if everybody was treated with a equal1 minus the average value of y if everyone was treated with a equals 0。

 And that's exactly what I showed you on the previous slide。

 mean of y for world 1 versus mean of y for world 2。 So in the case where y is binary， for example。

 this would just be a risk difference。 It， In fact， it would be a causal risk difference。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_42.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_43.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_44.png)

Because。The mean of a binary variable is just a probability or a risk。

 and so then the mean of a difference of potential outcomes where the outcome is binary would be a risk difference and a causal risk difference in this case。

So now we'll present。An example， which is the average causal effect。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_46.png)

Under。This situation where we're comparing regional versus general anesthesia for hip fracture surgery and risk of major pulmonary complications。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_48.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_49.png)

So here our population that circle from previous slides。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_51.png)

s the population of people who are undergoing hip fracture surgery。

 so that's the population we're targeting。Our outcome Y is major pulmonary complications。

 and that's just a binary variable， so just a yes or no，1 or0。

 and our treatment is regional versus general anesthesia。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_53.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_54.png)

So suppose that the causal effect here。

![](img/8c7596c226dd43f1be35a79d7ea6e9db_56.png)

The average causal effect is negative 0。1。So right now。

 we're just imagining that we know what that is so that。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_58.png)

We can just think about what the causal effect means。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_60.png)

So at this point， we're not thinking about estimation or any of that。

 We're imagining that we just happen to know what this causal effect is and we want。

 we want to interpret it。 So imagine that the causal effect is negative 。1。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_62.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_63.png)

What that means is the probability of major pulmonary complications is lower by 0。1。

 if given regional anesthesia compared with general anesthesia。

But it's a little bit difficult to think about。What a difference in probabilities means or a difference in risk means。

 So one thing that's helpful is to to quantify that in terms of number of people。

 So we could imagine if 1000 people were going to have hip fracture surgery then。

If the causal effectiveness is negative 0。1， we would expect about 100 fewer people to have pulmonary complications under regional anesthesia compared with general anesthesia。

Now we can look at another example， suppose treatment is thighsi diuretics versus not versus no treatment。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_65.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_66.png)

Among hypertensive patients。 And our outcome， why here is systolic blood pressure。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_68.png)

So our population， that circle that we're interested in is hypertensive patients。

 so patients with hypertension。

![](img/8c7596c226dd43f1be35a79d7ea6e9db_70.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_71.png)

And we're interested in， is it effective？To treat with thighsi diuretics。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_73.png)

And now imagine that the true causal effect。

![](img/8c7596c226dd43f1be35a79d7ea6e9db_75.png)

This population average causal effect is。Is the value of negative 20？So this is， again。

 the outcome sstolic blood pressure。

![](img/8c7596c226dd43f1be35a79d7ea6e9db_77.png)

So what this would mean then is that。If you think of the population of hypertensive patients that。

That took thighsi diuretics。 On average， they would have a。

Cystolic blood pressure value that's about 20 units lower than if they did not take this particular medication。

Next， we're going to。Focus a little bit on a very important topic， which has to do with。

Conditioning versus setting。

![](img/8c7596c226dd43f1be35a79d7ea6e9db_79.png)

And in particular， we're thinking about treatment and so some of this has to do with statistical notation and some of this has to do with is conceptual and it's really crucial to get this distinction down。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_81.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_82.png)

So first。What we mean by conditioning is in the usual sort of statistical sense where。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_84.png)

Whereas a given。

![](img/8c7596c226dd43f1be35a79d7ea6e9db_86.png)

Or conditional on。A particular variable， in this case， we're focused on treatment。So。

 the main idea is that。This average causal effect。Of the。

 which is the mean of this difference of potential outcomes。

 which is what we see on the left side of this inequality， the expected value of y 1 minus y 0。

 That's not， in general， going to be the same thing as。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_88.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_89.png)

The expected value of y， your observed y given a equal 1 minus the expected value of y given equals 0。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_91.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_92.png)

And。This idea is。Is really fundamental to causal inference。So let's think about what what these。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_94.png)

Different types of quantities mean。So whenever you see this vertical line in an expected value。

 you could。One way you can read it is。

![](img/8c7596c226dd43f1be35a79d7ea6e9db_96.png)

You know， the expectability of y give an equal one。But I usually like to think of it as。

Its defining a subpopulation。So rather than say， give an equal1。

 you could read it as the expected value of y among people who have。

A equal 1 or among the subpopulation of people who have a equal 1。 So this vertical line。

 this conditioning is really restricting to a subpopulation of people。

 So the expected value of y given equal1 means what is the average value of y in the subpopulation of people defined by those who actually receive treatment equal to 1。

But they might differ from the population as a whole in important ways。So for example。

 people at higher risk for flu might be more likely to choose to get a flu shot。So we。

So imagine that that's the case that people at higher risk for the flu might be more likely to get the flu shot。

Then， if we take。The expected value of y。Among people who actually got the flu shot。

We're taking expected value of y among sort of a higher risk population。

And that's different than the expected value of the potential outcome Y superscript1。

 because y superscript 1。Is。The outcome， if everyone in the whole population got treatment。

 it's not restricting to a subpopulation。 So when I say setting treatment。

 I mean manipulating or in the potential outcome situation。 And when I say conditioning on。

 I really mean restricting to subpopulations。We can see this pictorially。 So again。

 imagine our population of interest is this circle。 but in reality， some people get a equals 0。

 So that's this gray partial circle on the left。 and you'll notice that。

It's not the original population anymore。 It's a population of people who actually got a equals 0。

 So we're not hypothetically manipulating anything at this point。 This is just reality。

 Some people actually get a a equals 0。And that's them。 And on the right hand side。

 this blue partial circle， that's a subpopulation of people who actually got a equal  one。

And you'll notice that。These are not the same population of people。

 so we could take the mean of both of those subpopulations。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_98.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_99.png)

And that would be an average difference in the outcome between subpopulations that are defined by treatment group。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_101.png)

So it would be the difference in outcome among two subpopulations。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_103.png)

But the people who get treatment a equals0 might differ in fundamental ways from people who get treatment A equal1。

 so we haven't isolated a treatment effect because these are different people and they might have different characteristics in general so。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_105.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_106.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_107.png)

That's why this distinction is very important between the thing we're targeting。

 which is this average， this causal effect where we're manipulating treatment on the same group of people。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_109.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_110.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_111.png)

Versus this thing that we actually observe， which is。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_113.png)

啊。A difference in means among subpopulations that are defined by treatment。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_115.png)

So conditioning versus setting。You know， as I mentioned。

 this first line is referring to an expected value of y in this subpopulation that actually received treatment a equal1。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_117.png)

But。That's different from the expected value of y superscript1， which is a potential outcome。

 that's the mean of why if the whole population was treated with a equal 1。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_119.png)

So， in general。This contrast。Between。The mean among treated people and the mean among untreated people is not a causal effect。

Because it's just it comparing two different groups of people and these different groups of people might differ。

In ways。That are independent from their treatment， you know， so they differ on treatment。

 but they also might differ on a lot of other variables。

Whereas the expected value of y superscript 1 minus y superscript0。

 this expected value of this difference in potential outcomes is a causal effect because we're comparing the same population of people and the only thing that's different is treatment。

So。In one case， we give everyone treatment a equals 0， in the other case， we give everybody a equal1。

 So we've isolated the treatment effect。In that sense。

So this is a very crucial distinction that we'll need to keep in mind throughout the course。

And we're always targeting this。Something involving a mean of potential outcomes。

But this average causal effect is just one possible causal effect。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_121.png)

So there's a lot of other causal effects that you might be interested in。And。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_123.png)

What you choose might depend on。I the particulars of your study of your research question or even what data you have available to you。

 so some of this will be covered later on in the course。

 but I'll give a few examples of causal effects。

![](img/8c7596c226dd43f1be35a79d7ea6e9db_125.png)

So here。This。Now， instead of a difference in potential outcomes， we're taking a ratio。

 so this is the expected value of y1 divided by y0。

 and so that could you know if we have binary outcomes， that would be a causal relative risk。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_127.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_128.png)

So we're taking them。

![](img/8c7596c226dd43f1be35a79d7ea6e9db_130.png)

Of risk， if everyone was treated versus the risk if if no one was treated。

 so that is a causal relative risk。

![](img/8c7596c226dd43f1be35a79d7ea6e9db_132.png)

Another somewhat common example that people are interested in is the causal effect of treatment on the treated。

And so you'll notice here that we condition on a equal  one。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_134.png)

And that's what we mean by on the treated。 We actually are restricting to a subpopulation。

So the subgroup people who actually receive treatment but。

We're contrasting potential outcomes for that group， so we're still in causal effect territory and。

If this one's confusing， I'll show in the next slide what this represents in a picture and I think it'll be more clear。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_136.png)

But。We might be interested in this because you might be interested in how treatment works among people who are actually treated。

 And sometimes this is important because there might be some subpopulation of people who who I just would never be interested in this particular treatment。

 Maybe it's surgery， and they just are not interested in surgery， but among people who。

Want the surgery。 We want to know how well it works。 So we would want， in that case。

 we would want to know what is the causal effect of treatment on the people who actually were treated。

Another situation you might be interested in causal effects among subpopulations。

This is also known as heterogeneity of treatment effects where there might be some subpopulation which I'll define by V。

 if so V is just some variable， and we might want to know well what is a causal effect in a subpopulation。

 so maybe among people who have a biomarker that's high or low or among what's a causal effect among men or among women or by age or by race。

 we're still isolating a treatment effect but maybe in certain subpopulations。So， let's look at。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_138.png)

The real world versus。You know， another example of a causal effect。

 So we saw this before in the real world， some people get treated。 Some people don't。

 These are different populations。

![](img/8c7596c226dd43f1be35a79d7ea6e9db_140.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_141.png)

But what we actually might be interested in。

![](img/8c7596c226dd43f1be35a79d7ea6e9db_143.png)

In the case of the causal effective treatment on the treated is focusing on the subpopulation who are treated。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_145.png)

So that's this little semicircle that's the treated population。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_147.png)

But you'll notice then when we get to World one versus World two。

 we're restricting to the same group of people。So we have this gray semicircle and this blue semicircle。

 but they're the same shape， they represent the same people。

 and now we're giving everyone treatment equals a equals0 versus treatment A equal 1。

 This is a causal effect of treatment on the treated。

 It's a causal effect because it's the same group of people。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_149.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_150.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_151.png)

It's this population of people who， in reality。We're treated。 But now we want to imagine。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_153.png)

In War1， what would have happened had we not treated them。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_155.png)

And in World2 was sort of what actually happened that we where we actually did treat them。

 So that would be the causal effect of treatment on the treated。

 The important distinction here is that。

![](img/8c7596c226dd43f1be35a79d7ea6e9db_157.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_158.png)

We're still comparing the same。Group of people。 So we can define a subpopulation。

 and that's fine as long as。

![](img/8c7596c226dd43f1be35a79d7ea6e9db_160.png)

On the treatment side of things， we're doing the same thing to everybody。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_162.png)

So in World one， we're treating everybody， we might not be treating everybody in World two。

 we're treating everybody and then we're contrasting the meat。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_164.png)

![](img/8c7596c226dd43f1be35a79d7ea6e9db_165.png)

But again， we're going back now to this fundamental problem of causal inference。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_167.png)

We only observe one treatment and one outcome for each person。Again。

 that's the fundamental problem of causal inference。 and so what we're moving into is。



![](img/8c7596c226dd43f1be35a79d7ea6e9db_169.png)

How do we then use observed data to link observed outcomes to potential outcomes？So in reality。

 for each person， we're going to see one treatment， and we're going to see one outcome。

But we want to be in this， we want to infer something about what would have happened。

And how are we going to do that。And so what we will need to do is make assumptions。And。

So we'll have to make assumptions to link observe data to potential outcomes。

And so a major focus this of the course will be。Once I have data。How do I then？Link these things。

 how do I estimate causal effects from observational data？

So we see what the fundamental challenge is， we've defined causal effects。

 and now we need to really focus more on。How do we then link these things together。

 with observed data and potential outcomes so that we can get the causal effects of interest。

