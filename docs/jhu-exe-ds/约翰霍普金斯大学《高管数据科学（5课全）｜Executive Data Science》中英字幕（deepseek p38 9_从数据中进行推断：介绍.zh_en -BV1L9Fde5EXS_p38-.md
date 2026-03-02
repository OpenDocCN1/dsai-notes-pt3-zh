# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p38 9_从数据中进行推断：介绍.zh_en -BV1L9Fde5EXS_p38-

![](img/72d750beee470a79ef357af4162c8450_0.png)

Inference is the task of making statements about things you can't observe This lecture is about the ingredients you need to make useful inferences from data。



![](img/72d750beee470a79ef357af4162c8450_2.png)

![](img/72d750beee470a79ef357af4162c8450_3.png)

So the goal of inference is to be able to make statements about things we can't really observe directly and we also want to be able to characterize our uncertainty about those statements that we make So these things that we can't observe the things that we want to make inferences about these are usually referred to generally as the population okay and then to make inference what we do is we collect a sample from the population and the sampling process that we use result in our data set okay so we have a data set that results from a sampling process that draws from a population so to make inferences from data you need three simple ingredients first you need to be able to identify the population to which you're making these inferences okay and of course you have to have a question about that population。

 but that's kind of secondary once you've identify the population then you you can talk coherently about what you're making inference about。



![](img/72d750beee470a79ef357af4162c8450_5.png)

![](img/72d750beee470a79ef357af4162c8450_6.png)

The next thing you need to be able to do is to describe the sampling process。

 you need to be able to tell a story about how the data came from the population and ended up in your lab okay if you can't describe that process。

 then it's going to be very hard to kind of understand how valid your inferences are from the data。

 the better and more clearly you can describe how the data came to you。

 the more stronger your results will be now the last thing you need is a model for the population you need a model for how either elements of the population interact with each other or how they're related to each other。

So defining the population is far and away the most important task if you can't coherently describe the population then you can you can't really make any inferences because there's building to make inference to so make sure that you can accurately characterize your population is going to help you tell the story better in the end after you analyze the data so similarly it's important that you identify an important question that you want to ask and answer but presumably you've done this already so just as a very quick simple runningny example here's a basic population of 10 penguins okay and each of these penguins has a turquoise hat or a purple hat and so the basic question that we want to ask is what proportion of this population of penguins has is wearing a turquoise hat okay so that's basically it now the problem of course is that we can't collect data on the population right so you they're penguins after all and we can't take care of all of them so we need to draw a sample from this population so the sampling process is the manner in which the data come to you。



![](img/72d750beee470a79ef357af4162c8450_8.png)

![](img/72d750beee470a79ef357af4162c8450_9.png)

![](img/72d750beee470a79ef357af4162c8450_10.png)

And this gives you the data set so let's say we're going to sample three penguins， okay。

 and the way that we sample those three penguins is we just we stand there in front of these 10 penguins and we take the first three that walk up to us Okay。

 so then we we have our data set with just three penguins。



![](img/72d750beee470a79ef357af4162c8450_12.png)

And so now the model for the population describes how the features of the units in the population are related to each other and this model can be more or less complex。

 depending on the type of question that we're trying to answer but the important thing is that the model connects the data that we observe to the population that we don't observe and so it's basically a little cartoon of how the world works。

 So a couple of examples of what a model might consist of is that we might assume， for example。

 that the units of the population are independent of each other So imagine that the different penguins in this population are wearing different hats。

 and the fact that one penguin is wearing a turquoise hat doesn't really influence whether another penguin is going to wear a purple hat or a turquoise hat。

 So they're all kind of independent of each other。 That's one assumption that will make that's part of our model。

 another attached assumption that we might want to make is that certain features of the population are are linearly related so there are linear relationships between them and there are many other kinds of things that you might want to assume about a population if you。



![](img/72d750beee470a79ef357af4162c8450_14.png)

![](img/72d750beee470a79ef357af4162c8450_15.png)

your question is a little bit more complex。 Now， the question that we're asking here is very simple。

 We just want to know what's the proportion of penguins with turquoise hats。

 So we don't have to make too many assumptions about the population in order to answer that question。

 So given our little data here of three penguins。 we want to estimate what's the proportion with turquoise hats in the population。

 So from the data， we can estimate that it's one third of the data。



![](img/72d750beee470a79ef357af4162c8450_17.png)

One thirdd of the penguins have turquoise hats。 So we'll assume that one third of the population wears turquoise hats。

 So that's what we're going infer from our data set。 Our final estimate is onet or 0。

33 penguins with turquoise hats。 Now it turns out because we know the population that the truth is about 0。

4 penguins actually we're turquoise hats are  two5s So our estimate is 0。

3 roughly And the truth is 0。4 And so the question is， well how do we know if 0。3 or 0。

33 is a good estimate so we'll talk about that in the next lecture in terms of how do you know whether you've made a good inference or not？

 But the point is that our estimate is 0。33 and the truth is 0。

4 So there's a variation there as we would expect。 but that's our estimate for the population level feature。



![](img/72d750beee470a79ef357af4162c8450_19.png)

![](img/72d750beee470a79ef357af4162c8450_20.png)

![](img/72d750beee470a79ef357af4162c8450_21.png)