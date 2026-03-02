# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p62 14_多重性.zh_en -BV1L9Fde5EXS_p62-

![](img/35a8c6d3574bcb2cb762f3d2d3bd8d8a_0.png)

Hi， my name is Brian Caho， and this is the lecture on multiplicity and multiple comparisons。😊。

So in this lecture， we're going to go fishing。And as a homework problem。

 I'd like you to read this XKCD comic comic number 882。

 and it's really a great description of multiple comparisons and so I won't rehash it here because it's a long one。

 but go read that， that's part of your homework， it's pretty funny。



![](img/35a8c6d3574bcb2cb762f3d2d3bd8d8a_2.png)

So what is multiple comparisons， multiple comparisons is the idea of repeatedly doing hypothesis tests。

Until one comes up significance。 Okay， and this sounds nefarious。

 but it can be often done with the best of intentions， right。

 and multiple comparisons issues can creep in in unexpected ways。

So to just give you an example of multiple comparisons that's sort of famous in the field that I work in is someone took a dead salmon and put it in a functional magnetic resonance imaging scanner。



![](img/35a8c6d3574bcb2cb762f3d2d3bd8d8a_4.png)

And they ran the。ixPixel by pixel analysis actually it's three dimensions。

 so it's often called a voxel instead of a pixel。They ran a voxel by voxel analysis， and。

Checked for a statistical significance at each voxel of whether or not brain activation existed。

 and they found significant things。 And the reason they found significant things is because of a lack of adjustment for multiple comparisons。

 Okay， see， so， and， of course， there was no brain activation because it was a dead salmon。



![](img/35a8c6d3574bcb2cb762f3d2d3bd8d8a_6.png)

So multiple comparisons， this basically just arises from applying many tests and focusing on the significant ones。

 that's the negative aspect of multiple comparisons。

 but basically the idea of multiple comparisons exist just from doing a lot of tests。

 even if all the tests are null， the fact that you will just get some rejections by chance。

Just by randomness。So this can arise from fitting too many models。

This can arise from looking at too many quantities of interest， like in our fish example。

 they just simply looked at too many voxels。Or not too many。

 They just didn't appropriately control for it。 Or I think the nefarious version of multiple comparisons。

 the most nefarious version is phishing expeditions。

 And that's basically testing hypothesistheses without testing everything without ari hypotheses and just trying to focus in on those ones that are just significant。

 So that's that's the most negative version of multiple comparisons。

 you have a large data set you want to explain an outcome you look at every variable you have every combination of variables with lots of models。

 pick out the small subset of significant ones and report them as if you hadn't looked at all the others。

 And I think everyone can agree that there's some problem with doing something like that。

 But I also want to emphasize multiple comparisons is not intrinsically in looking at lots of hypothesis test is not intrinsically a bad thing to do。

 The bad thing to do is to do a lot of hypothesis test and not be up。

Front and account for the fact that you've done a lot of hypothesis tests。

 and that's basically the point of this lecture。And I want to give you the easiest fix possible。

 there is a vast literature on multiple comparisons。

 but the easiest fix is used as an inequality that's named after the mathematician Bon Ferroni。

And this， because it's named after his inequality， it's called the Bonferroni correction。

 And the easiest way to execute a bonferroni correction is if you have a bunch of P values。

 simply multiply your P values by the number of tests that you're performing。 So， for example。

 if you perform 10 tests and one of the P values is 0。01。Then that P value is now 010。 Okay。

 because you've multiplied it by 10。 So the bond for any correction is。Highly robust。

 And it works in all circumstances。 The only problem is it's quite conservative。

 So you you can imagine if you perform 1000 tests， you're multiplying all your P values by 1000。

 It's unlikely you're going to get anything significant。

 So the result of the Bo froni correction is often that it's very conservative。

 tends to err on the side of declaring fewer things significant。

But it's the easiest thing and then if you want to get into harder versions of multiple comparisons。

 you can look into further reading， you can read up upon things like false discovery rates and things like we actually had a relatively well knownn multiple comparisons paper come out of this department from the faculty member named David Duncan。

And Duncan's multiple range test is an example in a nova of multiple comparisons corrections。

 but I think all those are much harder than the simple bonfnic corrections。

 So that's what I would go with now。嗯。One thing I would mention about the Boon fronone correction is that it doesn't give you any guidance on what number to multiply by。

 So if you do a bunch of tests and some are related and and another set are kind of unrelated。

 There are two groups should you aggregate all of those tests together and count you know say if you did 10 tests of this sort and 10 tests of this sort for a totally different hypothesis。

 do you aggregate all of them together and multiply all your P values by 20， or you just say well。

 this is one separate investigation from this other separate investigation and so we multiply these by 10 and these by 10。

 the Bo fronone correction gives no guidance on this problem。

 The Bo fronone correction doesn't tell you what is the right number of tests to multiply by and that is an inherent problem。

 So the best advice I can give on that is to be your own critic know a critic of the results that you have and include all the tests that you think a critic of yours would want you to。

Include as penalizing for having looked at the data。Okay， so again。

 I would just reiterate there's a vast literature on some other techniques for handling multiple comparisons。

 but again the boonfronny correction is the simplest and easiest one and if you're managing someone who's done a lot of test or looked at a lot of models。

 fit a lot of models， the easiest thing to do is when you're looking at the output and you discuss the number of models they fit and the number of parameters they looked at。

 you can just kind of do a rough calculation， you know rounded up to the easiest number to multiply by and use that correction。



![](img/35a8c6d3574bcb2cb762f3d2d3bd8d8a_8.png)