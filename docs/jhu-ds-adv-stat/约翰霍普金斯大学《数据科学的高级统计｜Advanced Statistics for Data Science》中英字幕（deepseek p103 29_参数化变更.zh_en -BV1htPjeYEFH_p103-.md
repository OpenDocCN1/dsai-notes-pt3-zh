# 约翰霍普金斯大学《数据科学的高级统计｜Advanced Statistics for Data Science》中英字幕（deepseek p103 29_参数化变更.zh_en -BV1htPjeYEFH_p103-

Now， remember last time we were considering a setting where we wanted to do y minus。

 let's say x1 beta。

![](img/02875b473bdc40d42440510b1cd9cde0_1.png)

And minimize that where x was， let's say J。And one。And then a bunch of zeros。



![](img/02875b473bdc40d42440510b1cd9cde0_3.png)

And then a bunch of zeros。N J， N2。Where J is again， a vector of one。Let's say x1 is like that。

 and we found that we have two groups of data and we found out that our estimates then works out our beta。



![](img/02875b473bdc40d42440510b1cd9cde0_5.png)

Hat works out to be Y1 bar。 Y2 bar。

![](img/02875b473bdc40d42440510b1cd9cde0_7.png)

Where again， our beta is equal in this case， to beta 1 and beta 2。



![](img/02875b473bdc40d42440510b1cd9cde0_9.png)

![](img/02875b473bdc40d42440510b1cd9cde0_10.png)

Now， consider。Y minus x 2 gamma。

![](img/02875b473bdc40d42440510b1cd9cde0_12.png)

Consider minimizing the model where x1 is equal to a vector J n1 plus n2。

 and then a vector that's JN1。

![](img/02875b473bdc40d42440510b1cd9cde0_14.png)

![](img/02875b473bdc40d42440510b1cd9cde0_15.png)

And then a bunch of zeros。 Let me just write it as 0 and 2。Meaning a vector of zeros of length and 2。



![](img/02875b473bdc40d42440510b1cd9cde0_17.png)

Now， so this is the0 and2。

![](img/02875b473bdc40d42440510b1cd9cde0_19.png)

![](img/02875b473bdc40d42440510b1cd9cde0_20.png)

And this is0 and1。So。

![](img/02875b473bdc40d42440510b1cd9cde0_22.png)

The and this is x2。 I'm sorry。 and then gamma is equal to gamma 1。



![](img/02875b473bdc40d42440510b1cd9cde0_24.png)

Yeah。Now notice if I add these two columns。

![](img/02875b473bdc40d42440510b1cd9cde0_26.png)

Right。I get this column right here。

![](img/02875b473bdc40d42440510b1cd9cde0_28.png)

And similarly， if I take this column and I subtract this one。



![](img/02875b473bdc40d42440510b1cd9cde0_30.png)

Then I get the second column here， so what we see is that x1 and x2 contain the same column space。



![](img/02875b473bdc40d42440510b1cd9cde0_32.png)

![](img/02875b473bdc40d42440510b1cd9cde0_33.png)

They have an identical column space， and what we know from a projection argument is that the fitted values from both the models have to be the same。



![](img/02875b473bdc40d42440510b1cd9cde0_35.png)

With the fit of values from Model1。

![](img/02875b473bdc40d42440510b1cd9cde0_37.png)

If for any observation in group1， the fit of value is going to be y1 bar。



![](img/02875b473bdc40d42440510b1cd9cde0_39.png)

And for any observation in group2 is going to be y2 bar。

 so we know that beta 1 hat equals y1 bar and beta 2 hat equals y2 bar we know that because we worked it out in the last example where we figured it out。



![](img/02875b473bdc40d42440510b1cd9cde0_41.png)

![](img/02875b473bdc40d42440510b1cd9cde0_42.png)

![](img/02875b473bdc40d42440510b1cd9cde0_43.png)

Okay。Now， look at x2 times gamma。

