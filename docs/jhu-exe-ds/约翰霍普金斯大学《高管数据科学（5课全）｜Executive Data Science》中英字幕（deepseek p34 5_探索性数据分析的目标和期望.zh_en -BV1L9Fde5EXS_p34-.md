# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p34 5_探索性数据分析的目标和期望.zh_en -BV1L9Fde5EXS_p34-

Expllororatory data analysis is an important part of any data analysis process this lecture discusses the goals of EDA and what to expect from it。



![](img/73e78d769962b4ef39d4fb67fdd8143f_1.png)

Some of the key questions that you want to think about before engaging in an exploratory data analysis process are basically do you have the right data to answer the question that you're interested in and then do you need to get other data if you don't have the right data to answer your question and then finally given what you see from the data and given what you make of everything that's going on in there do you have the right question because it could be that maybe you thought you had the right question and you thought you had the right data set。

 but when looking around in the data set exploring what's in there。

 you realize that maybe the question is better asked a different way or maybe you need to just slightly refine the question。

 make it more specific or maybe focus on specific variables so the goal of EDA is to think of it' to get a chance to look at the data。

 see if you've got the right data， do you need to get more and do you need to refine your question at all。

This lecture we're gonna to talk about you know whether you have the right data to answer your question and then another goal that of exploratory data analysis assuming you pass that first port first part is to think about how can you develop a sketch of what the answer to your question might be one of the end products of Exploratory data analysis is to really get a sense of whether the solution is out whether the solution exists and what it might look at and then from there if you want to continue you might go into something more like formal modeling which we'll talk about later So this lecture we'll talk about figuring out whether you've got the right data for the job now I assume you've already formulated your question but it's good to here to always double check to make sure that it's a sharp as it can be so that you can kind reduce the number of variables or the kind fact features that you might want to look at before you kind of go ahead。



![](img/73e78d769962b4ef39d4fb67fdd8143f_3.png)

Now the first thing you want to do of course， is you have to read in the data。

 you can't do an exploratory data analysis without reading in the data。

 but the next assuming you can do that the thing that I like to do is what I call check the packaging imagine you've got some box and there's something inside you want to get at and you can't get it yet so you kind shake it around maybe measure it see how big it is is it bigger than a bread box and see what kind of noises does it make when you shake it。

 things like that So that's kind what you're trying to do with your data here。

 your data is the thing that's inside the box but you want to make sure see what everything's kind of the right shape and size So some of the things that I like to check are do you have the right number of rows and columns if someone if the person or the way that you've got the data youre expecting there to be 10 rows。

 then there should be 10 rows in the table for example they're gonna be 60 features there should be 60 columns for example in a table So just make sure you got those dimensions right basic details about the packaging of a data if you were told that certain。

A were gonna be included in the data。 Just check to see that they are in fact。

 included in the data right It's a very simple check。

 You don't have to look at any data to figure that out。

 you just basically had to look at the metadata， things like the variable names and the number of rows for example if if there's any other metadata that you might need things like codebooks。

 things that describe what the variables are， make sure that comes with the data so this can all be done without actually looking at any numbers yet now the next thing I like to do is to check the edges of the data set。

 And so for example， if you're looking at the table looking at a table I like to check the top in the bottom so just look at the first few rows and then maybe look at the last few rows So the first few rows are are helpful just make sure that you've got the right numbers there the things that you were expecting to see I find it's very useful to look at the last few rows just to make sure for example that the data is read in properly that you've got all of data that you were expecting to get often in data files some junk at the end some comments maybe some。

Notes that someone put in there， especially if they were exported from an Excel spreadsheet so you usually don't want to read that kind of stuff in。

 so looking at the bottom of the data can so to speak can kind of help you to see if there's any that kind of junk down there。

 and you want to check to see if the data formatted correctly。

 does it look like the right numbers are in the right columns and the right numbers are in the right rows sometimes those things can be shifted by one or two So you want to make sure you got everything correct there。

 if you got data for example with dates often looking at the top and the bottom can be useful because if they're sorted by date。

 you can see if if the range is correct the earliest and the latest dates are correct and so so that's another thing that you might want to check for And so just looking at the very edges of the data can be very useful can be useful to flag a number of just kind of basic problems that very often occur and are usually easy to fix but but once you kind of get into a data analysis if you discover these things later it can be a real pain in the neck to deal with。

