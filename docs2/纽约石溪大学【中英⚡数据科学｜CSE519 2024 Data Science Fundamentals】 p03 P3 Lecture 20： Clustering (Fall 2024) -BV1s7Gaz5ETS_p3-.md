# 纽约石溪大学【中英⚡数据科学｜CSE519 2024 Data Science Fundamentals】 p03 P3 Lecture 20： Clustering (Fall 2024) -BV1s7Gaz5ETS_p3-

![](img/47ecd5140a2038c2597922896eddfe7f_0.png)

Let's， I guess I guess let's get started。 First， are there any questions about， by the way。

 it's funny。 I'm just just so you know what I'm thinking today。



![](img/47ecd5140a2038c2597922896eddfe7f_2.png)

![](img/47ecd5140a2038c2597922896eddfe7f_3.png)

I am。 this is gonna be a lecture on clustering。 And I'm looking around the room。

 Does anybody see clusters。

![](img/47ecd5140a2038c2597922896eddfe7f_5.png)

Okay， I'm seeing an unusual cluster today。 Okay， and clustering is gonna to be about recognizing patterns in point sets。

 And that's so maybe we'll， we'll keep this some inspiration。 Okay， Any question。

 But before we get into that。 The question of homework 3。 Any questions about homework 3。



![](img/47ecd5140a2038c2597922896eddfe7f_7.png)

![](img/47ecd5140a2038c2597922896eddfe7f_8.png)

![](img/47ecd5140a2038c2597922896eddfe7f_9.png)

![](img/47ecd5140a2038c2597922896eddfe7f_10.png)

![](img/47ecd5140a2038c2597922896eddfe7f_11.png)

How many people feel they have it under control？

![](img/47ecd5140a2038c2597922896eddfe7f_13.png)

See a bunch of people under control。 any technical blocks that people are having。



![](img/47ecd5140a2038c2597922896eddfe7f_15.png)

No， any technical blocks。

![](img/47ecd5140a2038c2597922896eddfe7f_17.png)

No， okay， and any interesting observations or anything people see that was surprising to them。



![](img/47ecd5140a2038c2597922896eddfe7f_19.png)

![](img/47ecd5140a2038c2597922896eddfe7f_20.png)

Yeah。そななす。

![](img/47ecd5140a2038c2597922896eddfe7f_22.png)

た。When music。User dimensions。Okay， a lot of， first of all， let's， let's okay。

 so I made some kind of a comment on。

![](img/47ecd5140a2038c2597922896eddfe7f_24.png)

![](img/47ecd5140a2038c2597922896eddfe7f_25.png)

Dimension reduction， which I swear we will talk about in a couple of classes， maybe next class， okay。



![](img/47ecd5140a2038c2597922896eddfe7f_27.png)

![](img/47ecd5140a2038c2597922896eddfe7f_28.png)

Was going to kind of reduce the dimensionality while trying to preserve as much structure as it could。



![](img/47ecd5140a2038c2597922896eddfe7f_30.png)

Now， as you reduce it too many dimensions， the structure should go away okay。

 now the question is how many is too many， and that's probably somewhat dependent upon the application and stuff。



![](img/47ecd5140a2038c2597922896eddfe7f_32.png)

![](img/47ecd5140a2038c2597922896eddfe7f_33.png)

![](img/47ecd5140a2038c2597922896eddfe7f_34.png)

So you seem， we'll get back to that， but what you're waving， what is it？



![](img/47ecd5140a2038c2597922896eddfe7f_36.png)

This to the dimension。When I reduce my em， the high， high dimensional ems。



![](img/47ecd5140a2038c2597922896eddfe7f_38.png)

Fored。様ける。

![](img/47ecd5140a2038c2597922896eddfe7f_40.png)

点大问 see。Okay， so you're saying， if I understood， first of all， there are two different tasks， right。

 There is language， and there is vision。

![](img/47ecd5140a2038c2597922896eddfe7f_42.png)

![](img/47ecd5140a2038c2597922896eddfe7f_43.png)

Okay， so it's possible things could behave differently on language and vision。



![](img/47ecd5140a2038c2597922896eddfe7f_45.png)

So let's just take a quick poll around here， who among the people who if we talk about the vision task。



![](img/47ecd5140a2038c2597922896eddfe7f_47.png)

If we reduce the clusters to a moderate dimension。

![](img/47ecd5140a2038c2597922896eddfe7f_49.png)

Does the accuracy of this thing fall out the roof or does it stay about the same。



![](img/47ecd5140a2038c2597922896eddfe7f_51.png)

Say for the vision desk， I'm hearing some people say it fell。

Now let's take a look at the language task。 Okay， when you reduce the language。

 the dimension by a moderate amount， did the accuracy fall or stay about the same？



![](img/47ecd5140a2038c2597922896eddfe7f_53.png)

![](img/47ecd5140a2038c2597922896eddfe7f_54.png)

I'm hearing that's the same on that side of the room。 And on this side。

 is it the same or did it fall。

