# 【阿尔托大学 - 中英】联邦学习 CS-E4740（Federated Learning，spring 2025） p29 P29 CS-E4740 Exercise 12-Mar-2025 -BV1cojRzDEfQ_p29-

， can you hear me， if you can hear me， please send me a message or okay， okay， thank you。O。😊。

Welcome to our better learning exercise session 3。In this exercise。

 you will be familiar with network X and be able to solve it。

 be able to use it to build a FMI station graph and also be able to solve the GTV minimization using closed form and be able to solve the GTV minimization using gradient method。

Okay。啊。

![](img/8441f595bf70ecc70e16a48042946edd_1.png)

Our first。Our first task is to build imp paragraph using the data here。 So the data。

 the data we use today is FMI data 2025。 The FMI means Finn Meteorological Institute。

 It means weather St。

![](img/8441f595bf70ecc70e16a48042946edd_3.png)

![](img/8441f595bf70ecc70e16a48042946edd_4.png)

![](img/8441f595bf70ecc70e16a48042946edd_5.png)

So， for example， this name is one weather station， and this is another weather station。

And we need to use all this data to build a graph。 So in the in each node of this graph corresponding to one station in this data。



![](img/8441f595bf70ecc70e16a48042946edd_7.png)

![](img/8441f595bf70ecc70e16a48042946edd_8.png)

For example， I draw an example here for example of this graph mean the sorry this node means this station and it contains it coordinates and some data。

 I will explain it later。And for the ages in graph， we choose four nearest neighbors for each node。

 For example， for this node， we choose four neighbors， for example 1，2，3，4 here。 and for this node。

 we also choose  four nearest neighbors， for example，1，2，3，4 here。



![](img/8441f595bf70ecc70e16a48042946edd_10.png)

So， after this。啊。We have the add H node here。 We have phone numberss and adds four lit neighbors to each node。

 After this， you will build a graph。Which contains。All these stations。And。This。

For narrativeist neighbors， S Hs。Any questions so far。Okay。



![](img/8441f595bf70ecc70e16a48042946edd_12.png)

And our next task is next question is how to deal with the data in each node。



![](img/8441f595bf70ecc70e16a48042946edd_14.png)

Will， briefly speaking。

![](img/8441f595bf70ecc70e16a48042946edd_16.png)

We use the team X and teaming as our features and the Y team X as our label。



![](img/8441f595bf70ecc70e16a48042946edd_18.png)

You can see from the code here。 we combine team X and teaming use as our eggs。

 which also means feature and。

![](img/8441f595bf70ecc70e16a48042946edd_20.png)

Here we use T Maxax as our label and after that we use contest speed to split the data set into trend sets and validation data sets also tested sets。

And after that， we need to add this trend set and validation data set and with you can assume that our initial width zero and coordinate the the coordinate means latitude and longitude for each station。



![](img/8441f595bf70ecc70e16a48042946edd_22.png)

![](img/8441f595bf70ecc70e16a48042946edd_23.png)

And we need to add this information。To our note。Which is built。Here。Any questions so far。Hey。😊，啊。

Then， our next task。We learned from the last lecture that we learned from the last lecture。

 the GTV minimization， which looks like this。And if we use linear regression and MSE loss。

 which looks like this， then we can solve this CTTV minimization using closed form。



![](img/8441f595bf70ecc70e16a48042946edd_25.png)

Which is introduced in our federal learning book section 3。4。1。



![](img/8441f595bf70ecc70e16a48042946edd_27.png)

How we do that？First。In each node， the upper index I here means node I。 So in each node。

 we calculate this capital Q using this equation。 and the MI I here means how many data in each node。

 In our case， iss always。

![](img/8441f595bf70ecc70e16a48042946edd_29.png)

It's always 10， I feel because in each that data set， we have 10 rows。 Oh sorry，8。

 because we also did the train test dispute。 So it should be 8。



![](img/8441f595bf70ecc70e16a48042946edd_31.png)

In our data， I feel it's always will it were checking the code。Okay， and。Okay for each node。

 we calculate this capital Q I here and the lowercase Q I here。And after that。

 we stack the after this Q I and plus some lu matrix and also stack the lower Q I like this。

 And then the TV optimization can be right like this equation。Is。Same as this one。

So in this equation， we can solve it using close form like this。Assuming that Q is universal。

Any questions so far。

![](img/8441f595bf70ecc70e16a48042946edd_33.png)

Okay。Then first， you need to implement the capital QI and the lowercase QI。KQ I here。

 you need to implement。According to this equation and this lower Q I， according to this equation。

And after that。You need to stack the capital Q I and the lowercase Q I。



![](img/8441f595bf70ecc70e16a48042946edd_35.png)

