# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p04 3_排列与组合.zh_en -BV1r483zbEzN_p4-

。

![](img/3742af1a256671c019090f4c341c86ff_1.png)

We're not going to talk about the two most fundamental types of counting in statistics and those are。



![](img/3742af1a256671c019090f4c341c86ff_3.png)

Per mutations。

![](img/3742af1a256671c019090f4c341c86ff_5.png)

And combinations。So a permutation。

![](img/3742af1a256671c019090f4c341c86ff_7.png)

And a combination are both used for accountinging without repetition that basically means that once you have。

 if you have a set of options right like a set of different colored balls and you're saying how many ways can I select or order these balls if if you can。



![](img/3742af1a256671c019090f4c341c86ff_9.png)

![](img/3742af1a256671c019090f4c341c86ff_10.png)

Pull it the option right， the ball out of the set and it's no longer there。

 that's when we're using permutations and combinations。 If you can replace it。

 then that's something else we'll talk about towards the end of the module。

 So permutations and combinations are both done for issues when there is without repetition。



![](img/3742af1a256671c019090f4c341c86ff_12.png)

![](img/3742af1a256671c019090f4c341c86ff_13.png)

![](img/3742af1a256671c019090f4c341c86ff_14.png)

![](img/3742af1a256671c019090f4c341c86ff_15.png)

![](img/3742af1a256671c019090f4c341c86ff_16.png)

系 the。Tian。Sorry， I do numbers， not words。When when we're talking about permutations。

 we're talking about ordered。😊。

![](img/3742af1a256671c019090f4c341c86ff_18.png)

![](img/3742af1a256671c019090f4c341c86ff_19.png)

Selection。When we talk about combinations， we're talking about unordered。

 So that means un or ordered that means that。

![](img/3742af1a256671c019090f4c341c86ff_21.png)

![](img/3742af1a256671c019090f4c341c86ff_22.png)

The order in which you've selected it doesn't matter， right？



![](img/3742af1a256671c019090f4c341c86ff_24.png)

And we'll give you examples of each。

![](img/3742af1a256671c019090f4c341c86ff_26.png)

So my notation for permutation will be， let's say that I have n possible things to choose from。

 and Im going to select from them are options。

![](img/3742af1a256671c019090f4c341c86ff_28.png)

![](img/3742af1a256671c019090f4c341c86ff_29.png)

Okay。

![](img/3742af1a256671c019090f4c341c86ff_31.png)

Well， what does that look like well I'm going to have。



![](img/3742af1a256671c019090f4c341c86ff_33.png)

A bunch of different boxes here to choose from， right，1，2，3， right， so I'll have  one，2，3。



![](img/3742af1a256671c019090f4c341c86ff_35.png)

All the way up to our options。

![](img/3742af1a256671c019090f4c341c86ff_37.png)

And so in this first box， how many choices do I have Well。

 I have n items to choose from now I told you there's no repetition。

 so now that I've selected one item， how many do I have to choose from next。



![](img/3742af1a256671c019090f4c341c86ff_39.png)

![](img/3742af1a256671c019090f4c341c86ff_40.png)

Well， n minus1。 All right， now I've taken n minus-1 another option。 I now have selected two spots。

 How many do I have， I have n minus2， and that continues all the way until you get to n minus R。



![](img/3742af1a256671c019090f4c341c86ff_42.png)

![](img/3742af1a256671c019090f4c341c86ff_43.png)

![](img/3742af1a256671c019090f4c341c86ff_44.png)

Now， if you recall， what we then have by the generalized principle of counting is the number of permutations is going to be equal to n times n minus1 times n minus 2。



![](img/3742af1a256671c019090f4c341c86ff_46.png)

![](img/3742af1a256671c019090f4c341c86ff_47.png)

![](img/3742af1a256671c019090f4c341c86ff_48.png)

All the way until we get to n minus R， right？

![](img/3742af1a256671c019090f4c341c86ff_50.png)

So we can write that more generally。😊。

![](img/3742af1a256671c019090f4c341c86ff_52.png)

![](img/3742af1a256671c019090f4c341c86ff_53.png)