![](img/02875b473bdc40d42440510b1cd9cde0_45.png)

Well， the fitted values。

![](img/02875b473bdc40d42440510b1cd9cde0_47.png)

For anyone in group one。Are now， if I multiply x2 times gamma。

 it's going to be gamma1 hat plus gamma 2 hat。 And then for anyone in group 2， it's got to just be。



![](img/02875b473bdc40d42440510b1cd9cde0_49.png)

![](img/02875b473bdc40d42440510b1cd9cde0_50.png)

![](img/02875b473bdc40d42440510b1cd9cde0_51.png)

Gamma， one hat。By itself。

![](img/02875b473bdc40d42440510b1cd9cde0_53.png)

So we know that the fitted values have to satisfy these equations。



![](img/02875b473bdc40d42440510b1cd9cde0_55.png)

![](img/02875b473bdc40d42440510b1cd9cde0_56.png)

And they have to agree because the column space of the two is the same。

 So what we know then is that beta 1 hat， which is y1 bar。

 has to equal to gamma 1 hat plus gamma 2 hat and beta 2 hat， which is equal to y2 bar。

 has to equal to gamma 1 hat。 We can use that to now solve for。



![](img/02875b473bdc40d42440510b1cd9cde0_58.png)

![](img/02875b473bdc40d42440510b1cd9cde0_59.png)

![](img/02875b473bdc40d42440510b1cd9cde0_60.png)

![](img/02875b473bdc40d42440510b1cd9cde0_61.png)

Gamma one hat and gamma2 hat without actually having to go through the trouble of inverting this matrix now it's a two by two matrix so it shouldn't be that hard to invert。

 but let's suppose you had a little bit harder of a setting then it would be a little bit harder to invert let's suppose we just had 10 columns。



![](img/02875b473bdc40d42440510b1cd9cde0_63.png)

![](img/02875b473bdc40d42440510b1cd9cde0_64.png)

![](img/02875b473bdc40d42440510b1cd9cde0_65.png)

![](img/02875b473bdc40d42440510b1cd9cde0_66.png)

this is kind of a common trick in these anova type examples where you can reparameterize to the easy case where you get a bunch of block diagonal one vectors like in the case of x1 in which case x transpose x works out to be a diagonal matrix and then very easy to invert and that if you want any different reparameterization which would result in an x transpose x that's hard to invert。

 you can use the fact that you know that the fitted of values have to be identical to convert between the parameters after the fact so in this case。

 you know you know you know that gamma1 hat has to be equal to beta 2 hat and then you know that gamma2 hat。

 then just plugging in with those two equations has to be equal to beta 1 hat minus beta 2 hat。



![](img/02875b473bdc40d42440510b1cd9cde0_68.png)

![](img/02875b473bdc40d42440510b1cd9cde0_69.png)

![](img/02875b473bdc40d42440510b1cd9cde0_70.png)

![](img/02875b473bdc40d42440510b1cd9cde0_71.png)

![](img/02875b473bdc40d42440510b1cd9cde0_72.png)

![](img/02875b473bdc40d42440510b1cd9cde0_73.png)

![](img/02875b473bdc40d42440510b1cd9cde0_74.png)

![](img/02875b473bdc40d42440510b1cd9cde0_75.png)

![](img/02875b473bdc40d42440510b1cd9cde0_76.png)

![](img/02875b473bdc40d42440510b1cd9cde0_77.png)

Okay。And so that gives you a very quick way to go between parameters in equivalent linear models with different specifications。

 with just different row organization。

![](img/02875b473bdc40d42440510b1cd9cde0_79.png)

![](img/02875b473bdc40d42440510b1cd9cde0_80.png)

![](img/02875b473bdc40d42440510b1cd9cde0_81.png)

Okay， so it's a useful trick when you're trying to work with these Anovava type models。



![](img/02875b473bdc40d42440510b1cd9cde0_83.png)