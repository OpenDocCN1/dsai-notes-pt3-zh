# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p40 11_推断：可能出错的地方.zh_en -BV1L9Fde5EXS_p40-

There are a number of things that can affect the quality of inferences that we make from data。

 this lecture talks about what can go wrong with inference。



![](img/3ff03f33f1d3f3c4af78f9bde2c99b83_1.png)

![](img/3ff03f33f1d3f3c4af78f9bde2c99b83_2.png)

So the basic problems that occur when we're making inference it usually result from a violation of the assumptions that we make about the population。

 the sampling process or the model for the population。

 And so so I'll kind of talk about each one of these things and kind of what happens when there's some sort of violation So the first problem is that the population is not well definedfined so this is a big problem because a vaguely defined population leads to vague inferences and can often and the sign that you have a vaguely defined population is that often the results are kind of uninterpreable or difficult to interpret。

 And so this is really a problem that isn't really solved by the data or a fixing the data really it's about thinking a little bit more clearly about what type of population you're trying to make an inference about。



![](img/3ff03f33f1d3f3c4af78f9bde2c99b83_4.png)

![](img/3ff03f33f1d3f3c4af78f9bde2c99b83_5.png)

Now the second problem you can have is it incorrectly specifiedifies sampling process okay now what this results in is that the sample data will not be representative of the population often this is called a convenient sample so when you collect data you collect data in the most convenient way and it may just involve。

 for example， if you're studying people in an observational study or in an experimental study you just kind of take whatever people come your way and enroll them in the study this may not involve a sampling process that represents your population it's often just a convenient sample and so what the result of this is that you'll have what's called selection bias so the people in your study will represent a selection of the population but not really the entire population and so the result is that if you fit any models if you estimate any characteristics of from your data。

 those things that you estimate won't actually apply to the target population that you originally design it。

 they will apply to some other population that you may not be able to accurately define。

Even if your model for the population is correct and even if you have a sense of what your target population is。

 if your sampling process is not well specified or well characterized or if you don't understand it properly。

 then the data that you collect and the inferences that you make will only apply to some other population that you haven't really well characterized yet。

 so that's what can result from kind of incorrectly specifying your sampling process。

The last part is incorrectly specifying the model for your population Now recall that we said that previously that all models are wrong and so you for sure you will incorrectly specify the model for the population and so really the goal is not to get the correct model but rather to get a model that's a reasonable approximation for what the population looks like and so if you have the wrong model a couple of things may occur first there may be uncertainty in your estimates from the data that are not accounted for so you may underestimate how certain you are about certain characteristics of the population any parameters that you estimate from your model may end up being uninterpretable and so if your model is incorrect。

 it doesn't correctly reflect the relationships in your data in your population then the parameters that you estimate will not really apply to that population and may be difficult to interpret Furthermore in prediction types of problems if you don't have the right model then it's pretty straightforward to see that your predictions this may be poor and they may have a high error。



![](img/3ff03f33f1d3f3c4af78f9bde2c99b83_7.png)

R。

![](img/3ff03f33f1d3f3c4af78f9bde2c99b83_9.png)

So really what you need to know is kind of what are the questions that you need to be asking when you're involved in a data analysis process okay and so the three basic questions related to the different kinds of violations that you might encounter when doing inference so the first is can we characterize the population that's a very simple question and the solution is to really just do more thinking beforehand okay before you engage in the inference process just take a little bit of extra time to think about what the population is and maybe engage in experts in this area。

 they may be inside or outside of your organization。

The second question you want to ask is do we understand the sampling process Okay now in terms of so what you want to do about this is you can either collect your own data in which case you can specify what the sampling process is going to be。

 you can maybe collect auxiliary data about the population characteristics so if you have auxiliary data about the population maybe certain features of the population。

 then you can quantify the differences between the sample that you collect and the auxiliary data on the population to see how different they are。

 for example， for example， you might have data on the sex of people in your study and so you might want to know well。

 if the population is roughly 5050 male female but your data set is say 70 30 male female。

 then you can characterize that difference between the data that you collected and the population you're trying to target you can be more specific about the differences between the two。

Okay so auxiliary data about the population can be very useful for characterizing any sort of selection bias that you might have in your sample The last question you want to ask is do you have an appropriate model for the population it's not going to be a perfect model but you hope it' it's a reasonable approximation this can be kind of addressed through a thorough exploratory data analysis or by using for example。

 things like robust methods for inference when you're fitting statistical models Another approach is to use very flexible models like machine learning methods that are useful for kind making very accurate predictions without you having to specify very carefully what the model is often lots of machine learning types of techniques can just learn the model from the data without you having to be very specific about it so that can be very useful when you don't have a good understanding about what the relationships in a population are。



![](img/3ff03f33f1d3f3c4af78f9bde2c99b83_11.png)

![](img/3ff03f33f1d3f3c4af78f9bde2c99b83_12.png)

The final challenge to making good inferences is sampling variability Now I've left this to the end for a reason because sampling variability will exist。

 even if you've done everything else right so you've defined the population you describe the sampling process you've developed a reasonable model for the population by virtue of the fact that you are sampling data you will introduce uncertainty because you don't have all the data and so every time you draw a sample。

 it will be slightly different and anything you estimate about the population will be slightly different every time you you sample data and so we'll talk a little bit more about this in the lecture about interpreting data analysis。

 but the important thing to know here is that you should always be asking for a measure of uncertainty along with any estimate that's obtained from the data so any summary statistic or any model parameter that that you can estimate from the data you should always be asking for a measure of uncertainty that comes along with it because there always will be uncertainty if you're sampling data from a population。

So just to summarize briefly， always think about what the population is going to be。

 always assess the sampling process and think about differences between what the data that you collect and the population that you're trying to make inferences to always try to diagnose your model as carefully as possible or use a very flexible method to kind of model your population and lastly。

 always require a measure of uncertainty for any estimate that you draw from the data so these are the kind of things that can go wrong with inferences and how you can try to protect yourself from these things。



![](img/3ff03f33f1d3f3c4af78f9bde2c99b83_14.png)

![](img/3ff03f33f1d3f3c4af78f9bde2c99b83_15.png)