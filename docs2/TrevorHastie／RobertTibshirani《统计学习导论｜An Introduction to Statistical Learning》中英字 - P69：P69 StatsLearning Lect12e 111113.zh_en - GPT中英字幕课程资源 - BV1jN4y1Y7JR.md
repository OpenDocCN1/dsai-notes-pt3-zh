# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P69：P69 StatsLearning Lect12e 111113.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/a83c3151690360d7093161bde05d38cf_0.png)

Welcome back。And in the last segment of this section。

 we're going to see an example of how requestquesting applied to a study of breast cancer。

So this is the last part of the segment， this is an example which actually Tra and I are both involved in。



![](img/a83c3151690360d7093161bde05d38cf_2.png)

Actually 10 years ago now， with a postdoc at Stanford in oncology， Thereez Sorely。

 Theres had measured。

![](img/a83c3151690360d7093161bde05d38cf_4.png)

![](img/a83c3151690360d7093161bde05d38cf_5.png)

Gene expression。From gene chips for about 88 women who had breast cancer are being treated for breast cancer and gene expression measurements for about 8000 genes。

 so what that means is for each of the 88 patients， there's a quantitative measurement for each of 8。

000 genes which measures how much that gene was expressing how active it was for that woman。

 and this is a very common kind of study now where people look at gene expression to try to understand the basis of diseases like breast cancer and figure out whether there are subtypes of the disease which should be treated in a different way。

 so this is quite large the amount of data with 88 patients 8000 features。



![](img/a83c3151690360d7093161bde05d38cf_7.png)

![](img/a83c3151690360d7093161bde05d38cf_8.png)

![](img/a83c3151690360d7093161bde05d38cf_9.png)

![](img/a83c3151690360d7093161bde05d38cf_10.png)

![](img/a83c3151690360d7093161bde05d38cf_11.png)

![](img/a83c3151690360d7093161bde05d38cf_12.png)

![](img/a83c3151690360d7093161bde05d38cf_13.png)

![](img/a83c3151690360d7093161bde05d38cf_14.png)

She used the group used average linkage with correlation metric， again。

 because this is the case where genes are in the same units in a sense。

 but they're measured the same units， but。

![](img/a83c3151690360d7093161bde05d38cf_16.png)

![](img/a83c3151690360d7093161bde05d38cf_17.png)

![](img/a83c3151690360d7093161bde05d38cf_18.png)

The actual level of gene expression wasn't very reliable because it varies across the way it's measured。

 but what's more thought to be more important was the shape of the relative expression of different genes for the same patient。

 so that's why we use correlation metric。

![](img/a83c3151690360d7093161bde05d38cf_20.png)

![](img/a83c3151690360d7093161bde05d38cf_21.png)

And we did higherquesting of the samples with the 88 patients。



![](img/a83c3151690360d7093161bde05d38cf_23.png)

Now， when Jase first used the full set of genes， the classroom she got out wasn't satisfactory。 Now。

 what does that mean Well，' again， it's very subjective， but。



![](img/a83c3151690360d7093161bde05d38cf_25.png)

Itt it wasn't very informative to Therez and her collaborators。

 so rather they use a subset of the genes called the intrinsic gene。

 so this is a way of choosing a most more informative subset of genes。

And I won't go into detail except the same words， in this particular study。

 these women were given chemotherapy， and there was actually a sample taken before and after for each woman。



![](img/a83c3151690360d7093161bde05d38cf_27.png)

And gene expression measurements were available before and after。 So what Theres did was she。

 she defined what called intrinsic genes。 So for each woman for each gene。



![](img/a83c3151690360d7093161bde05d38cf_29.png)

![](img/a83c3151690360d7093161bde05d38cf_30.png)

And for each woman， we look to see which genes had the smallest variation within a woman。



![](img/a83c3151690360d7093161bde05d38cf_32.png)

Within a woman， as opposed to between the 88 women。



![](img/a83c3151690360d7093161bde05d38cf_34.png)

And the ones that the smallest variation were defined to be the intrinsic genes of 500 most the 500 genes was the lowest variation。

 The idea being， again， this is a biological concept was that。



![](img/a83c3151690360d7093161bde05d38cf_36.png)

Jeans， which didn't very much in a woman。Before and after chemotherapy。

 compared to between one variation， were thought to be intrinsic to her cell biology。

