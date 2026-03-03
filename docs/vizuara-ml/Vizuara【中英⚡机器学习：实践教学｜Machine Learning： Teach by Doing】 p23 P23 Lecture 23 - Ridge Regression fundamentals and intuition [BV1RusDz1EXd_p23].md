# Vizuara【中英⚡机器学习：实践教学｜Machine Learning： Teach by Doing】 p23 P23 Lecture 23 - Ridge Regression fundamentals and intuition [BV1RusDz1EXd_p23]

Hello， my name is Dr。 Raj Daneer and today we are going to learn about re regression。

In the previous lecture， we looked at ordinarily squares method。

 but we did not add a regularization term to it。Today， we are going to see。

What does it mean to add a regularization term to the ordinarily square solution？

And more importantly， how does it solve。

![](img/5cccb9092fda923f11e705691012059a_1.png)

Two main problems which are encountered in the regression without regularization。



![](img/5cccb9092fda923f11e705691012059a_3.png)

Towards the end， we will also see why is it called as Ri regression？



![](img/5cccb9092fda923f11e705691012059a_5.png)

This is rarely explained in many courses， but in fact。

 there is a very nice and a beautiful visualization to this name。



![](img/5cccb9092fda923f11e705691012059a_7.png)

And there is a very strong reason as to why this name exists in the first place。

 so we will also take a look at that towards the end。



![](img/5cccb9092fda923f11e705691012059a_9.png)

So， let' us get started first of all I would like to have a small recap of the theta optimal or the theta star which we obtained in the regression without regularization and it was given by this particular formula。



![](img/5cccb9092fda923f11e705691012059a_11.png)

![](img/5cccb9092fda923f11e705691012059a_12.png)

![](img/5cccb9092fda923f11e705691012059a_13.png)

![](img/5cccb9092fda923f11e705691012059a_14.png)

If you have not seen the regression， the OLS lecture which was done in the previous class。

 I would highly encourage you to go through that。

![](img/5cccb9092fda923f11e705691012059a_16.png)

Because then understanding this particular lecture will be so much more easier。So here。

 as I noted before， we did not do regularization。

![](img/5cccb9092fda923f11e705691012059a_18.png)

So I mentioned about solving these two problems right， the first problem is going to be。



![](img/5cccb9092fda923f11e705691012059a_20.png)

What if。The universeverse of。W transferpose W does not exist。What will we do in this case。

 this formula。Is completely based on taking this inverse， right。

But what if the inverse does not exist in the first place？How do we proceed。

 then that' is the first major problem。

![](img/5cccb9092fda923f11e705691012059a_22.png)

And the second major problem is， of course。Overfitting。



![](img/5cccb9092fda923f11e705691012059a_24.png)

And both of these problems will be solved if we use regularization。

 especially re regression so essentially we are kind of killing two birds with the same stone it is a beautiful solution to both of these problems so lets start looking at rigid regression in the first place。



![](img/5cccb9092fda923f11e705691012059a_26.png)

![](img/5cccb9092fda923f11e705691012059a_27.png)

![](img/5cccb9092fda923f11e705691012059a_28.png)

It's actually very similar to regression which is regularization which we saw in classification。



![](img/5cccb9092fda923f11e705691012059a_30.png)

so。Re regulation。

![](img/5cccb9092fda923f11e705691012059a_32.png)

Simply looks like this。So the objective function I'm going to call as J Rige。

It will again depend on theta and theta not。So you can think of this as the slope。

And you can think of this as the offset。And the objective term will be equal to the average of。

This is I。The average of the square loss function。

![](img/5cccb9092fda923f11e705691012059a_34.png)

And Im now going to add one more term here。In fact， this is the regularization term。

This is the regularization term， it is exactly similar to the term which we added for classification。

 if you recall。

![](img/5cccb9092fda923f11e705691012059a_36.png)

![](img/5cccb9092fda923f11e705691012059a_37.png)

Where Lada is a hyperparameter， and it's a constant。And in the vector form。

 this is magnitude of theta whole square which can also be written in vector form as theta transpose into theta。



![](img/5cccb9092fda923f11e705691012059a_39.png)

Now one small distinction which I would like to point out here is that when we add the regularization term。

 we are not including the offset here in particular what this means is that。



![](img/5cccb9092fda923f11e705691012059a_41.png)

![](img/5cccb9092fda923f11e705691012059a_42.png)

As we also saw in classification， this regularization term adding it means that we want to keep the magnitude of theta smaller。



![](img/5cccb9092fda923f11e705691012059a_44.png)

So in particular， we are penalizing the slope if its too large。

So theta is the slope and remember theta not is the offset， so let's say if these are my data points。



![](img/5cccb9092fda923f11e705691012059a_46.png)

![](img/5cccb9092fda923f11e705691012059a_47.png)

![](img/5cccb9092fda923f11e705691012059a_48.png)

And I want to find the regression line among these data points， lets say。



![](img/5cccb9092fda923f11e705691012059a_50.png)

This is the first version of the line now if I take a line with a higher slope。

 lets say which looks something like this。ARe regression will penalize this。

 so this will be penalized。

![](img/5cccb9092fda923f11e705691012059a_52.png)

And by penalized I mean that if the slope is higher， this quantity will also be higher。

 which means the loss function or the objective function will be higher， so which we don't want。

 we want this j or the objective function to be as low as possible。

 which implies that we want the theta or the slope to be as close to horizontal as possible。



