# 【阿尔托大学 - 中英】联邦学习 CS-E4740（Federated Learning，spring 2025） p31 P31 CS-E4740 Exercise 19-Mar-2025 -BV1cojRzDEfQ_p31-

Thanks you。And welcome to our exercise session for federal Learn As for。In this assignment。

 you will know the basic idea of decision entry and be able to implement the F network using allmetric local models。

 for example， the decision entry。

![](img/ebf582d2486e600c840231748bdb5454_1.png)

First is data set。 We use the same data set as we use in a sum 3。 So we so we use the F data225。

 and it includes some stations and names and coordinate and its temperature data。



![](img/ebf582d2486e600c840231748bdb5454_3.png)

![](img/ebf582d2486e600c840231748bdb5454_4.png)

![](img/ebf582d2486e600c840231748bdb5454_5.png)

And we also use the same method to build FMI network。哎。Okay， so。Next， we introduce FD relaxed。



![](img/ebf582d2486e600c840231748bdb5454_7.png)

NowIn assignment3， we learned about the linear model。

But we know that sometimes linear model is not really convincing。 So we reduce this feather relaxed。



![](img/ebf582d2486e600c840231748bdb5454_9.png)

The basically idea of federal relaxed is。We assume that for each node I is neighborhood。

Already have optimal weights。

![](img/ebf582d2486e600c840231748bdb5454_11.png)

So as we see here in each node I， we assume that its neighbor already have its optimal with So it' fixed so we can update。

Each neighbor using this equation， because this W hat a prime is its neighbor and will assume my s。

And this AII prime here is adjacent matrix， and the alpha is a hyperfimeter so we can solve this equation relatively easily。

Any questions so far？Okay， so next come with the no parametermetric models。So still。

 we look back to our GTV minimization。

![](img/ebf582d2486e600c840231748bdb5454_13.png)

The idea of GTV minimization or the idea of better learning is if two data sets or two individuals or two node。

 if they are closely related， then they will have similar models。



![](img/ebf582d2486e600c840231748bdb5454_15.png)

But how can we say two models are similar， How can we measure their discreancy。Well。

 in the G minimization， we use this probability。 We calculate the Euclidean distance between their widths or parameters。

 But what if we don't have parameters。嗯。Recad it a function in a computer view is something that。

 for example， this is a function。 A function in computer is something that takes an input。

And give some output。If we can select all this input and all this output。

Then we can define this function， right。So if two functions， they are similar。

 then given the same input， they should also have the similar output。And based on this idea。

 we introduce this federate relaxationism with agnostic model。This D here means the。

 the discrepancy between model H I and H I frame。And we rifleed this equation。

So riseD as loss function， we have。It is career here。で l。嗯。With X and H。Yess。Is a loss function。哦。

Each I。W。Data set X and H。Where the X is feature。As we。Use。And this， this H is prediction。From。

His neighbors。对。So with each this data set。 and we use this data set。On each prime。

 its a measure the distance between。HI and H prime。



![](img/ebf582d2486e600c840231748bdb5454_17.png)

呃。Our next task is we take thisry， for example， because we cannot get the parameter from thisentry。



![](img/ebf582d2486e600c840231748bdb5454_19.png)

So if I see in this picture， verse three build some public data sets。

This publication data set corresponding to this set here。

And it's any board means it only have a feature。So。In Note  I， we use this public data set。

As feature， how about libo， the labelo is prediction from his neighborhood knows we use the prediction from his neighbor as libo。

And this is。The new data or no eye。And we combine this， this new data with this original data。

 We have this augmented data set。And we use these augment dataset sets to turn node I。

And because we also have something， some information from his neighbor， which is legal here。

 So in this way， we can compare the。

![](img/ebf582d2486e600c840231748bdb5454_21.png)

Model for La and live pride。Any question here？Good。We a task。First， you need to。



![](img/ebf582d2486e600c840231748bdb5454_23.png)

First， you need to initialize the model for each node， which is a dis entry model。And then。

You need to build this。Augmented a data set， use X public we here。

And then you need to use as local and as public。Combine them together。As augmented as。

Then use this augmented dataset to train。一も通り一度。Any questions？Okay。

 we have a question here for the public data set。

![](img/ebf582d2486e600c840231748bdb5454_25.png)

然这嗯。First the idea who compare to compare to a agnostic model is because we don't have their parameters。

 so we cannot compare their parameters to different models。

 then how can we compare these two models without knowing their parameters， We can only use data。

Because this is federal learning。 we need to care about privacy so we cannot share our data directly。



![](img/ebf582d2486e600c840231748bdb5454_27.png)

So， we build some。APublic data。In this code。We build public data。

 according to highest temperature and lowest temperature from our hotel data set。