So they are thought to be the ones that could could best drive the clustering and separate the women in terms of their biology and maybe the response to treatment。

 They varied a lot between women， but little within women across the two repeated measures。

 So doing that we we got the following clustering。 So what do we see here。 First of all， this is the。



![](img/a83c3151690360d7093161bde05d38cf_38.png)

![](img/a83c3151690360d7093161bde05d38cf_39.png)

![](img/a83c3151690360d7093161bde05d38cf_40.png)

![](img/a83c3151690360d7093161bde05d38cf_41.png)

Here are the。

![](img/a83c3151690360d7093161bde05d38cf_43.png)

500 or so intrinsic genes。 And this is called a heat mount。

And this is a common display for this kind of data， so what do we see here。

 each row of the heat map is a gene。

![](img/a83c3151690360d7093161bde05d38cf_45.png)

![](img/a83c3151690360d7093161bde05d38cf_46.png)

500 so genes， each column is a woman， one of the 88 women， and each pixel is displayed as either。



![](img/a83c3151690360d7093161bde05d38cf_48.png)

Green， which is negative。 so gene expression is normalized。

 so it runs from something like minus5 to plus5。 So green would be negative and red is positive。

 So green means the gene expression for that gene for that woman is lower than average and red means it's higher than average。



![](img/a83c3151690360d7093161bde05d38cf_50.png)

![](img/a83c3151690360d7093161bde05d38cf_51.png)

![](img/a83c3151690360d7093161bde05d38cf_52.png)

![](img/a83c3151690360d7093161bde05d38cf_53.png)

And what's been done here is we applied hierarchical clustering to the columns as the women in the way I just described。



![](img/a83c3151690360d7093161bde05d38cf_55.png)

![](img/a83c3151690360d7093161bde05d38cf_56.png)

In addition， how co was done to the rows， the genes。 and this is done in both directions。

 And that's why this picture looks， it's got it has patches of red and green， right。

 because it looks because we've sorted them， basically， we sorted the。



![](img/a83c3151690360d7093161bde05d38cf_58.png)

![](img/a83c3151690360d7093161bde05d38cf_59.png)

![](img/a83c3151690360d7093161bde05d38cf_60.png)

We' done article clustering， and we sorted the observations by the order of the leaves in the tree。

 both for genes and both and for samples。

![](img/a83c3151690360d7093161bde05d38cf_62.png)

And that's why if， if we just display the data in the order， we， we obtained it。

 This picture would not look so nice。 So it it would be。



![](img/a83c3151690360d7093161bde05d38cf_64.png)

A checkerboard pattern and would look very random， but here looks much more structured because of the clusters when applied and the ordering of the leaves has been used to reorder the rows and columns。



![](img/a83c3151690360d7093161bde05d38cf_66.png)

![](img/a83c3151690360d7093161bde05d38cf_67.png)

Just to。

![](img/a83c3151690360d7093161bde05d38cf_69.png)

This actually this kind of display was actually used first at Stanford in the gens labs around the time the gene chip was invented。

 which is also done partly here at Stanford。 And I think this has become very attractive just because it's it's a nice way just to see all the data if you have if you're given a data set of 88 observations women in 8000 genes。

 that's a lot of data just to even look at And so the first kind of challenge is how do I just make a display so I can look at all the data and see that the gross patterns And here this is actually a very effective display is one of the pioneering if it's in the labs of Patrick Brown and David Botstein gene expression really started So it's kind of funny to think that a pioneering。



![](img/a83c3151690360d7093161bde05d38cf_71.png)

![](img/a83c3151690360d7093161bde05d38cf_72.png)

![](img/a83c3151690360d7093161bde05d38cf_73.png)

![](img/a83c3151690360d7093161bde05d38cf_74.png)

![](img/a83c3151690360d7093161bde05d38cf_75.png)

![](img/a83c3151690360d7093161bde05d38cf_76.png)

![](img/a83c3151690360d7093161bde05d38cf_77.png)

![](img/a83c3151690360d7093161bde05d38cf_78.png)

![](img/a83c3151690360d7093161bde05d38cf_79.png)

Peace of science is actually display， but that's often the case， right， some some very simple things。

 which might be seem trivial， actually can have a lot of impact。 just in this case。

 just the ability to to look at。

![](img/a83c3151690360d7093161bde05d38cf_81.png)

![](img/a83c3151690360d7093161bde05d38cf_82.png)