As if you notice this where you have n， n minus1， n minus2， so forth， right。

 we represent that with the symbol of an exclamation point here， which is factorial。

 and what does n factorial mean， it means n times n minus1 times n minus2。

 if I to give you an example like3 factorial would be3 times 2 times 1。



![](img/3742af1a256671c019090f4c341c86ff_55.png)

![](img/3742af1a256671c019090f4c341c86ff_56.png)

![](img/3742af1a256671c019090f4c341c86ff_57.png)

![](img/3742af1a256671c019090f4c341c86ff_58.png)

So。It doesn't go all the way to one， though， because we stop here at n minus R。 And so the way we。

 we do that is we divide by the。

![](img/3742af1a256671c019090f4c341c86ff_60.png)

![](img/3742af1a256671c019090f4c341c86ff_61.png)

N minus R。Options that we are not going to be counting。



![](img/3742af1a256671c019090f4c341c86ff_63.png)

Okay， and so we have n minus R。

![](img/3742af1a256671c019090f4c341c86ff_65.png)

Let's do an example， well a couple other things to identify first， zero factorial。



![](img/3742af1a256671c019090f4c341c86ff_67.png)

RightWell， how do we incorporate zero factorial into a situation like that？ Well。

 we've defined that just kind of for convenience as one。



![](img/3742af1a256671c019090f4c341c86ff_69.png)

![](img/3742af1a256671c019090f4c341c86ff_70.png)

And of course， one factorial。

![](img/3742af1a256671c019090f4c341c86ff_72.png)

Is also one， okay， just so that we have those in our pocket。



![](img/3742af1a256671c019090f4c341c86ff_74.png)

So if we have the situation of P。

![](img/3742af1a256671c019090f4c341c86ff_76.png)

N times n， which basically means we're going to go and we're going to select n items。

 We're going to go all the way to the end， Right， Well， then that has n factorial。



![](img/3742af1a256671c019090f4c341c86ff_78.png)

Over n minus n factorial。

![](img/3742af1a256671c019090f4c341c86ff_80.png)

N factorial over 0 factorial， which I told you was one。 So that ends up being just。



![](img/3742af1a256671c019090f4c341c86ff_82.png)

In factorial。 So if we're going to exhaust the entire set of things we're choosing from。

 we would just use n factorial as the notation。

![](img/3742af1a256671c019090f4c341c86ff_84.png)

What's the probability， how many ways can we select nothing？



![](img/3742af1a256671c019090f4c341c86ff_86.png)

Well， intuitively， we shouldt know the answer to that。 Let's see if it checks out。 It's n factorial。



![](img/3742af1a256671c019090f4c341c86ff_88.png)

![](img/3742af1a256671c019090f4c341c86ff_89.png)

Divided by n minus0 factorial。

![](img/3742af1a256671c019090f4c341c86ff_91.png)

And so that ends up being n factorial over n factorial， which is one。

 so there's one way in which you can select nothing in the set。



![](img/3742af1a256671c019090f4c341c86ff_93.png)

So。

![](img/3742af1a256671c019090f4c341c86ff_95.png)

Let's do an example。How many？

![](img/3742af1a256671c019090f4c341c86ff_97.png)

Ways。Can10 people？

![](img/3742af1a256671c019090f4c341c86ff_99.png)

Be arranged。In a row。

![](img/3742af1a256671c019090f4c341c86ff_101.png)

Okay， how many people， how many ways can 10 people be arranged in the row。

 I'd like you to pause the video right now and try and solve that problem and then hit resume when you've done your solution ready to see mine。

😊。

![](img/3742af1a256671c019090f4c341c86ff_103.png)

![](img/3742af1a256671c019090f4c341c86ff_104.png)

I'm assuming you pause the video and so now we're going to continue so there are 10 people so there's 10 spots。

 there's one，2， three，4，5，67， eight，9，10 spots right so how many ways are there to select the first person well there's 10 people you can choose from？



![](img/3742af1a256671c019090f4c341c86ff_106.png)

![](img/3742af1a256671c019090f4c341c86ff_107.png)

![](img/3742af1a256671c019090f4c341c86ff_108.png)

