# 约翰霍普金斯大学《数据科学的高级统计｜Advanced Statistics for Data Science》中英字幕（deepseek p105 31_基函数导论.zh_en -BV1htPjeYEFH_p105-

Hi， let's talk about a special instance of least squares that winds up being rather important。



![](img/b94473d4c5f3bbe062bbf861c1dc75d9_1.png)

![](img/b94473d4c5f3bbe062bbf861c1dc75d9_2.png)

So consider the instance where x transpose x。

![](img/b94473d4c5f3bbe062bbf861c1dc75d9_4.png)

They could I。And x is full rank。

![](img/b94473d4c5f3bbe062bbf861c1dc75d9_6.png)

And even maybe what appears to be a little bit stranger， let's consider the case where x is N by N。

So now this may seem to be an odd thing to do， recall。If our if our y is three dimensional， y1， y2。

 y3， and our y at some point in three dimensional space。



![](img/b94473d4c5f3bbe062bbf861c1dc75d9_8.png)

And our x is three dimensional。

![](img/b94473d4c5f3bbe062bbf861c1dc75d9_10.png)

Then why had？

![](img/b94473d4c5f3bbe062bbf861c1dc75d9_12.png)

Will just be。Exactly equal to y because the dimension of the space we're trying to project on is three dimensional。

 our original data is three dimensional， so this extends up to n dimension。

 so it seems like if we have a full rank n by n matrix X what's the point of doing least squares at all so we'll get to that in a minute。



![](img/b94473d4c5f3bbe062bbf861c1dc75d9_14.png)

![](img/b94473d4c5f3bbe062bbf861c1dc75d9_15.png)

![](img/b94473d4c5f3bbe062bbf861c1dc75d9_16.png)

![](img/b94473d4c5f3bbe062bbf861c1dc75d9_17.png)

But notice here， if I want to solve my least squares equation， y minus x beta。



![](img/b94473d4c5f3bbe062bbf861c1dc75d9_19.png)

![](img/b94473d4c5f3bbe062bbf861c1dc75d9_20.png)

And minimize that with respect to beta。Then。My estimate is， of course。

 we've discussed this x transpose x。Inverse x transpose y， but in this case， x transpose x is just I。

And so it works out to just be x transpose y。

![](img/b94473d4c5f3bbe062bbf861c1dc75d9_22.png)

So。

![](img/b94473d4c5f3bbe062bbf861c1dc75d9_24.png)

And looking at this。If my ax。

![](img/b94473d4c5f3bbe062bbf861c1dc75d9_26.png)

Is equal to。And columns。

![](img/b94473d4c5f3bbe062bbf861c1dc75d9_28.png)

Then， this means。That it's the inner product of x1。

 the first column of x with y is the first coefficient， the inner product of x2 with y and so on。

 all the way up to x n with y。

![](img/b94473d4c5f3bbe062bbf861c1dc75d9_30.png)

![](img/b94473d4c5f3bbe062bbf861c1dc75d9_31.png)

And my fitted values now and my fitted values。My white hat。Which is now going to be。



![](img/b94473d4c5f3bbe062bbf861c1dc75d9_33.png)

X。X transpose y。Well。This works out to be nothing other than the summation。



![](img/b94473d4c5f3bbe062bbf861c1dc75d9_35.png)

I equals1 to n。Xi times the inner product of Xi。With why。Now。What's interesting is imagine。

Imagine the case。Where instead of having x， I have just a few columns of x， let's say。X subset。

I'll just put a little x of S。Well x of S transpose x of S， let's suppose it only contains P。

 a random collection， not a random， but any subset of the columns of x。

Also has inner product eye because again， just because of this statement up here。Well。

 then this whole argument just goes through， and then it says that why hat。

 my Y hat fitting the subset。

![](img/b94473d4c5f3bbe062bbf861c1dc75d9_37.png)

Of x。Rather than the full basis x， just fitting the subset of x。



![](img/b94473d4c5f3bbe062bbf861c1dc75d9_39.png)

That Y hat is just the sum over the collection of eyes in the collection of indices。

 the subset indices。

![](img/b94473d4c5f3bbe062bbf861c1dc75d9_41.png)

Xi。Times。The inner product of Xi and Y I。 So what this means is。

If I have my full design matrix and it's a full ranked basis for RN。My coefficients just work。

 and it's aor and normal basis。My coefficients work out to just be the inner products between the basis elements and my outcome。

 and if I want to fit instead of a。alN dimensional version of this basis。

 if I just want a p dimensional version of this basis。

 I can just grab the relevant subset of these coefficients。Right。