![](img/47ecd5140a2038c2597922896eddfe7f_56.png)

What。Okay， so that's why there's two clusters in the room。

 This is the people who had stayed the same on。 And these are the people who would fell it。



![](img/47ecd5140a2038c2597922896eddfe7f_58.png)

Okay， did it fall by a lot or fall by a small amount？😡。



![](img/47ecd5140a2038c2597922896eddfe7f_60.png)

Small， okay， so when I， when， when， when we did it， I know we did it on the language 1。

 I'm not sure we did it， You know， I don't。

![](img/47ecd5140a2038c2597922896eddfe7f_62.png)

Remember， for sure that we did it on the Vi  one。

![](img/47ecd5140a2038c2597922896eddfe7f_64.png)

On the vision 1， what I saw was that when you drop， when you shra the dimensions by a fair amount。

 the quality stayed about the same。

![](img/47ecd5140a2038c2597922896eddfe7f_66.png)

![](img/47ecd5140a2038c2597922896eddfe7f_67.png)

And even sometimes went up a little bit when I lowered the number of dimensions。 Who saw that。



![](img/47ecd5140a2038c2597922896eddfe7f_69.png)

![](img/47ecd5140a2038c2597922896eddfe7f_70.png)

He saw that。 He saw that。 Some of you didn't see that。



![](img/47ecd5140a2038c2597922896eddfe7f_72.png)

The question of why is that possible， Okay， is the first question。

 Why is it possible that reducing the dimensions would make it better。



![](img/47ecd5140a2038c2597922896eddfe7f_74.png)

![](img/47ecd5140a2038c2597922896eddfe7f_75.png)

Well， one would be as if a lot of the dimensions had noise。



![](img/47ecd5140a2038c2597922896eddfe7f_77.png)

Suppose I take your data and I give you， I Ed， you say， oh。

 I've only got 100 dimensions in my data set。

![](img/47ecd5140a2038c2597922896eddfe7f_79.png)

![](img/47ecd5140a2038c2597922896eddfe7f_80.png)

And I say， well， I can give you another hundred。 Just generate random numbers in each column。 Okay。

 now youve got 200 dimensions。 Okay， is that going to make your clustering better or worse。



![](img/47ecd5140a2038c2597922896eddfe7f_82.png)

![](img/47ecd5140a2038c2597922896eddfe7f_83.png)

![](img/47ecd5140a2038c2597922896eddfe7f_84.png)

Probably worse。Now， if you do something to reduce the dimensions。



![](img/47ecd5140a2038c2597922896eddfe7f_86.png)

Which will likely try to squeeze out the noise。

![](img/47ecd5140a2038c2597922896eddfe7f_88.png)

Might you now do better， okay， so that's the mystery of why you might do better。😡。



![](img/47ecd5140a2038c2597922896eddfe7f_90.png)

Maybe a lot of the features that you have in there are are， you know。

 there's some noise involved with them， they're not that important。

 maybe they are essentially duplicates highly correlated with other features。



![](img/47ecd5140a2038c2597922896eddfe7f_92.png)

![](img/47ecd5140a2038c2597922896eddfe7f_93.png)

![](img/47ecd5140a2038c2597922896eddfe7f_94.png)

So that's why it might do better。

![](img/47ecd5140a2038c2597922896eddfe7f_96.png)

Okay。The thing that I even for the ones that it went down on， as I recall。

 you went down to 10 dimensions in the NLB1 from how many did you start with。



![](img/47ecd5140a2038c2597922896eddfe7f_98.png)

![](img/47ecd5140a2038c2597922896eddfe7f_99.png)

How many。

![](img/47ecd5140a2038c2597922896eddfe7f_101.png)

What？I didn't hear that。7，7，6，8。 Okay， so he went from 768 down to 10。



![](img/47ecd5140a2038c2597922896eddfe7f_103.png)

嗯。

![](img/47ecd5140a2038c2597922896eddfe7f_105.png)

Who did it maintain reasonably， at least reasonably similar performance？



![](img/47ecd5140a2038c2597922896eddfe7f_107.png)

Raise your end if it was reasonably similar。

![](img/47ecd5140a2038c2597922896eddfe7f_109.png)

He says yes。He says yes。They say yes， you guys don't say yes。



![](img/47ecd5140a2038c2597922896eddfe7f_111.png)

What percentages did you have before and after？

![](img/47ecd5140a2038c2597922896eddfe7f_113.png)

Bllpark figures of accurate。

![](img/47ecd5140a2038c2597922896eddfe7f_115.png)

Okay。

![](img/47ecd5140a2038c2597922896eddfe7f_117.png)

So what I am expecting， first of all， you guys do the experiment。

 but I think you will find that for the language ones， if you compress it。

 you should be able to preserve roughly the same accuracy on that。



![](img/47ecd5140a2038c2597922896eddfe7f_119.png)

O。

![](img/47ecd5140a2038c2597922896eddfe7f_121.png)