Now that you've chosen 10， you have nine。

![](img/3742af1a256671c019090f4c341c86ff_110.png)

Then eight， then7。And we continue。

![](img/3742af1a256671c019090f4c341c86ff_112.png)

Right and so the way we would write that is by the generalized principle of count is 10 times 9 times8。

 et cetera， or just 10。

![](img/3742af1a256671c019090f4c341c86ff_114.png)

![](img/3742af1a256671c019090f4c341c86ff_115.png)

Factorial。ok。And that would be our。

![](img/3742af1a256671c019090f4c341c86ff_117.png)

Answer。Give you another example， What if we said that we are going to do an example and we're going to arrange 10 people but but so that。



![](img/3742af1a256671c019090f4c341c86ff_119.png)

![](img/3742af1a256671c019090f4c341c86ff_120.png)

A certain pair。

![](img/3742af1a256671c019090f4c341c86ff_122.png)

Are always together。

![](img/3742af1a256671c019090f4c341c86ff_124.png)

Sorry for my writing there so there's a certain pair are always together so let me generalize that a little bit。

 and I'm going to say that， you know A and B， they always have to be together so we can treat A and B two of these folks as a unit。



![](img/3742af1a256671c019090f4c341c86ff_126.png)

![](img/3742af1a256671c019090f4c341c86ff_127.png)

![](img/3742af1a256671c019090f4c341c86ff_128.png)

So if we've taken A and B， there are eight other people that we have to arrange。

 so if we treat this as a single unit， we essentially have nine factorial combinations。

 but we have to recognize that certain pair always together A and B is the same as B and A right that that's another option so that means that for every combination where A B is together there's also one of B A together and so that will be times。



![](img/3742af1a256671c019090f4c341c86ff_130.png)

![](img/3742af1a256671c019090f4c341c86ff_131.png)

![](img/3742af1a256671c019090f4c341c86ff_132.png)

![](img/3742af1a256671c019090f4c341c86ff_133.png)

![](img/3742af1a256671c019090f4c341c86ff_134.png)

![](img/3742af1a256671c019090f4c341c86ff_135.png)

Two， so the number of ways in which we can construct 10 people in a row so that a certain pair are always together becomes nine factorial times  two。

 and that becomes your answer。

![](img/3742af1a256671c019090f4c341c86ff_137.png)

![](img/3742af1a256671c019090f4c341c86ff_138.png)

![](img/3742af1a256671c019090f4c341c86ff_139.png)

Okay we'll give another example here。😊。

![](img/3742af1a256671c019090f4c341c86ff_141.png)

So that。

![](img/3742af1a256671c019090f4c341c86ff_143.png)

A certain pair。

![](img/3742af1a256671c019090f4c341c86ff_145.png)

R。Never。Together。

![](img/3742af1a256671c019090f4c341c86ff_147.png)

Now at this point， what I'd like you to do is pause the video and see if you can work out that problem and then hit resume when you're ready to see my solution。



![](img/3742af1a256671c019090f4c341c86ff_149.png)

![](img/3742af1a256671c019090f4c341c86ff_150.png)

Welcome back， I'm assuming you've paused the video and you've worked out this solution so when we look at this we've kind of we're going to use a little trick right we've kind of identified how you know how many ways can two people。

 a certain pair always be together and now we flip it and we say hey。

 we're going to do this so that a certain pair are never together。

 meaning what are the ways in which this does not happen。



![](img/3742af1a256671c019090f4c341c86ff_152.png)

![](img/3742af1a256671c019090f4c341c86ff_153.png)

![](img/3742af1a256671c019090f4c341c86ff_154.png)

![](img/3742af1a256671c019090f4c341c86ff_155.png)

![](img/3742af1a256671c019090f4c341c86ff_156.png)

Well， if we know that there are 10。

![](img/3742af1a256671c019090f4c341c86ff_158.png)

Factial ways in which 10 people can be arranged， and we're excluding nine factorial times 2。



![](img/3742af1a256671c019090f4c341c86ff_160.png)

![](img/3742af1a256671c019090f4c341c86ff_161.png)

