# 【全集-附课程讲义】密歇根大学-人工智能编程-EECS492-中英字幕-p27-Lecture-27---多项式的零点—牛顿法与霍纳法--BV14JqfBNEAS_p27-

Section 3。6，0 sub polynomials。A polynomial of degree N has the form， as in this equation。Here。

 AIs are called the cors of the polynomial P。And A M， the leading patient is Nan X。Interse。

The objective is to find the zeros sub the polynomial P。Let's begin with some theory on polynomials。



![](img/c2a606883855ccf2f2672c362094855d_1.png)

Fundamental theorem of algebra such that every non constant polynomial has at least one root。

Possibly in the complex field。Here each root will make a linear factor in the polynomial。So that。

We can refresh this statement。As follows， every non constant polynomial has at the least one linear vector。

For example。코드라틱풀리노으면。Has at least one linear factor。But the other part must be， again。

 linearar factor。And so that quat polynoomers will have two linear vector。Now for cubic polynomials。

They have at least least one linearar factor。And。The other part question must be。

Quadrara and quadrara。Can be expressed as a product of two line factors。So， that。啊，里边处理。

The polynomials of the good N can be expressed as a product of n linear vectors。

Here this is coss of the theorem。A polynomial of N has deed n roots in the complex plane when we count the roots with multiplicity。

That is， there are unique complex turnst， x1 to xk and unique integers， M to Mk， such that。

The polynomial of degreean can be expressed in this vein， the product of linear termss。

And the multiplicity M M2。 if we add them， then it must be N。So。A polynomial of N has exact n roots。

And the complex plan。

![](img/c2a606883855ccf2f2672c362094855d_3.png)

Localization of roots， all roots of the polynomial P lie in the open disk centered at the origin and of radius of wall。

That is one plus one of bone。Abs value of the leading equation times maximum of。Other。

The cor sense in mods。So once we try to get roots by using iterative algorithms。

 then we can initialize the roots inside this steerco so then we can get。Better convergenence。

Unicorness ofponomials。P and Q are two polynomials of Diguan。If。2 polynomals a。诶。

Excellent to Xr with R larger than n and this numbers。Then the two polynomials must be the same。

In particular， two polynoomerials of the N are the same if they agree at n plus1 points。

So values of m plus one distinguished points。We decide a polynomial of degree N uniquely。



![](img/c2a606883855ccf2f2672c362094855d_5.png)

![](img/c2a606883855ccf2f2672c362094855d_6.png)

Here we have the bonus method。Known as nasty multiplication， and also as。Stfer division。

 the horn method can evaluate polynomials very efficient to them。Let's try to evaluate P react。

And x equals x0。We will use the remainder theorem。The theodorem says here， pilbeage。



![](img/c2a606883855ccf2f2672c362094855d_8.png)

That POBx is this one。Okay。Per be is divided by x minus x0， then we have quoed and remained。

Al must be a constant， because divide the。Is a linear term， a linear function。

But all can be decided quite easilyly， when we。Pull out x0， then this will be 0 and R。

That means P at Xome is R， so we have here P at Xome。

Now we express cube x expressly as in this equation， P and x to the M minus1 plus and P to x plus P1。

We are product this here， and expand。And we have， yeah。The anth polynomial。

 and we have another one here， now we try to compare persons of equal power of x。



![](img/c2a606883855ccf2f2672c362094855d_10.png)

And then we can have here m plus one equations。This one came from。The courses of x to the N。

 and the next one came from。The coefficient sense of x to M-1， and so on。Now。We have。These questions。

 but the shas a bit different so that we try to make the shape。



![](img/c2a606883855ccf2f2672c362094855d_12.png)

Okay。Now， here， we try to add。X 0 and B M plus one with the PMm plus 1 and 0。

Then this whole thing can be expressed using that way。 Of course。

 we have the interprets over there another。嗯。Notation， there's a piece wrong。Then。

 this imp plus oneation。Can be leading in this rank。You Bk。Its 18。

Plus x 0 times B K plus one all the way。 same form。 So by using this liquidible formula。

We can get all B values。 And the last one， B0 will be the desired the value， P at X 0。

So we can implement this one， but we have to start with P n plus 1 equals s。And initialization。

 and use theulive formula。

![](img/c2a606883855ccf2f2672c362094855d_14.png)

Okay。Now。Here， if we try to use a table techcon。Then it is known as synthetictic division。

 I believe you learned this one from high school。Now here the quos are collected。And go down。

To become PM N， that is x 0。 And we multiply this to。And put here and add them。

 There is exactly this equation。 And multiply this through。Put here and add to them。And and so on。

Then and after the addition of this one， that will be p0， this is the last equation。

 which must be P at x0。

![](img/c2a606883855ccf2f2672c362094855d_16.png)

Let's see this example。Use the Homa algorithm to evaluate P at 3 where P of V X is given in this equation。



![](img/c2a606883855ccf2f2672c362094855d_18.png)

Now xv is a 3A， and so we put here 3 a now we collect the quos of the polynomial 1 minus4。

7 minus5 minus2。Now， this AN go down 2 pN。응 그냥 말투케 수술。And put here and add these two numbers。

To have -1， again， multiplication and addition。And now the multiplication 12 edition must be 7。

 and multiplication is 21。 Now addition becomes finally 19。Which is a P at 3。And here。

This one is at the course of ks。

![](img/c2a606883855ccf2f2672c362094855d_20.png)

No。😔，Now， B values are。