![](img/ebf582d2486e600c840231748bdb5454_29.png)

We only use high test temperature and low temperature。

 so this data set will not leak privacy for each node， right。

 so this public data is safe for each node。

![](img/ebf582d2486e600c840231748bdb5454_31.png)

And using this public data。We train on each node， for example， we train this public data on node I。

 Then we get some label from sorry， if we train this public data or node I prime。

 then we get some label from I prime。 Then we have the hotel with feature and label。

And we use its other data and label from node Iframem。to唇 no爱。

Then we can compare the excimacy between tie and the low life project。

Our next question in better relax， We are assuming that all those have update。No updating the wayss。



![](img/ebf582d2486e600c840231748bdb5454_33.png)

是。In very relaxed。あの部屋。In F relax， in each iteration of each node。

 we assume that its neighbor have faced width。 we should here。 the head here means it's optimal。

 We assume it's optimal， but it's not necessary optimal， but for node I。

 we assume that its neighbor have optimal width， so we can face it。

 Then we only need to care about the node for the weight for node I。



![](img/ebf582d2486e600c840231748bdb5454_35.png)

Then it's it's idea of Jacob。 If you know it's from Union is that we fix other parameters and we can and。

By this way， we can only update this WI here。

![](img/ebf582d2486e600c840231748bdb5454_37.png)

Did I make here。Okay， thank you。Okay， and that question is。Our next question is。

 what we are augmenting in no perfect model， okay。

![](img/ebf582d2486e600c840231748bdb5454_39.png)

What we are augmenting， We are augmenting data。Because we use public data and label from neighbors who build new data。

And we added this new data set to our original data set。

 So this original and the public data set is augmented data set。So it's like a data orientation。

 but using a label from neighbors。Any more questions？The media is span and whole。

How we use this augmented data sets and how do we compare to a diagnostic model。ok for嗯 if we。

Think the model is a function。It's a function。

![](img/ebf582d2486e600c840231748bdb5454_41.png)

How can we compare two functions in TTV minimization if these functions have same structures and we know their parameters。

 for example， if it's a linear model， and we know its sweets and biass。

 then we can directly compare the parameters， that's the discreancy between two models。

But what if our model is agnostic means we don't know his parameter。



![](img/ebf582d2486e600c840231748bdb5454_43.png)

Then if we takes the function as。Some input to output。It's some it's two functions。

 here are similar then given the steam input。To different functions。Then their output。



![](img/ebf582d2486e600c840231748bdb5454_45.png)

Should there also be similar rights？Then we can。Measure the discreimancy between two functions by their output。

So a difference between。Output of function X and output of function key。And this is。せ。Dcrency。

It's on。一。And they act here because we cannot directly share our data with our neighbors。

 So we need to build some public data。对。In notice this as public。And she is here in this image。

And using this X public， using this public data。For each note。Ae。And no dark crime。For example。

 this is F。I exist， I pray。With seeing exp detail。And it's output。啊。I see why pray and then this。Oh有。

AFs。Let's see why。And we compare。So discriminancy between the why and the white part。And how can we。

How can we compare the discancy between white and the white frame？So why is sleepal？

Right it's simple for our data sets。Or for example， Arthur there is legal。そう。I5 a sense。小声。Oh， nice。

And the what from。诶 stable啊。哦。Oublic data， public data。要先。Yes， right。



![](img/ebf582d2486e600c840231748bdb5454_47.png)

So if we turn X public。And why？Oh， that correct。And we train next public。



![](img/ebf582d2486e600c840231748bdb5454_49.png)

My friend。Oh。And嗯。If prime， the loss function will be。ロ。不是。Spak。And the why。Right。

 because this label crpher near this label， and this is the prediction of aph。

And also seeing for yes。The last function is。It's public。And。This is label for S。Yeah了。Right。

And if you'll know the LP home。说方学习。Book sizes。Okay。

This is the same idea as re used using this augmented data。That's because it's T here。嗯We integrate。

This discreimacy。In the dorm地。And the domain we used in our model is this X public dataset。有我开始。

Why we are doing no primary look model。嗯。Because we want to generalize this CTV minimization。



![](img/ebf582d2486e600c840231748bdb5454_51.png)

You see that's in this。In this category miniization we。Assume that we have this W here。

 which is weight or parameter for model。 but some model it。

We don't have access to the parametermeter。 for example， this entry here we。

Usually don't have access to the parameter for this century。

 but we still want to do the federal learning。 So we need to compare two models。

 But if we don't have these parameters and how can we compare these two models， yes。

That's why we use this model wetic federal learning so the reason is because not all models have the parametric that we can compare using this method。



