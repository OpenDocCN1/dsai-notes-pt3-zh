# YannicKilcher【中英⚡AI经典论文领读(全203篇)(上)｜Papers Explained】 p03 P3 TAPAS：基于预训练的弱监督表格解析方法（论文详解） [BV1o3xLznExj_p3]

Hi there。 Have a look at this table on the left。 So in this table in each row。

 you can see following things。The name of a wrestler。

 the number of times that wrestler has been a champion and the combined number of days where that wrestler has been a champion or like the sum of the length of all their championships。

Along with the column that is the rank， and this is ranked by the combined days attribute。

So this table is very interesting by itself， but if you look at the right。

 we have a couple of questions and let's try to answer them which wrestler had the most number of res。

 So for that you need to go to number of rains column right。And you need to mentally sort them。

 And you'll find out that 8 is the highest number。 And therefore。

 Rick Flair is the wrestler you're looking for。 Second question。

 the average time as a champion for top 2 wrestlers。 Now， we need to go the top two wrestlers。

 we can guess that pertains to the rank。 And then so we want the average of these two numbers。

You even have questions such as which of the following wrestlers were ranked in the bottom three？

Which the answers would be all of those。 And then after that， out of these who had more than one re。

 And you can see that's Dan Severn。So the paper that we're having here is trying to answer questions like this if given a table。

 As you can see， this is a pretty pretty hard task。 and so pretty excited to read this。

 The paper is called tapas， Weekly supervised table parsing via pre training by Jonathan Her Siig Pol。

 Christoav Novak， Thomas Miller， Francesco Pciino and Yunne Martin Eisenchlo， full disclaimer。

 I know these people。 So I might be slightly biased。



![](img/79924697bbe6b2c1351cf2ac73f7eb41_1.png)

![](img/79924697bbe6b2c1351cf2ac73f7eb41_2.png)

![](img/79924697bbe6b2c1351cf2ac73f7eb41_3.png)

Alright， so you've already seen the task。 The task is you are given a table and a question and you're trying to answer that。



![](img/79924697bbe6b2c1351cf2ac73f7eb41_5.png)

Now， there it's not， it's not as easy as that， but the table questions come in different forms。

 as you have seen， Sometimes you just need to select a cell from a table like we have here。

 the first question。

![](img/79924697bbe6b2c1351cf2ac73f7eb41_7.png)

I simply most number of res。 I simply select whatever that is。

 So the answer here is already in the table， Rick Flair。



![](img/79924697bbe6b2c1351cf2ac73f7eb41_9.png)

![](img/79924697bbe6b2c1351cf2ac73f7eb41_10.png)

And this they call a cell selection task。 This is wherever you need to select a cell。

 the same for these bottom here。 So which of the following wreers are ranked in the bottom3 and out of these which one of more than one range。

 all of these answers are in the table somewhere。 The second thing is what they call a scalar answer。



![](img/79924697bbe6b2c1351cf2ac73f7eb41_12.png)

![](img/79924697bbe6b2c1351cf2ac73f7eb41_13.png)

That is when。The answer to be computed is a number that is not in the table。

So these average time here。Which turns out to be 3426 is nowhere to be found in the table。

 So there actually needs to be a computation performed by the model。



![](img/79924697bbe6b2c1351cf2ac73f7eb41_15.png)

And lastly， you have these things called ambiguous answers。 Now， the ambiguous answers refer to a。

Thing where it is a number that you're looking for。 So how many。



![](img/79924697bbe6b2c1351cf2ac73f7eb41_17.png)

But the number here is in the table。So you can think of this in terms of training data if you have a task like this and you have training data and you just have the question。

 you just have this question and you're given the answer too， right。

🎼You can teach your model either to select this number here， or you can teach your model。

That would be wrong， right， because how many world champions are there with only one rain。

To simply select this cell here is not correct， because that cell， even though the number is 2。

 it doesn't mean the same thing， It's not counting， right。

 So the correct programme here would be to count the number to count the cells where there is a one here。

 which is also two。 And they call the situation ambiguous answer。

So you might have already guessed that a single model that does all of this needs to sort of have multiple modes。

 That's exactly what they propose。 So they propose a model。



![](img/79924697bbe6b2c1351cf2ac73f7eb41_19.png)

That takes in the table and the question。And then， in the first step。It selects its mode。

So the mode is either the cell selection。Or it is to compute something。