Then our solution will be we need to take the total number of possibilities and subtract out what we're excluding right。

 so 10 factorial minus9 factorial times 2， that becomes our answer。



![](img/3742af1a256671c019090f4c341c86ff_163.png)

![](img/3742af1a256671c019090f4c341c86ff_164.png)

This is a little bit tricky， but it is a very important concept in statistics。

 What we're doing is we are taking。

![](img/3742af1a256671c019090f4c341c86ff_166.png)

![](img/3742af1a256671c019090f4c341c86ff_167.png)

The big pie of possibilities。 And in this example， and that's what we're saying， you know。

 we're describing here in this first example。 And the second one we're saying， hey。

 when a certain pair are together， that's that's a more restrictive condition。

 and that's some subset。

![](img/3742af1a256671c019090f4c341c86ff_169.png)

![](img/3742af1a256671c019090f4c341c86ff_170.png)

![](img/3742af1a256671c019090f4c341c86ff_171.png)

Inside of this circle。 So it's smaller than 10 factorial in this case。



![](img/3742af1a256671c019090f4c341c86ff_173.png)

When we're going to say a certain pair never together and you see that never。

 that exclusionary criteria， what we're basically doing is we're cutting this possibility out of the total set of options。



![](img/3742af1a256671c019090f4c341c86ff_175.png)

![](img/3742af1a256671c019090f4c341c86ff_176.png)

![](img/3742af1a256671c019090f4c341c86ff_177.png)

And the way we end up doing that is if this is 10 factorial and this is9 factorial times2。

 then when we do 10 factorial minus9 factorial times 2， we're leaving ourselves this unshaded region。

 which is what we're interested in and you'll see that general type of subtraction going on in a lot of different problems in statistics。



![](img/3742af1a256671c019090f4c341c86ff_179.png)

![](img/3742af1a256671c019090f4c341c86ff_180.png)

![](img/3742af1a256671c019090f4c341c86ff_181.png)

All right， let's do another example。

![](img/3742af1a256671c019090f4c341c86ff_183.png)

In this example， we're going to say that we want to arrange seven women。



![](img/3742af1a256671c019090f4c341c86ff_185.png)

And。

![](img/3742af1a256671c019090f4c341c86ff_187.png)

3 men。In a row。

![](img/3742af1a256671c019090f4c341c86ff_189.png)

Arranged。In a row。

![](img/3742af1a256671c019090f4c341c86ff_191.png)

嗯。How many ways can we do that Well， we've kind of already answered that。 We just said 10 people。

 so we know that the total number possible here is 10 factorial because we just did that problem。



![](img/3742af1a256671c019090f4c341c86ff_193.png)

![](img/3742af1a256671c019090f4c341c86ff_194.png)

Okay。

![](img/3742af1a256671c019090f4c341c86ff_196.png)

If we said such that。3 men。

![](img/3742af1a256671c019090f4c341c86ff_198.png)

Are always。

![](img/3742af1a256671c019090f4c341c86ff_200.png)

Together。Okay。

![](img/3742af1a256671c019090f4c341c86ff_202.png)

I'd like you to pause the video and work out that problem and then hit resume when you're ready to see the solution。



![](img/3742af1a256671c019090f4c341c86ff_204.png)

I'm assuming you've paused the video and you've worked this out。

 This is exactly the same as the problem we just did。 So we have three men。



![](img/3742af1a256671c019090f4c341c86ff_206.png)

![](img/3742af1a256671c019090f4c341c86ff_207.png)

Are always together。And so we can treat that as one unit。

 and then we have plus seven women so we have。

![](img/3742af1a256671c019090f4c341c86ff_209.png)

8 factorial combinations。 But how many ways can we order the three different men？



![](img/3742af1a256671c019090f4c341c86ff_211.png)

![](img/3742af1a256671c019090f4c341c86ff_212.png)

Okay， so the three different men is very similar to the first problem， right。

 How many ways can you arrange 10 people was 10 factorial。

 How many ways can you arrange three people？ Well， that is。



![](img/3742af1a256671c019090f4c341c86ff_214.png)