![](img/ebf582d2486e600c840231748bdb5454_53.png)

![](img/ebf582d2486e600c840231748bdb5454_54.png)

Another example is if， if two node for example this node and this node。

 they use different models for example this node using linear regression and this model using some neural network。

 then we。

![](img/ebf582d2486e600c840231748bdb5454_56.png)

![](img/ebf582d2486e600c840231748bdb5454_57.png)

Cannot compare there with using this Eukradal。Okay， next question。

All model does not have same parameters for the region yes。

 one reason is if we know their parameters， but different model have different structure。

 then we cannot compare their parameters using this euclian node and if for some reason we don't know their parameters。

 then we can only compare them using data， which is a method we introduce here。

 we use some augmented data using this augmented data to compare models。



![](img/ebf582d2486e600c840231748bdb5454_59.png)

![](img/ebf582d2486e600c840231748bdb5454_60.png)

![](img/ebf582d2486e600c840231748bdb5454_61.png)

![](img/ebf582d2486e600c840231748bdb5454_62.png)

Yeah。ok， we have a question。And how do I receive neighbors from？He next。Yes， yes。

 you can use wait There must some function from network X that you can acquire。

Every neighbors for every note。 I don't remember it exactly， but。



![](img/ebf582d2486e600c840231748bdb5454_64.png)

There must be a function and directly gets the neighbors load。嗯。By the way， speaking of discancy。

 do you know how to compare some like other mathematic objects？For example。诶。For example。

 how do we compare to vectors？We can use both products。And how to compare to strings。You can use。

Ham in distance。Or headed distance。How do we compare to proities？One method is using care damages。

And how can we compare horizontalal matrixes？You can use host， host of distance。And for functions。

It was healthy。I feel the discacy or this decline objects。



![](img/ebf582d2486e600c840231748bdb5454_66.png)

![](img/ebf582d2486e600c840231748bdb5454_67.png)

It's a really fundamental concept in machine learning。 for example， if we take this， for example。

 so compare vectors， we use dot product and this is a methods used in attention attention mechanism if you read this paper and know about attention and transformer。

 how do we know which context we should pay attention to if we live in a vector space。

 then can compare their dot product。

![](img/ebf582d2486e600c840231748bdb5454_69.png)

![](img/ebf582d2486e600c840231748bdb5454_70.png)

And for example， this one。If we use probability machine learning。

 if we assume our model is some kind of distribution。人嗯。Using prior and likelihood wood。

 for some reason， we don't want our distribution too wild。

 We don't want our distribution goes too far from our prayer so we can use care divergence to constrain our model to constrain our。



![](img/ebf582d2486e600c840231748bdb5454_72.png)

![](img/ebf582d2486e600c840231748bdb5454_73.png)

searcharch space or distribution。We have a question here。The question is。

 sometimes the local data set have eight values and sometimes have 10。



![](img/ebf582d2486e600c840231748bdb5454_75.png)

Of。In。Data set。

![](img/ebf582d2486e600c840231748bdb5454_77.png)

Insteadter set， you can see that each local always have 10 raw data and。



![](img/ebf582d2486e600c840231748bdb5454_79.png)

If we。L this contest test speed here。诶系系。

![](img/ebf582d2486e600c840231748bdb5454_81.png)

It's。Here， if we use this train test suite using test sizes open to。

 then we have eight train data set and two test data set， That's why we have it。

 but the whole data set is always ten0 for each node。



![](img/ebf582d2486e600c840231748bdb5454_83.png)

![](img/ebf582d2486e600c840231748bdb5454_84.png)

For those if you aren really familiar with Jacobin algorithm。



![](img/ebf582d2486e600c840231748bdb5454_86.png)

哦诶 organizationization。この。Imagine we have an optimization of the problem and it has many。

 many parameters for example W1，W2， W3。So大分。We have many。

 many unknown parameterss for this optimization problem。So for some reason。

 we cannot update all these parameters simultaneously。

 It might be too too much competition or simply not or simply impossible sometimestime。

 Then how can we do that。父心学燕。Thatumber3。We update。One parameterur。By fixing other parameters。 Or。

 if we want to update W 3， then we。Fixix other parameters。

And we can only update one parameter and it become relatively easy。And after some iteration。

For example， this laboratory get is optimal solution。人。So we can update other transcripts。

 for example。呃，W one here。When we update everyone， we also assume that。Other。Fmeterters are fixed。

 Then we can only update W1。Until it。That is optimal。Here有。



![](img/ebf582d2486e600c840231748bdb5454_88.png)

And that's how we use Zealand is federalized。So update update our parameter in each node。



![](img/ebf582d2486e600c840231748bdb5454_90.png)