![](img/79924697bbe6b2c1351cf2ac73f7eb41_21.png)

And then whenever it's a cell selection， it simply has a component to select cells。



![](img/79924697bbe6b2c1351cf2ac73f7eb41_23.png)

But when it's a compute， it needs to decide in the second step， what to compute。



![](img/79924697bbe6b2c1351cf2ac73f7eb41_25.png)

And then also select the appropriate cells。

![](img/79924697bbe6b2c1351cf2ac73f7eb41_27.png)

So， this is。The model。Now， this stuff like this has existed for a long time in these table answering things。

 But the way we want to do it here is end to end with a single deep learning model， of course。

 because we want to be better than anything else。 And the trend in deep learning is to。



![](img/79924697bbe6b2c1351cf2ac73f7eb41_29.png)

Put more and more into one model and to have it end to end differentiable。Alright， so you see。

 we need multiple components， right， We need some sort of a mode selector。

 We need some sort of a cell collector， and we need a thing that decides if we are in the compute mode。

 what computation to be done。

![](img/79924697bbe6b2c1351cf2ac73f7eb41_31.png)

Now， let me present the model that this paper proposes。So， this paper。Propos to。

Embbed the question here。 So you can see here， that's the question。Into a bird input。

 So this is a transformer right here。 This is Bt or any variant of birds that you can think of。



![](img/79924697bbe6b2c1351cf2ac73f7eb41_33.png)

🎼So the question is embedded as natural language。 And then interestingly enough， the table。

Right here。Is also embedded as language。

![](img/79924697bbe6b2c1351cf2ac73f7eb41_35.png)

🎼We'll get to that in a second。But the question and the table are in the input。

 and then the model is asked to do two things。 first of all。

 it's asked to do an aggregation prediction。

![](img/79924697bbe6b2c1351cf2ac73f7eb41_37.png)

![](img/79924697bbe6b2c1351cf2ac73f7eb41_38.png)

![](img/79924697bbe6b2c1351cf2ac73f7eb41_39.png)

🎼So this can either be one of these programs called count sum average， or it can be， as you can see。

 none。 So no aggregation。 So this handles our first two components。

 It can decide to perform a calculation or none。 And if it is performing a calculation。

 It can decide to do count a sum or an average。

![](img/79924697bbe6b2c1351cf2ac73f7eb41_41.png)

Now the， of course， the model here is not limited to those computations。

 You can think of extending this to any further computation。

 The important thing is that they have a number as an output。



![](img/79924697bbe6b2c1351cf2ac73f7eb41_43.png)

Second of all。There is a cell selector。 So depending on this aggregation prediction。

 you need some cells， like if you want to compute an average。

 you need the cells to compute an average over。 So the cell selector here will select cells from the table。



![](img/79924697bbe6b2c1351cf2ac73f7eb41_45.png)

IsSpecifically， it goes by row and column。 sorry， column and row。 Since these tables。

 usually they have a header， right， This is the table header where the attributes are listed。

 It makes sense to first in a first step。Select which column you want to select from。

And then if once you have a column， let's say this column here。In the second step。

You'd say which of the cells you want to select。 Now， these can be multiple。

 but the way the system is set up， it's first a column selector。

And then a cell selector within that column。 So you can only ever get columns from the same cell in this thing。



![](img/79924697bbe6b2c1351cf2ac73f7eb41_47.png)

Let's remember that for later。

![](img/79924697bbe6b2c1351cf2ac73f7eb41_49.png)

All right， so this is what the model does。 now let's look at the input。



![](img/79924697bbe6b2c1351cf2ac73f7eb41_51.png)

The input to the model is this here。 Now， this， if you refer from this before。

 this was in this blue box。 And then here you'd have the computation selection。

 and here you have the cell selection， right， So this is。



![](img/79924697bbe6b2c1351cf2ac73f7eb41_53.png)

![](img/79924697bbe6b2c1351cf2ac73f7eb41_54.png)

This is how you can relate that。

![](img/79924697bbe6b2c1351cf2ac73f7eb41_56.png)

So usually if you input something into a transformer， what you want to do is you want to embed。

This into2。Into a token embeddings。 So first， you want to split。

Everything you put in into what are called tokens。 Now。

 tokens are either things like words or word pieces。 The important thing is to you have a dictionary。



![](img/79924697bbe6b2c1351cf2ac73f7eb41_58.png)

![](img/79924697bbe6b2c1351cf2ac73f7eb41_59.png)