![](img/c2a606883855ccf2f2672c362094855d_22.png)

The coefficients of the Q X。 so that here this one。



![](img/c2a606883855ccf2f2672c362094855d_24.png)

呃。Is for。The Q x cubeator1 and then minus1， there's4 and7。So that。P of Vx can be read here。

 X3 and Q of Vx plus。P3， which is 19。对。Okay， now so that we know how to evaluate。

The polynomial value efficiently now。When we try to use Newton's method。For finding。

On a push0 of the polynomial。Then the etuition is happening in this vein。



![](img/c2a606883855ccf2f2672c362094855d_26.png)

Now， P at。嗯。The last point。And Ti buy the by P at。The same point， people Im at the same point。

 that was being。Here are subjecttracted from。At that last point。To get the updates the。

Point the it read。So that here we have to know how to get this value efficiently and what we know how to get it。

 now， we'll consider。

![](img/c2a606883855ccf2f2672c362094855d_28.png)

Now how to get at this value， de value。Okay。

![](img/c2a606883855ccf2f2672c362094855d_30.png)

Yeah。Now， for。

![](img/c2a606883855ccf2f2672c362094855d_32.png)

That dimension theorem， from this one， we differentiate it。Then this sort disappear and here。



![](img/c2a606883855ccf2f2672c362094855d_34.png)

We have now okay， bying product rule。We have a cure back and x minus taxixedone。Q primates。Now。

 what we have to do is evaluation of a P prime at ex。So once x is ex， then no matter what it is。

 this term will be zero so that it is the same as Q at x。

So the evaluation of a Q at x0 becomes the de at quantity P prime at x0。



![](img/c2a606883855ccf2f2672c362094855d_36.png)

That makes such a。Because it was twice a preca of a horn of the method them。



![](img/c2a606883855ccf2f2672c362094855d_38.png)

No。For the polynomial we considered earlier example， let's try to evaluate the P prime L3。



![](img/c2a606883855ccf2f2672c362094855d_40.png)

Then only we know that this portion。And。From the descriptions of polynomial at 3。

We do hear the bonusness algorithm to get P at 3。Now that's QVx。



![](img/c2a606883855ccf2f2672c362094855d_42.png)

Yeah。By evaluating a Q at X， we can find。The de P at oxygen that means that for Q again。

 we have to evaluate the value at 3。

![](img/c2a606883855ccf2f2672c362094855d_44.png)

So we apply one more time the whole method。 So the questions go down qualification。

And put here an addition， and multiplication， addition and multi 30， addition 37。

The value 37 is set is Q of 3， which must be P prime。At 3。



![](img/c2a606883855ccf2f2672c362094855d_46.png)

嗯。Now we can implement the H algorithm to evaluate。P L3 and P prime a3 for the polynomial， this one。



![](img/c2a606883855ccf2f2672c362094855d_48.png)

Okay， now this is Hona。m MALb called M5。Here。Now。Hner will。That the portions of。

The polynomial now it is now increasing order rather than decreasing。 This is the。Dereing order。

 now this is increasinging order。It doesn't matter。You can use。The ur， either way。

 but this M file is made along with the increased order。And x0 is evaluation point。Now， here。

For this one。And。First， we universalize and then。Now， I moving from。M-121 decreasing。And then here。

 D， at the last moment， D will。Include。The derivative value。And the P will。Have the polynomial value。

So you can check this algorithm and step by step and。Yeah， so that you can make sure。

This implementation is right， okay。For this polynomial。

 we collect the coefficients in decreasing order here and x0 is of 3， and we call the Ho that。

Feng Shan， and。P and D are obtained and we try to print out then result is P at 3A is 190 and P prime at 3A is now 37 is saved in this variable D。

Okay， so it is correct implementation。对。Now here for this polynomial。

Use the Newton's method and the horn method， tool。嗯。Now，2。I'll find the， okay。Someha。

Okay get to implement code and find on Op make 0。P你有 it。行。Okay， this has a newutton Ho method。Now。

 this is core sense of。The polynomial。 and that is a beginning point。And。

This tolerance and itm for netoneration。Y。And each iteration， ueration， we call。And for K point x。

 start with now x， x0 is now x， and we call the function Ho and find the function value and derivative value at x。

And this is correction Tom and added the to gap。Updated the point that once H in modulus is small。

 similar than tolerance， then we break the iteration。So that is now nutrient。Along with。

Help from owners of them to get。The polynomial value anditive value。Okay， here a。

That is the portion and extra is a 3 and total is minus 12。And maximum iteration is 1000。

 and we call。Newton Ho。And here the upper is。The approach made to zero。

 And we want to see number of iterations， so that。Here， I T number is now returned。



![](img/c2a606883855ccf2f2672c362094855d_50.png)

So we can print it out here。And the results Newton Ho start with 3。

 and final point is 2 in 7tuerations， the newton method converted in 70tus for the tolerancele。



![](img/c2a606883855ccf2f2672c362094855d_52.png)

Now， let's see the figure。We start from3 here due to methodthda drawn here。70 traditions。

 And then located this zero。啊，系。Acur today。For the function， it is2 zeros。 That is。When is here now。

This one。And this one is true。Okay。In fact， this is quadratic。 this is a photo of the polynomial。

 and there are only two wheel zeros， and there are also two。Comp value zeros， okay。Okay。

 this they end with section。 Thank you。

![](img/c2a606883855ccf2f2672c362094855d_54.png)