![](img/5cccb9092fda923f11e705691012059a_54.png)

![](img/5cccb9092fda923f11e705691012059a_55.png)

![](img/5cccb9092fda923f11e705691012059a_56.png)

![](img/5cccb9092fda923f11e705691012059a_57.png)

And there is a reason why we do that we saw that reason in the classification case also the reason why we want the slope or the parameters to be small in magnitude is that we don' not want our final answer to capture the noise。



![](img/5cccb9092fda923f11e705691012059a_59.png)

![](img/5cccb9092fda923f11e705691012059a_60.png)

![](img/5cccb9092fda923f11e705691012059a_61.png)

If there is noise in the data， we don't want to capture that and having smaller parameters or having smaller slope ensures that the noise is not captured a general rule to remember is that。



![](img/5cccb9092fda923f11e705691012059a_63.png)

If the parameter values are too high， it means that our hypothesis has started to behave like crazy and it is starting to capture noise so we should be careful in such a scenario reach regression or regularization allows us or prevents theta from becoming too high in magnitude and keeps this slope low。



![](img/5cccb9092fda923f11e705691012059a_65.png)

The second thing what we are saying is that let us say if this was the original line right。

 this this line， this was the original line and I told you that if it is rotated we will penalize it but essentially what we are saying is that if I had an offset to this line。

 which means that if I keep the slope of this line same but I change the theta not。



![](img/5cccb9092fda923f11e705691012059a_67.png)

So let' us say consider the blue line which Im calling O and consider L1 and L2。



![](img/5cccb9092fda923f11e705691012059a_69.png)

So O， line O， line 11 and line l 2 have the same same slope， so have the same theta。

 but they have different theta node。

![](img/5cccb9092fda923f11e705691012059a_71.png)

We are not going to penalize that it is totally fine for us how much our offset is there we don't want to penalize the offset。



![](img/5cccb9092fda923f11e705691012059a_73.png)

In the region regression。What is only penalized is the slope。

The offset actually does not matter too much because whether we increase or decrease the offset it does not mean we are capturing the noise or not capturing the noise What is more important is to penalize the slope。



![](img/5cccb9092fda923f11e705691012059a_75.png)

![](img/5cccb9092fda923f11e705691012059a_76.png)

So one small distinction which I would like to note here and this may be asked in interviews because it is a minor point that in the rigid regression。



![](img/5cccb9092fda923f11e705691012059a_78.png)

We penalize the slope。And not the offset。If we are penalizing the offset。

 then there would have been one more term or Lada into theta node square or something like that。



![](img/5cccb9092fda923f11e705691012059a_80.png)

![](img/5cccb9092fda923f11e705691012059a_81.png)

But we don't add that because it' is fine to have the offset we are just going to penalize an increase in slope。



![](img/5cccb9092fda923f11e705691012059a_83.png)

In the lecture on classification， we saw the physical meaning or the intuition behind this regularization term。

 It really helps us to keep the。

![](img/5cccb9092fda923f11e705691012059a_85.png)

magnitude of theta small and today we are going to see a handson example of how this works in practice and how it prevents overfitting。

 how it prevents us from capturing the noise in the training data also。



![](img/5cccb9092fda923f11e705691012059a_87.png)

![](img/5cccb9092fda923f11e705691012059a_88.png)

Before coming to that， I just want to write the mathematical origin of this so we looked at last time minimizing。



![](img/5cccb9092fda923f11e705691012059a_90.png)

![](img/5cccb9092fda923f11e705691012059a_91.png)

Minimizing J of theta。Without the rigid regression gave us this particular formula for gradient of J。

Gradient of J was 2 by n。W transpose， W theta minus P。



![](img/5cccb9092fda923f11e705691012059a_93.png)

Now if you take the gradient of this just one more term would be added you already must have guessed that and if you take so it would be an added derivative so if you take the derivative of this it will be two Lada theta。



![](img/5cccb9092fda923f11e705691012059a_95.png)

![](img/5cccb9092fda923f11e705691012059a_96.png)

![](img/5cccb9092fda923f11e705691012059a_97.png)

So gradient of J Ridge。Which is the。Re regression， objective function is。

The first term is actually exactly similar because it does not change this squared loss。



![](img/5cccb9092fda923f11e705691012059a_99.png)

![](img/5cccb9092fda923f11e705691012059a_100.png)

W theta minus t， but we add another term which is2 lambda theta remember that the dimensions of everything here are d by 1 and D by 1。



![](img/5cccb9092fda923f11e705691012059a_102.png)

So， for the sake of simplicity here I am not considering theta not because optimizing J reach with theta n turns out to be difficult and I want to present to you with a simple formula here so I am just looking at theta right now for the sake of simplicity。



![](img/5cccb9092fda923f11e705691012059a_104.png)

![](img/5cccb9092fda923f11e705691012059a_105.png)

![](img/5cccb9092fda923f11e705691012059a_106.png)

![](img/5cccb9092fda923f11e705691012059a_107.png)

We also saw that。Theた start。

![](img/5cccb9092fda923f11e705691012059a_109.png)

In the normal case， without age regression is。W transpose W inverse， W transpose T。



![](img/5cccb9092fda923f11e705691012059a_111.png)

It turns out that。