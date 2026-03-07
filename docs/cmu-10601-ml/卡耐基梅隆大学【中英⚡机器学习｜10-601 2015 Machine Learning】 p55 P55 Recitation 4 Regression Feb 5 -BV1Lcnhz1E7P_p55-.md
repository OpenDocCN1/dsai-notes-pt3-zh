# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p55 P55 Recitation 4 Regression Feb 5 -BV1Lcnhz1E7P_p55-

Okay I guess we will get started now there's not as many people as when I first did it。

 but this I guess maybe it moved to a different room also if you came here expecting Nicole。

 sorry to disappoint， but so today we're going to be talking about Im just going to go over some things that Tom talked about earlier in class this week。

 mostly we're going to focus on linear regression which just a reminder if you're performing some sort of regression。

 you want to predict continuous value and then talk about logistic regression again。

 and this is for classification which is when you want to predict a discrete value。

And then at the end， we're going to go over gradient descent a little bit because that is a useful way to find the parameters for logistic regression。

And in general， it's a very general optimization technique you can use it a lot。

 so it's a good thing to be familiar with。So to remind you of the definition， oh， and at any point。

 if anyone has questions， raise your hand and we can talk about whatever is confusing at the moment。

 so for regression you want to predict continuous valued output for your given input。

 so you have a set of labeled training examples which are would be ddisional X vectors， your input。

And associated with each input， you have a real valued output， why。😡。

And we want to learn this function， F that maps x to y。

 so we can use that to predict future values of x that maybe we haven't seen before。

 predict the label or the output Y that goes with them。😡，And in the regression settinging to do this。

 you assume that your output Y is some deterministic function of x。Plus， some zero mean noise。

 typically used human Scion。For the specific case of linear regression。

We assume a linear relationship between inputs and outputs that is we have the same kind of data as the general regression setting again we want to learn this function that maps our inputs to our real valued output。

 but now we assume that this function F is a linear function of the inputs so you maybe have some sort of intercept W0 and then for each of the features and a particular data sample for the J feature of the I sample you have some weight associated with that and then you sum up over all of the weights and whatever dimension of your data。

So that's the setup we have for linear regression to go through a simple example to make it concrete。

 this is a one- dimensionional example， so say you collected data about people's commute times。

 you assume that people who live farther away from campus it' likely to take them longer to get to campus。

 but you know there is some variation， maybe they have a lot of hills to go or something but so you collected information。

 you pulled people and said you find out how far they live from CMU and then the time it takes them to walk to campus。

And like there's a general trend as you would kind of think。 so now with this information。

 you want to predict the commute time for a new person who lives 1。

1 miles from campus so that would be about like right here。

 we don't have anyone who's really living at that point so we can't like we don't already know the answer we'd like to predict what it's going to be so does anyone have any ideas about what to do。

Obviously， we're going to talk about linear regression。

 but I didn't know if anyone had any other ideas。Yeah。Oh， you can say linear regression。

 the obvious thing or。Okay， so yeah what。Yeah， yeah exactly so that's what we're going to be talking about Does anyone have any other ideas？

Just to get you thinking about ways you can predict for new values given a set of current values。

Okay， well， one thing I thought someone might say would be maybe you could just look at points nearby。

 so say this person lives 1。1 miles away。 you see that you know you take whatever distance away from that point and say oh。

 it's maybe the average of these values of people who are live a similar distance away。

 So that's one approach you could do， but that's not what we're focusing on right now。

 but if you were thinking about other ways you might want to solve this problem yeah。Yeah， yeah。

 so that would be a nearest neighbor's approach？Yeah， yeah， so that's another way you can do it。

I mean， what you ultimately decide to do depends on the problem that you have。 So maybe in this case。

 we thought that there is kind of a general linear relationship。

 but if we didn't think it was a linear relationship and something like KNN is it doesn't make that assumption on your data that it does follow that linear relationship。

 So depending on what your problem is different things may be more or less appropriate。

 you can I mean， sometimes it's interesting just to try different approaches and see how the results differ or if they're similar。

Yeah， so in this case， we're going to fit a line to the data points。

 we are making this assumption that they do lie on a line。So if we could find this line。

 we could easily make a prediction for any point because this line。Kd of extends， we can just I mean。

 I just fit it to the points that we have here， but you could think about it extending farther up and it doesn't really make sense if someone lives in negative distance from campus。

 so at that point it doesn't really work。 But so if we fit this line。Then we'd go and we find 1。

1 miles， and it looks like this person， it would take about 23 minutes for them to walk to Samuel。

So what we're interested in in order to make this prediction is finding this line from the points that we have。

So we're going to formally define our input， the dependent variable， the distance from campus。

 which was。Potted there。 and then that output is the commute time。

 And we want to predict Y for an unknown X so we haven't seen before。So， again， in general， in。

Regression， you assume that the output is some function of the input plus some zero mean noise。

And for the case of one dimensional linear regression， this line。

 it really only has two values that define it， the intercept， W0 and the slope， W1。

And we want to learn these values， the parameters of W。And the way we do this。

 as you've done for several different kinds of problems in class。

 is to maximize the conditional likelihood of the data that you see。😊，So。Remember， this is our setup。

 we assume it's a function， you can model it as a function。

 and for the case of linear regression in general， we have this linear relationship between or we assume F is a linear function of the input with this weight vector W。

Just some new notation for mathematical convenience and to kind of tighten things up as we're going through。

 let's put all the elements of w including the intercept w0 into one vector it'll be a d plus one dimensional vector and then we're going to make this transformation of x phi of x where we add in this extra1 component to the top of it and you can see if we do that then we can rewrite F of x。

 which has been w0 plus like wj times xj as then we can move this essentially we're removing this w0 into the sum because the first component of phi is going to be this one so then we'll multiply1 times w0 and that's how we get that and then the rest of the sum is still the same so then we can write that as w transpose times v。

And then we can learn W from the data by maximizing the conditional likelihood。

 which we write just our estimate W hat， maximize the likelihood of P of y given x。

 do you all want to do this interactively， or I can just click through， doesn't matter。No preference。

 okay？Okay， then I'll just click through， it'll be faster again if you have any questions or anything。

 stop so we assume the data are independent so we can model this joint probability as the product of the individual probabilities。

And then we can take the log because log is an increasing function。

Say the log of x is greater than the log of y。 That means that x is greater than y。

So this is equivalent。And now。