![](img/3742af1a256671c019090f4c341c86ff_215.png)

Three factorial。

![](img/3742af1a256671c019090f4c341c86ff_217.png)

Okay， so then this becomes our。Answer。

![](img/3742af1a256671c019090f4c341c86ff_219.png)

What if we said then？Such that。

![](img/3742af1a256671c019090f4c341c86ff_221.png)

Three men。A never。

![](img/3742af1a256671c019090f4c341c86ff_223.png)

Together。Id like you to pause the video， work out the solution to that problem。

 and then hit resume when you're ready。

![](img/3742af1a256671c019090f4c341c86ff_225.png)

Welcome back I'm assuming you've paused the video， worked out this problem now this is very similar to the one we just did before right we said that there are 10 factorial total possibilities and the ones that we are excluding is8 factorial times three factorial and this then becomes our answer。



![](img/3742af1a256671c019090f4c341c86ff_227.png)

![](img/3742af1a256671c019090f4c341c86ff_228.png)

![](img/3742af1a256671c019090f4c341c86ff_229.png)

![](img/3742af1a256671c019090f4c341c86ff_230.png)

![](img/3742af1a256671c019090f4c341c86ff_231.png)

We'll change it now and say。

![](img/3742af1a256671c019090f4c341c86ff_233.png)

Example， and say。So that。

![](img/3742af1a256671c019090f4c341c86ff_235.png)

No。Two men。Are together。

![](img/3742af1a256671c019090f4c341c86ff_237.png)

Okay，' changing it up a little bit。

![](img/3742af1a256671c019090f4c341c86ff_239.png)

So in this case， we're going to have no two men together， we're going to have woman one。



![](img/3742af1a256671c019090f4c341c86ff_241.png)

Woman two， woman three， woman， four， woman five。

![](img/3742af1a256671c019090f4c341c86ff_243.png)

six。Seven， and we have these potential spaces。

![](img/3742af1a256671c019090f4c341c86ff_245.png)

That occur。That the men。Can occupy because we can't have any two men together。

 So how many places do we have between， you know， in in this scenario， Well。

 you'll find that we have8， right， I know there's 7 women because， you know， if you have one， two。

 right， you have the two spaces on either end。 So right， there are  eight spaces。



![](img/3742af1a256671c019090f4c341c86ff_247.png)

![](img/3742af1a256671c019090f4c341c86ff_248.png)

![](img/3742af1a256671c019090f4c341c86ff_249.png)

![](img/3742af1a256671c019090f4c341c86ff_250.png)

![](img/3742af1a256671c019090f4c341c86ff_251.png)

For the men in this situation。Okay， so if there's eight spaces。

 then the ways in which we can select men to fill these spaces is a permutation of eight spaces and we have to fit in three men right so we recall the the number of places here are then going to be eight。



![](img/3742af1a256671c019090f4c341c86ff_253.png)

![](img/3742af1a256671c019090f4c341c86ff_254.png)

![](img/3742af1a256671c019090f4c341c86ff_255.png)

Factorial。Over。8ight minus3。

![](img/3742af1a256671c019090f4c341c86ff_257.png)

Factial okay， which is and then there are how many ways can we arrange the seven women in this situation。

 Well we know that from the problems we are just working is。



![](img/3742af1a256671c019090f4c341c86ff_259.png)

![](img/3742af1a256671c019090f4c341c86ff_260.png)

Seven factorial right that we have。So we end up having this as。



![](img/3742af1a256671c019090f4c341c86ff_262.png)

Or。

![](img/3742af1a256671c019090f4c341c86ff_264.png)

Answer right， seven factorial times 8 factorial over 8 minus3 factorial。



![](img/3742af1a256671c019090f4c341c86ff_266.png)

Let's look at another example。😊。

![](img/3742af1a256671c019090f4c341c86ff_268.png)

How many。Wes。Can the English alphabet？

![](img/3742af1a256671c019090f4c341c86ff_270.png)

Alphabet。Be arranged。

![](img/3742af1a256671c019090f4c341c86ff_272.png)

In a row。Without repetition。So that。

![](img/3742af1a256671c019090f4c341c86ff_274.png)