So the next item that I always try to think about when I'm looking at a new data set。

 I'm just getting involved in a data analysis is what I call ABC， always be checking your N。

 Okay so every aspect of your data is gonna to have some kind of count or a number associated with。

 for example， you might there's gonna be an a total number of observations or your sample size。

 I that what you expect it to be Are you expecting a certain number of columns is that know there's gonna to be a number of columns you should be should always check that n。

 But then also you know within the data set。There's going to be a certain within the data。

 there's going to be certain numbers that you expect， for example。

 if if you have a number of subjects， you want to count the number of subjects or units in your analysis。

 if every subject was measured three times， you want to make sure that every subject's got actually three measurements associated with。

 right So there's all kinds of just ends that you can check within your data set and kind of around your data set to make sure that everything is kind of in structured in place。

 okay。So the next thing you want to do is actually just look at your data and to me。

 the easiest way to look at the data to determine if there are any problems is to make a plot。

 So making a plot is useful in two ways。 the first way it's useful is for setting expectations about your data so when you look at a plot。

 you get a sense of kind of how the variables are related to each other if you make a scatter plot if you make a box plot you can look at the distributions of the variables to see whether they're skewed or they positive and negative values are you expecting positive and negative values things like that。

 So plots can kind of very quickly reveal this kind of information in a way that often tables cannot because one of the things that plots give you is they give you a summary plus a deviation and very often tables will only give you the summary。

 So for example， they give you the mean or the median but a plot will allow you to visualize both the mean and the deviations from the mean And so you'll be able to see if。

There are very large deviations that are perhaps unexpected and or there are kind of values that。

 for example， negative values or maybe there are positive values that you weren't expecting that don't appear a correct right so I think a plot is very important to make not that there is no role for tables in data analysis。

 but a plot has a unique ability in my opinion to show you both what to expect and what not to expect in the sense that know what the deviations are from that expectation so look at the data and make a plot。

The next useful thing that I like to do with datasets is to try to validate it with at least one external data source so obviously how you do this will depend on exactly what your problem is。

 what your question is and the data that you have at hand but it's nice to be able to check certain aspects of your data data that they match something outside you know that the data that you got are at least kind of within the realm of reality so even just a single number can be useful so for example。

 if you know that the average level of some feature in your population is on the order of plus or minus whatever 10 and if you look in your data and you have a measurement on that same feature and it looks like the average is around 10 well that can be useful just so you know that roughly the mean of the distribution in your data corresponds to kind of what you might expect in the population Another thing you can do is to look at some measurements that you have in your data and compare it with measurements。

A similar， if not exactly the same feature， but things that you would expect to be correlated with what's in your data and check to see if they're actually correlated And so that way you can get a sense of okay well whatever I'm measuring in my data it's measuring the same thing that this other metric is looking at And so there may be some there may be some validity there。

 So trying to just make just doing a little check to see that your data matches with something that's kind of independent and outside your data can give you a little bit more confidence in the idea that your data is properly formatted and it came to you in the right way。

So now that you've checked the packaging， you've checked your ends。

 you looked at the top of the bottom of the data set。

 you've made maybe a simple plot just to kind of visualize the data and you validated with one external data source。

 The next thing to do is try to take a stab at your solution。

 And I won't get into that very much right now。 But my only point to make here is that you should try the easy solution first what is the most obvious thing that you would do in the kind of simplest of scenarios right So because you you want to be able to start with something simple。

 and then you can kind of get more complex a little bit later。

 but often the simplest thing can be very revealing。 That's the key。

 And often the more sophisticated approaches we give you a little bit more insight。

 but not any more than you would have gotten from just looking at the very simple。



![](img/73e78d769962b4ef39d4fb67fdd8143f_5.png)

Picture or table or whatever it is that you try to do it first。

 and the goal of this is really to start developing what I call a primary model right。

 so a primary model is the model on which you kind of base your other analysis around And it's not It's not gonna be permanent。

 You may change what the primary model is later。 it's kind the focal point。

 your initial focal point for your analysis。 and then you'll try all kinds of other analysis。

 secondary analysis that I called that will try to test to whether your primary analysis is appropriate or not。

 And many times you'll find that actually your primary analysis was not right。

 and you'll focus on a different model， you make that your primary model。

 But sometimes your primary model will hold will hold up and then you'll be able to stick with it。

 but it doesn't matter at first of what you choose。 you want be able to say craft the solution。

 then and then kind of hang onto it for a moment and try to do some secondary analysis around it to see if your initial solution holds up。

 So the idea is that you want to build if you're kind of making a case for something。

 You want to build some。Fia evidence and so the primaaccia evidence is really this initial solution。

 it's the simplest solution that you can think of at the moment。

 and then you'll try to pick away at to see if it falls apart。

 but one of the endpoints of exploratory data analysis is to develop this primaacia case to develop this primary model。

😊，So once you've gone through this process， you looked at the data。

 you check to see that everything's valid。 You want to be able to follow up。

 Okay so this is the point where you're asked yourself。

 look those three questions that we talked about in the beginning。

 Do you have the right data do you need to get other data so do you need to collect more。

 do you need to ask for more in order to and do you have the right question or does it need to be refined a little bit。

 So once you're here you may need to slightly revise a few things with your data and with your question But once you've done that if you want to move on。

 then you can start using exploratory data analysis techniques to kind of refine your primary model and then move on later into more more formal modeling。



![](img/73e78d769962b4ef39d4fb67fdd8143f_7.png)

![](img/73e78d769962b4ef39d4fb67fdd8143f_8.png)