To arrange and display the data informatively was very useful， and it still used a lot today。

 So here's the full heat map。 and then the clustering tree is at the top。



![](img/a83c3151690360d7093161bde05d38cf_84.png)

![](img/a83c3151690360d7093161bde05d38cf_85.png)

![](img/a83c3151690360d7093161bde05d38cf_86.png)

This is here， and it's been expanded out here。 And it's。



![](img/a83c3151690360d7093161bde05d38cf_88.png)

It's been divided into one， two， three。4， five， six， seven， eight clusters。



![](img/a83c3151690360d7093161bde05d38cf_90.png)

The gray is just basically an unknown group， but the other clusters have been labeled by names。



![](img/a83c3151690360d7093161bde05d38cf_92.png)

![](img/a83c3151690360d7093161bde05d38cf_93.png)

Like normal， basal， ERB2， luminal， A luminal B， these names were chosen by Ters and collaborators based on the genes that we expressing in the groups。

 so now if we look at this picture。

![](img/a83c3151690360d7093161bde05d38cf_95.png)

![](img/a83c3151690360d7093161bde05d38cf_96.png)

What we've taken is the same clusters and we've just taken subsets of the rows。



![](img/a83c3151690360d7093161bde05d38cf_98.png)

That's these five groups， and。

![](img/a83c3151690360d7093161bde05d38cf_100.png)

These are genes which are expressing highly in one or more of these peak groups。

 like for example here， let's see。

![](img/a83c3151690360d7093161bde05d38cf_102.png)

This block of sea genes is suppress Holly in the。

![](img/a83c3151690360d7093161bde05d38cf_104.png)

Red group and the blue group。 This block of D genes expressing highly in these cluster ce， so。



![](img/a83c3151690360d7093161bde05d38cf_106.png)

Then the oncologist will look at this and they'll try to understand， well。

 how are so these groups are different with respect to these particular genes。

 what do these genes do in the cells？

![](img/a83c3151690360d7093161bde05d38cf_108.png)

![](img/a83c3151690360d7093161bde05d38cf_109.png)

![](img/a83c3151690360d7093161bde05d38cf_110.png)

What does it tell us about at least these subgroups？



![](img/a83c3151690360d7093161bde05d38cf_112.png)

In particular， let's under the。The last display of this。

 if you look at these subgroups and you look at the survival of these women。

 these are calledcaamire survival curves。

![](img/a83c3151690360d7093161bde05d38cf_114.png)

![](img/a83c3151690360d7093161bde05d38cf_115.png)

These women were treated for cancer and followed up to see and hopefully。Recovered， some didn't。

 and the survival curves of the groups are given here。 So， for example， the basal group。

 I believe they're ready and the purple， which groups are those basils。



![](img/a83c3151690360d7093161bde05d38cf_117.png)

![](img/a83c3151690360d7093161bde05d38cf_118.png)

Basil and Errby2。Are doing。Not nearly as well。 the probably survival is much worse as the。



![](img/a83c3151690360d7093161bde05d38cf_120.png)

This group， did that group， the luminal A is doing much better。



![](img/a83c3151690360d7093161bde05d38cf_122.png)

So because their survival is quite different， the scientists were really wanted to find out how are these groups different in with respect to what genes and that it gives us a clue as to how how the diseases might be different in the different groups。



![](img/a83c3151690360d7093161bde05d38cf_124.png)

![](img/a83c3151690360d7093161bde05d38cf_125.png)

So that's an example of clustering for in a real scientific problem that's of importance。



![](img/a83c3151690360d7093161bde05d38cf_127.png)

So just to wrap up this section though， unsupervised learning is what has been the topic。

 we've talked about principal components and clustering and they're important in general for understanding the variation and grouping structure of a set of unlabeled data。

 so they can be useful for themselves， just by themselves。

 that we saw for example in that last example， or as a preprocessor to choose a linear combination of features for supervised learning。

And we also saw that the problem is intrinsic harder than supervisor learning because there's no label。

 there's no gold standard so we can't use prediction error to figure out how well we're doing and we've just shown you two techniques in these presentations。

 principal components and clustering and those are part of a big tool by a bag of lots of other techniques some of them are listed here like self-organizing maps in the independent component analysis。

 spectral clustering and many more many more of these are covered in our book elements of statistical learning in chapter 14 and even beyond that there are many others as well。

