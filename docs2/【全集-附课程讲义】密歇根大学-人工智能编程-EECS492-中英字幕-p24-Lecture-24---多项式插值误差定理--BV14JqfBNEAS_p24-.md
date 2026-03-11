# 【全集-附课程讲义】密歇根大学-人工智能编程-EECS492-中英字幕-p24-Lecture-24---多项式插值误差定理--BV14JqfBNEAS_p24-

It is part2 of Section 3。23 polynomial interpolation Ethereorem。In the first part of the section。

We studied polynomial interpolation and constructed interpolating polynomials in the Laange form。

Here we have a question。Ren。On interpoling polynomial PM， approximate。Of function have。Then。

 what is the error。In this， second part， we'll try to answer the question。Deid a theorem。

Polynomial interpolation Eum。Frees。Continuously defishable M plus1 times。

And PN is the interpoum polynomial of T and OF。Add M plus  one distinct points， x 0 x N。

 which are chosen in the interval A B A。Then， for each x。In the interval。There is number chx。

 chx is a number。Which it depends on。X。Such van。Here the difference between FO X and Pnx。

As given in this ring。This is the。Interpolation error。

This theorem can be compared with the Taylor theorem。In Taylorfiem， the Lagarraj remainderda。

Is given here， along with。X minus a to the M plus 1。So rather than this product in teletheorem。

 you'll see here now x minus a to the n plus 1。So it is。Well compared with the Taylor theorem。Now。

 for the interolating polynomial， and we have to make sure this term is a sum。

Then the polynomial is appromating the function quite well。Let's see here the example。

The fushan Ex is a canax now。Will approximate it by saying。嗯。Tgu5 polynomia。And equally。

 this3 to points so that there must be six points stuff from -1。 So X I are here minus-1 and minus-0。

26。 So each sub interval length is 0。4。Because the whole length is now。A2。Okay。

Now we want to measure the maximum possible error。Okay。So here the points are given。And now。

 following this formula， N is5， so that we have to get。6 with a tilt tip。And we measure yet。

And then this term， but now cos must be between minus1 to1， so the maximum pass value is a sine 1。No。

We are organized this term， and。X minus minus1， x minus minus 0。6， so the whole product for that one。

Now by using a map cord， we try to measure the absolute maximum， which is this one。



![](img/14ec1dd889e0ae15f788fe9385324bb1_1.png)

So that the difference。Is now Samsva。And this one is bounded by son。And6 effectial。 And this one。

Maxim values already we have here， G Max。So if we multiply these terms。

 then we can get here 8 times 10 to the minus5。So once you try to make5 of the polynomial for sinine x between minus1 to1。

Then maximum possible error is this one。 This is。Upper bound。



![](img/14ec1dd889e0ae15f788fe9385324bb1_3.png)

Okay。So it is quite accurate。 The polynomial will approximate the function quite nicely。



![](img/14ec1dd889e0ae15f788fe9385324bb1_5.png)

Okay， here we have another theordom。For interpolation error。

Polynomial interpo E theor 4 equallys spaced the nodes。



![](img/14ec1dd889e0ae15f788fe9385324bb1_7.png)

Now， we assume that the points at chosen from a to B equally spaced。 So the first we。

Find h p minus a over n， and then here I is moving from0 to n and a plus ih so that here beginning point is x is0 A and the next one is x1 and last one will be x N。

 then here the error is bounded by this to。So that when it is equally spatial then rather than。



![](img/14ec1dd889e0ae15f788fe9385324bb1_9.png)

This competition， we may try to use this one to get the upper bound easily。



![](img/14ec1dd889e0ae15f788fe9385324bb1_11.png)

Okay， here M capital M is the maximum。Of N F to the M plus force derivative。That function， right。

 Okay， here。

![](img/14ec1dd889e0ae15f788fe9385324bb1_13.png)

Now here we have proof。And。You may try to read it， but will not go through the detail for the proof。



![](img/14ec1dd889e0ae15f788fe9385324bb1_15.png)

![](img/14ec1dd889e0ae15f788fe9385324bb1_16.png)

Okay， now for the same problem， same example with F of X sine X。 Now we'll try to get。あフてれ。

Polynomial， interpooling polynomial at 6 equally distributed to the points in minus-1 to1。



![](img/14ec1dd889e0ae15f788fe9385324bb1_18.png)

And we try to measure the upper bound biasing here practical quantity。



![](img/14ec1dd889e0ae15f788fe9385324bb1_20.png)

Now。

![](img/14ec1dd889e0ae15f788fe9385324bb1_22.png)

That one is more convenient， but。The upper bond is measured roughly。



![](img/14ec1dd889e0ae15f788fe9385324bb1_24.png)

But it is true。And by using this one， let's try to see the upper bound。 In fact。

 try to measure that one。

![](img/14ec1dd889e0ae15f788fe9385324bb1_26.png)

![](img/14ec1dd889e0ae15f788fe9385324bb1_27.png)

Here。Okay。So。Using Python。We try to get here now。And for F O X。

 we try to make M plus first time derivative。And for that， now maximum is measured。

 so n becomes that one。嗯。But now， rather than Gm， we try to use this some other parts from the theorem。

 and we can get thearrow bound and print towel。That is now this one。 That is about 1。4。

Times 1 to minus4。Which is about twice a larger than and more tight upper bound。But along with this。

 I will lose upper bound and is true so that the arrow cannot be larger than this one。Okay。



![](img/14ec1dd889e0ae15f788fe9385324bb1_29.png)

嗯。Here， that will be more convenient， but Ill be lose and。

And so that you have to understand why we are doing this two different。Uple bounds， okay？



![](img/14ec1dd889e0ae15f788fe9385324bb1_31.png)

Okay， that's the end of the section。 Thank you。

![](img/14ec1dd889e0ae15f788fe9385324bb1_33.png)