There is。Exactly。

![](img/3742af1a256671c019090f4c341c86ff_276.png)

5 letters。

![](img/3742af1a256671c019090f4c341c86ff_278.png)

Between。A and B。

![](img/3742af1a256671c019090f4c341c86ff_280.png)

5 letters between A and B。Okay。

![](img/3742af1a256671c019090f4c341c86ff_282.png)

So in solving this problem， this is a little bit more involved。

 you can feel free to pause the video if you're feeling like you have this down and you understand it。

 if you can do this problem， you're definitely on your path to success。

 but if you want to follow along with me， that's fine。



![](img/3742af1a256671c019090f4c341c86ff_284.png)

![](img/3742af1a256671c019090f4c341c86ff_285.png)

![](img/3742af1a256671c019090f4c341c86ff_286.png)

Okay， I'm going to give you some options for this problem so option A。



![](img/3742af1a256671c019090f4c341c86ff_288.png)

![](img/3742af1a256671c019090f4c341c86ff_289.png)

Is the answer could be the permutation of 24， chooseose 5。Times。2y。Factorial。

Let me give you four choices here。Option B is it's the permutation of。24。five。



![](img/3742af1a256671c019090f4c341c86ff_291.png)

Times。19 factorial。It could be the。Permutation。24。Choose 5。😔，Times，9 factorial。Times。2 factorial。

Or the permutation of 24，5。Times。20 factorial times two factorial。

 So if you'd like to pause the video or make a guess as to which of those they are。

 then hit resume and I will work out the solution。

![](img/3742af1a256671c019090f4c341c86ff_293.png)

![](img/3742af1a256671c019090f4c341c86ff_294.png)

![](img/3742af1a256671c019090f4c341c86ff_295.png)

So welcome back， I'm assuming you have selected one of these answers and you know you have a one in four possibility of being correct anyway right so maybe I could have given you that as a problem Okay。

 for this problem we have a and we have exactly five spaces。



![](img/3742af1a256671c019090f4c341c86ff_297.png)

![](img/3742af1a256671c019090f4c341c86ff_298.png)

![](img/3742af1a256671c019090f4c341c86ff_299.png)

Between A and B right and we can treat this as one unit and how many options do we have left Well。

 if we've selected these， there's seven choices， A and B and then five in between。

 so that leaves 19 left So we have 20 factorial ways of arranging these units well now let's look in here in here。



![](img/3742af1a256671c019090f4c341c86ff_301.png)

![](img/3742af1a256671c019090f4c341c86ff_302.png)

![](img/3742af1a256671c019090f4c341c86ff_303.png)

![](img/3742af1a256671c019090f4c341c86ff_304.png)

![](img/3742af1a256671c019090f4c341c86ff_305.png)

Right， we have 24 ways right， because we've taken A and B out of the 26 letters。

 so we have a permutation of。

![](img/3742af1a256671c019090f4c341c86ff_307.png)

![](img/3742af1a256671c019090f4c341c86ff_308.png)

24 possibilities and five ways to choose them or arrange them here in the middle。 So like before。

 when we had just A and B together and we had A and B or B And A， there were two possibilities。 Well。

 now there's 24。

![](img/3742af1a256671c019090f4c341c86ff_310.png)

![](img/3742af1a256671c019090f4c341c86ff_311.png)

![](img/3742af1a256671c019090f4c341c86ff_312.png)

Permutation of 24 and five ways of arranging five letters in the middle。



![](img/3742af1a256671c019090f4c341c86ff_314.png)

And so we would have 20 factorial。

![](img/3742af1a256671c019090f4c341c86ff_316.png)

Right， times。The permutation of 24， choose5。

![](img/3742af1a256671c019090f4c341c86ff_318.png)

And there's one thing I'm missing， which is A and B is the same as B and A。

 so I have to multiply that。

![](img/3742af1a256671c019090f4c341c86ff_320.png)

By2。So you'll see that D here。

![](img/3742af1a256671c019090f4c341c86ff_322.png)

Is the correct answer？

![](img/3742af1a256671c019090f4c341c86ff_324.png)