We'll talk more about dimension reduction next class。 Okay， but as far as why this is useful。

 if it does squeeze out noise。 Okay， it might make it more accurate。



![](img/47ecd5140a2038c2597922896eddfe7f_123.png)

![](img/47ecd5140a2038c2597922896eddfe7f_124.png)

And even if it doesn't make it more accurate， it certainly makes it more convenient to work with。



![](img/47ecd5140a2038c2597922896eddfe7f_126.png)

![](img/47ecd5140a2038c2597922896eddfe7f_127.png)

Again， but if when you squeeze it out， it completely destroys all structure in there。 That's bad。

 okay。

![](img/47ecd5140a2038c2597922896eddfe7f_129.png)

Any questions about that？Any other questions about the homework？Okay， and finally。

 any questions about the projects。 If you have， I guess a question。

 I don't know if this question is it's fine， If not。

 if you want to come and talk to me about your project thing。

 I'm happy to talk to anybody after class or some either during my office hours。😊。



![](img/47ecd5140a2038c2597922896eddfe7f_131.png)

![](img/47ecd5140a2038c2597922896eddfe7f_132.png)

![](img/47ecd5140a2038c2597922896eddfe7f_133.png)

![](img/47ecd5140a2038c2597922896eddfe7f_134.png)

Any questions？Okay， so what I'd like to now talk about is clustering。

 which is a I sort of introduced at the end of last lecture but basically it's the problem of you're given a randomly structured or a structured group of points typically in space。

 and some you know in some data space and you'd like to find natural groupings of them。



![](img/47ecd5140a2038c2597922896eddfe7f_136.png)

![](img/47ecd5140a2038c2597922896eddfe7f_137.png)

![](img/47ecd5140a2038c2597922896eddfe7f_138.png)

![](img/47ecd5140a2038c2597922896eddfe7f_139.png)

![](img/47ecd5140a2038c2597922896eddfe7f_140.png)

![](img/47ecd5140a2038c2597922896eddfe7f_141.png)

And this is a， you know， one of the best applications of clustering that I have ever seen this diagram。

 So I'd like to explain it because it this， this was kind of a， you know。

 amazing bit of scientific discovery in what you're seeing here。 This is a。😊。



![](img/47ecd5140a2038c2597922896eddfe7f_143.png)

![](img/47ecd5140a2038c2597922896eddfe7f_144.png)

![](img/47ecd5140a2038c2597922896eddfe7f_145.png)

![](img/47ecd5140a2038c2597922896eddfe7f_146.png)

Data， okay， there， there is a technique， various techniques and， okay。

 you guys have cells in your body。

![](img/47ecd5140a2038c2597922896eddfe7f_148.png)

You know， these cells divide， right。

![](img/47ecd5140a2038c2597922896eddfe7f_150.png)

You know， you've seen these pictures right， You have a cell。 suddenly it goes。

 dos this and bloop two cells， right。

![](img/47ecd5140a2038c2597922896eddfe7f_152.png)

What happens when your cells divide badly， Does anybody know what happens to you when you have problems when your cells don't divide？



![](img/47ecd5140a2038c2597922896eddfe7f_154.png)

![](img/47ecd5140a2038c2597922896eddfe7f_155.png)

Badly。Cancer， okay， bad thing。 cancer is a disease of essentially of cell division。

 so understanding how cells divide are important， okay。



![](img/47ecd5140a2038c2597922896eddfe7f_157.png)

![](img/47ecd5140a2038c2597922896eddfe7f_158.png)

![](img/47ecd5140a2038c2597922896eddfe7f_159.png)

Now， cells dividing the fact that cells divide is a very fundamental part of what cells do。 Okay。

 cells had to learn how to had to evolve， how to divide。



![](img/47ecd5140a2038c2597922896eddfe7f_161.png)

![](img/47ecd5140a2038c2597922896eddfe7f_162.png)

You know， billions of years ago， not not recently。

![](img/47ecd5140a2038c2597922896eddfe7f_164.png)

So all things that are cells that all cells kind of divide in roughly the same way。



![](img/47ecd5140a2038c2597922896eddfe7f_166.png)

![](img/47ecd5140a2038c2597922896eddfe7f_167.png)

So this is a study to try to figure out how cell division works in yeast。

 okay how much are you like yeast， well in many ways you are smarter than yeast， okay。

 but your cells divide in roughly the same way， okay？



![](img/47ecd5140a2038c2597922896eddfe7f_169.png)

![](img/47ecd5140a2038c2597922896eddfe7f_170.png)

![](img/47ecd5140a2038c2597922896eddfe7f_171.png)

So what is this trying to do？

![](img/47ecd5140a2038c2597922896eddfe7f_173.png)

The question is， what genes are involved in。

![](img/47ecd5140a2038c2597922896eddfe7f_175.png)

Helping in， in。The cell division process， okay？

![](img/47ecd5140a2038c2597922896eddfe7f_177.png)

And yeast has somewhat fewer genes。