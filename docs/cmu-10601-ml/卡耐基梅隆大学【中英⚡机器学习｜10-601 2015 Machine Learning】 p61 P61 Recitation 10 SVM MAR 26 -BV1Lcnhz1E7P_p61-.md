# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p61 P61 Recitation 10 SVM MAR 26 -BV1Lcnhz1E7P_p61-

Okay， I guess we'll get started now today my plan is talk about support vector machines， kernels。

 and then a bit on lagGe multipliers， which。Part of an we made it extra credit on the homework。

I think it's a useful skill to know。 Okay， so we'll start with support vector machines。

 which solve a general problem of classification， which， as I'm sure you're。😊。

Intimately familiar with by now is when you have a discrete label that you want to predict。

 so say for support vector machines， you might have points。Some are labeled positive。

 some are labeled。Negative。And you somehow want to be able to predict kind of the general。

Let me it a better picture。A general rule that you can use in order to predict future points that you get。

So in this case， if we wanted to draw a linear decision boundary。

 there are several that we could draw one。Might look like that。

 So you can see we have all the positive points on one side and all the negative points on another side。

 That's not the only decision boundary we could draw。 We could also have one that looked more like。

This， so of the two， the dashed line and the solid line。

 Does anyone have any particular attachment to one over the other。

 Do you think one would be a better。Boundary to have than the other。Yeah， the solid one， right。

 So what's the intuition behind why the solid one is maybe a better decision boundary。Yeah。

 so that's getting into the idea of margin， but really another way kind of this a similar perspective on that is that you can see there are some points that are pretty close to the boundary。

 so what if we were to move this point just a little tiny bit。Over here。

 it seems like it's pretty similar， but if we use this original dashed line as our boundary。

 then all of a sudden we're predicting that it's the totally opposite label。 So in that sense。

 if you have this large margin idea， it's a bit more stable to if your data is moved around slightly。

😡，So that's kind of why。We would prefer。A line like the。Solid one here。So what is your name？

Sorry whatng okay so like Shang mentioned， the idea here you have a larger margin in that it's sort of like the distance。

From your points。To the decision matterer， you want to kind of like maximally separate the points on one class from the other。

So in this。Formulation， kind of where SVM gets its name， is that the points that lie。

On this boundary， maybe you have a couple others are called support vectors and the idea is that the classification。

 the results of your classification really hinges only on the values of these support vectors。

 so over here it provided everything's all negative we can have a point here over here over here it really doesn't matter the only thing that we need to keep track of in order to maintain our solution is in this case just three values so maybe you have thousands and thousands of points。

 but you know only 10 or so our support vectors so really don't have to。

It doesn't depend on as many data points。And so we can represent this decision boundary mathematically by。

Specing a value for this particular line。We'll say it's W transpose x plus B equals zero。

 so in lecture when Nina went through， she assumed that everything was centered。

 so essentially you had B equals0， but you can also do this kind of slightly more generally where you just sort of shift your data and B can be nonzero。

And then。The way you predict a value is that。You say。

 so let's say this minus has a class labeled negative1 and the plus has class labeled positive one。

Then the way you're going to predict that value is everything that's on the negative side here satisfies。

😡，W transpose x minus B。Is less than。Negative one。And here on this side。You have。

W transpose x plus B is greater than1。So now if we get a new point。Greater than or equal to。

So now if we get a new point， say maybe we have a point。Like right here that we get。

If we already know W and B， and then of course we know the coordinates of the point。

We have a point right here， don't know what it is yet， but we know W， we know B。

 we just make this calculation， so maybe here we say w transferpo x plus B equals 2。

Which is greater than one， so we're going to say that this point is positive。

And then suppose we have a point all the way out here。And we want to guess。

 make a prediction of what its label is， so here again we're going to oh sorry that should be a plus we're going to calculate Ws transpose x plus B and say here maybe it equals negative 15。

And so since it's less than negative one， we're going to say that this point。Is the negative one。

It's class negative。And so here you can kind of get a sense that this was sort of close to the margin and the value is 2。

 This was farther away from the margin。 and value is negative 15。

 So the magnitude here kind of indicates the confidence we have in this particular prediction。Yeah。

 so our final prediction rule。It's just the sign。Of W transfer x plus B。Yeah。Yeah。

 yeah so here if it's exactly on this line it would be zero here is positive one here is negative one so right now this was just talking about the hard margin formulation of SVM where you say that nothing can be in the margin at all。

 everything has to be linearly separable and nothing can be in the margin so in that case that's enforced on your training data but when your test data come in you don't know like you didn't know what the values were as you were learning your W and B parameters。

 so really you can't really say there so because otherwise like I mean I guess you could say if something's in here like oh。

 I'm not really sure but if you just want to still get a guess for what the value is。

 if you just do the sign then you can still get a value for your predicted value of y even if it is in the margin。

Yeah， so this was just assuming we already know the W&B parameters。

 but really what we're interested in if we have a data set is we want to find these values。

 so we can set it up as an optimization problem like we talked about in class。So if we。

Say that this distance here。Is the margin？And we'll call it gamma。啊。The margin。

That's inversely proportional。2。The norm of this vector W。

So we want to maximize gamma here while obeying these constraints that all of our negative points are on one side of the margin and all of our positive points are on the other side of the margin。

Did this one not No， it doesn't go okay。So our optimization problem here is going to be。

We want to maximize gamma。Subject two。First of all， when the let's say our。Inputs are X。

And the label is why。啊。Say x is indisional。Each lie。Is negative one or a positive one？

So we want to obey the constraint that。啊。W transpose X plus。