I can hear。

![](img/8441f595bf70ecc70e16a48042946edd_37.png)

And here。And after that。You can calculate the optimal W。



![](img/8441f595bf70ecc70e16a48042946edd_39.png)

Or theGTV minimization using this也可以。Any questions so far？啊。So next。

 it's not always practical to solve a optimization problem using closed form in machine learning most time we use some iteration method。

 for example， the gradient method。

![](img/8441f595bf70ecc70e16a48042946edd_41.png)

In our book section 5。3， we introduced a 5。1， which is using。

The iteration method to solve our GTV minimization。And对。To do this first。

 you need to compute the local gradient like this。Oh。I can show you。

The ex5 point one here a few case。Okay。And the first week， and is it。see。Of the rule，5 point。请。

Is here。So。First， we need to。Computer， local gradient。Which looks like this。

 And then compute the graph penalty， which looks like this。So this is local gradient。

And this is fourth penalty。And。Then we add them together and use this gradient to update。



![](img/8441f595bf70ecc70e16a48042946edd_43.png)

Thank you。So your task is to implement this local gradient and。



![](img/8441f595bf70ecc70e16a48042946edd_45.png)

F penalty and update rule。Any questions？

![](img/8441f595bf70ecc70e16a48042946edd_47.png)

Well， that's basically all an。

![](img/8441f595bf70ecc70e16a48042946edd_49.png)

Need to introduce in this assignment。You can ask questions。Ask any question about this assignment。

 if it's not clear。O啊。Okay， one question is between closed form and greeting method。

 which is frequently used and why。Of course， that greeting method is most frequently used because the reason we can solve it in include form is。



![](img/8441f595bf70ecc70e16a48042946edd_51.png)

Is the assumption that we use linear regression and MSE loss。 You know， it's not always critical。

 We can solve some。 We can build some model based on some real data using linear regression。

Most time， we use some more complex models like neural neural network or something。 In that case。

 it's not really easy to solve this using closed form。 So we need to use ingredient based method。

And our next question， can I。O okay， of course。Well one question is。

 can you ask something not related to sumit， Okay， of course you can ask。啊。没钱。If for saying。

As the first question is。The deadline for the project。I am not sure about the deadline。

 but of the project。 I need to check it after this session。

 I will reply or you can send me a message while slack， and I can reply to you。

And is this project mandatory？嗯。And next is。嗯。S me some framework or library about deynchralized effort。

 Okay， these three questions。I suggest you ask them while slack so I can check the deadline。

 And if it's mandatory and some related topics， I need to check it later。

And we have a question that while we're trying to run the ad。Add a function。

AndGett an error with this。嗯。Like what kind of error。Sa you have an error in。I H in this。

It is fine right。In K neighbors Square。Yes， it's slide。In the first task。

 ask you will use the add ages function in。Here。The add ageged function have two parameters。

 The first is J， which is graph。We use this one。

![](img/8441f595bf70ecc70e16a48042946edd_53.png)

呃GFMI no ages。As。

![](img/8441f595bf70ecc70e16a48042946edd_55.png)

As this G here。 And for neighbors， you can set it for or just use the default as for it works。

And I need to know what errors you get to answer a question。O， okay， I see the error嗯。

It looks like something wrong with coordinate。😔，嗯，可行。ISorry。

 I I will check this error later and now I answer another question is their question that that it's okay to create extra sale in notebook。

I feel you， of course， you can create extra sales to check your output and something else。

 but I'm not sure if it will disrupt the checking procedure。

My suggestion is you can create your checkill and delete it before submission。

And the next question is， can we can， can you please explain this code。This deep play function， okay。

嗯。O呃 one question about this deep， deep copy function。嗯。

This deep co function here is try to avoid directly modify this graph G here。 In this case。

 it's okay。 I feel if we modify G because we this G。

 we pass it to this add ages is our no edges graph。 And we need to add ages to this graph anyway。

 So I feel in this case is okay to modify this G。 And why we do this here is because we want to keep the original version of this no edges graph。



![](img/8441f595bf70ecc70e16a48042946edd_57.png)

![](img/8441f595bf70ecc70e16a48042946edd_58.png)

![](img/8441f595bf70ecc70e16a48042946edd_59.png)

And。For， for backup， I feel。But in next。But in， but in next deep copy here。For example， in this。

A gradient method。 We use this deep copy here， because in this gradient function。

 we will change the widths in each node。And we want to keep its original width。

 like the original width。 we can assume ass all。 the original width is 0。 And we， we only keep this。

 we only change this copy version of this graph so we can train it again， using our original graph。



![](img/8441f595bf70ecc70e16a48042946edd_61.png)