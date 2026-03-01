# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p06 5_组合数学.zh_en -BV1r483zbEzN_p6-

![](img/0f214ce75d73a1cdc200c101262f879e_0.png)

We're now going to talk about combinations， combinations。



![](img/0f214ce75d73a1cdc200c101262f879e_2.png)

Now in permutations， the order mattered， in combination， the order does not matter。

 so in this situation， A and B， B， and a same thing because the order does not matter like we saw before。

So our notation for combinations， I'm going to use C of n choose R that n choose R means that of n possible options。

 I'm going to randomly pick R of those options。 How many ways are there to do that Another way you might see this written is。



![](img/0f214ce75d73a1cdc200c101262f879e_4.png)

![](img/0f214ce75d73a1cdc200c101262f879e_5.png)

![](img/0f214ce75d73a1cdc200c101262f879e_6.png)

![](img/0f214ce75d73a1cdc200c101262f879e_7.png)

![](img/0f214ce75d73a1cdc200c101262f879e_8.png)

N choose R， they're stacked on top of each other， that means the same thing。



![](img/0f214ce75d73a1cdc200c101262f879e_10.png)

And then the formula for N choose R is。

![](img/0f214ce75d73a1cdc200c101262f879e_12.png)

N factorial。Over。N minus R factorial。

![](img/0f214ce75d73a1cdc200c101262f879e_14.png)

R factorial， so that becomes the formula for n choose R。



![](img/0f214ce75d73a1cdc200c101262f879e_16.png)

![](img/0f214ce75d73a1cdc200c101262f879e_17.png)

So。We's start with an example。How many ways？

![](img/0f214ce75d73a1cdc200c101262f879e_19.png)

Right， how many ways？

![](img/0f214ce75d73a1cdc200c101262f879e_21.png)

Can five people。Be selected。

![](img/0f214ce75d73a1cdc200c101262f879e_23.png)

From。10 people。Okay， how many ways can five people be selected from a 10 person group？



![](img/0f214ce75d73a1cdc200c101262f879e_25.png)

Well， using our formula， we would have 10 factorial。



![](img/0f214ce75d73a1cdc200c101262f879e_27.png)

Right over 10 minus。5 factorial times 5 factorial。 And then this becomes the answer。

 We can simplify this if we wish。 so you can look and say， if I have something like this。

10 factorial， we recognize that's going to be 10。

![](img/0f214ce75d73a1cdc200c101262f879e_29.png)

![](img/0f214ce75d73a1cdc200c101262f879e_30.png)

Times 9， times 8， times 7， times 6 times5 factorial。



![](img/0f214ce75d73a1cdc200c101262f879e_32.png)

![](img/0f214ce75d73a1cdc200c101262f879e_33.png)

And I can recognize that 10-5 is just 5 factorial， and 5 factorial is going to be 5 times 4 times 3 times 2 times 1。

 And then you can start seeing how things can cancel。

 So this5 factorial cancels with the5 factorial up here。 That's why I stopped。



![](img/0f214ce75d73a1cdc200c101262f879e_35.png)

![](img/0f214ce75d73a1cdc200c101262f879e_36.png)

![](img/0f214ce75d73a1cdc200c101262f879e_37.png)

![](img/0f214ce75d73a1cdc200c101262f879e_38.png)

Okay， you can look and see things like， hey， the two goes into this three times。

 the three goes into the three one time。

![](img/0f214ce75d73a1cdc200c101262f879e_40.png)

You can see that the four goes into the eight twice。

 the five goes into the 10 twice right so now that I've canceled everything out in the denominator that kind of leaves me with two times 2。

 which is four。

![](img/0f214ce75d73a1cdc200c101262f879e_42.png)

![](img/0f214ce75d73a1cdc200c101262f879e_43.png)

And 9 times 7 is 63， and then if you work that out。

 you can get 6 times 4 is 240 and 12 is 252 right so you end up with 252 and you can simplify。



![](img/0f214ce75d73a1cdc200c101262f879e_45.png)

![](img/0f214ce75d73a1cdc200c101262f879e_46.png)

![](img/0f214ce75d73a1cdc200c101262f879e_47.png)

For purposes of our class， I'm mainly interested that you can describe it as a factorial you probably code something up a little bit later to do that what we're attempting to do here though is just show you that when you actually work these factorial problems out that there is some canceling that can be done if you're clever about it。



![](img/0f214ce75d73a1cdc200c101262f879e_49.png)

![](img/0f214ce75d73a1cdc200c101262f879e_50.png)

![](img/0f214ce75d73a1cdc200c101262f879e_51.png)

![](img/0f214ce75d73a1cdc200c101262f879e_52.png)

Okay。嗯。So。

![](img/0f214ce75d73a1cdc200c101262f879e_54.png)

How many ways how many ways？Can。

![](img/0f214ce75d73a1cdc200c101262f879e_56.png)

5 people。

![](img/0f214ce75d73a1cdc200c101262f879e_58.png)

Be selected from a group of。

![](img/0f214ce75d73a1cdc200c101262f879e_60.png)

seven。Men。

![](img/0f214ce75d73a1cdc200c101262f879e_62.png)

And six women。So what I'd like you to do is pause the video right here and work out that solution and then hit play when you're ready to resume。



![](img/0f214ce75d73a1cdc200c101262f879e_64.png)

Welcome back。 So this problem is really no different than the one we just did。

 We are saying the combination of 13 people， and I'm going to choose five of them。

 which ends up being 13 factorial over。

![](img/0f214ce75d73a1cdc200c101262f879e_66.png)

![](img/0f214ce75d73a1cdc200c101262f879e_67.png)

13-5 factorial。

![](img/0f214ce75d73a1cdc200c101262f879e_69.png)

F factorial and I would like you to simplify it like this。



![](img/0f214ce75d73a1cdc200c101262f879e_71.png)

13 factorial over 13 minus5 is going to be 8 factorial5 factorial but that's about the most simplification you need to do for me。



![](img/0f214ce75d73a1cdc200c101262f879e_73.png)

![](img/0f214ce75d73a1cdc200c101262f879e_74.png)

Okay。So。

![](img/0f214ce75d73a1cdc200c101262f879e_76.png)

Now， if we're going to。

![](img/0f214ce75d73a1cdc200c101262f879e_78.png)

Extend this a little bit。Right。How many ways are there to select three men？



![](img/0f214ce75d73a1cdc200c101262f879e_80.png)

![](img/0f214ce75d73a1cdc200c101262f879e_81.png)

And。To women。From this group and you'd say why would we do that well let's say that there's this group of seven men and six women and so you're going to form a five person committee and you want to make sure that the five first person committee kind of represents the group so you decide that there needs to be three men and two women on the group how many ways are there to form the committee？



![](img/0f214ce75d73a1cdc200c101262f879e_83.png)

![](img/0f214ce75d73a1cdc200c101262f879e_84.png)

![](img/0f214ce75d73a1cdc200c101262f879e_85.png)

![](img/0f214ce75d73a1cdc200c101262f879e_86.png)

Okay， so how many ways are there to select three men？



![](img/0f214ce75d73a1cdc200c101262f879e_88.png)

From the group， I'm going to pause there and I'm going to say。

 why don't you try and work out this problem and then hit play when you're ready to continue。



![](img/0f214ce75d73a1cdc200c101262f879e_90.png)

Welcome back， So how do you select three men from how many men from seven men， so we have seven。

 choose three。

![](img/0f214ce75d73a1cdc200c101262f879e_92.png)

RightThat's how many ways we can select three men and we how many ways can we select two women well we have six。



![](img/0f214ce75d73a1cdc200c101262f879e_94.png)

Choose two women that we can choose。

![](img/0f214ce75d73a1cdc200c101262f879e_96.png)

Okay， but it's also possible that you can have， no， that's it。 that's all the possibilities， right。

 so we have。

![](img/0f214ce75d73a1cdc200c101262f879e_98.png)

![](img/0f214ce75d73a1cdc200c101262f879e_99.png)

Those multiplied， which is going to end up being seven。Over 7 minus3 factorial。



![](img/0f214ce75d73a1cdc200c101262f879e_101.png)

Times 3 factorial， and that will be multiplied by6 factorial。Over 6 minus3。Factorial over3 factorial。

 right， which I would like you to simplify as7 factorial over four factorial times 3 factorial。



![](img/0f214ce75d73a1cdc200c101262f879e_103.png)

![](img/0f214ce75d73a1cdc200c101262f879e_104.png)

Times 6 factorial。

![](img/0f214ce75d73a1cdc200c101262f879e_106.png)

Over three factorial， three factorial。

![](img/0f214ce75d73a1cdc200c101262f879e_108.png)

Okay so then this becomes your answer。Okay。

![](img/0f214ce75d73a1cdc200c101262f879e_110.png)

Let's do another problem。 How many ways can a。

![](img/0f214ce75d73a1cdc200c101262f879e_112.png)

Can you make a five member committee？

![](img/0f214ce75d73a1cdc200c101262f879e_114.png)

Okay， five member committee such that you have at least。



![](img/0f214ce75d73a1cdc200c101262f879e_116.png)

Two women。

![](img/0f214ce75d73a1cdc200c101262f879e_118.png)

So now I just want to make sure that I have at least two women on the committee so you know for that I get more than two women。

 but I have to have at least two women on the committee so let's look at the women right and then that's my hint for you and then I want you to pause the video and try and work out this problem and then hit resume when you're ready to continue。



![](img/0f214ce75d73a1cdc200c101262f879e_120.png)

![](img/0f214ce75d73a1cdc200c101262f879e_121.png)

![](img/0f214ce75d73a1cdc200c101262f879e_122.png)

![](img/0f214ce75d73a1cdc200c101262f879e_123.png)

All right， welcome back so how many ways， as I said。

 are there to choose the women so if we start with six women and we pick two right well then we have to say how many ways then are there to select from the remaining men so we are going to select three from the remaining men。



![](img/0f214ce75d73a1cdc200c101262f879e_125.png)

![](img/0f214ce75d73a1cdc200c101262f879e_126.png)

![](img/0f214ce75d73a1cdc200c101262f879e_127.png)

![](img/0f214ce75d73a1cdc200c101262f879e_128.png)

We also have these possibilities of selecting three women right and when you select three women。

 then you still have to select two remaining men。

![](img/0f214ce75d73a1cdc200c101262f879e_130.png)

![](img/0f214ce75d73a1cdc200c101262f879e_131.png)

It's still possible to select four women， and then you have one remaining man。



![](img/0f214ce75d73a1cdc200c101262f879e_133.png)

And it's also possible to select all five from the women in which case you have no remaining men to select from right。



![](img/0f214ce75d73a1cdc200c101262f879e_135.png)

![](img/0f214ce75d73a1cdc200c101262f879e_136.png)

You know， you can simplify that and then you know with the equation。

 and then this becomes your answer， right？

![](img/0f214ce75d73a1cdc200c101262f879e_138.png)

![](img/0f214ce75d73a1cdc200c101262f879e_139.png)

![](img/0f214ce75d73a1cdc200c101262f879e_140.png)

All right， let's do another example。

![](img/0f214ce75d73a1cdc200c101262f879e_142.png)

At most。

![](img/0f214ce75d73a1cdc200c101262f879e_144.png)

One woman。Okay， most one woman， so this means that you know you can only have one woman or zero women nothing in between right or nothing more than one woman。

 so what I would like you to do is pause this video and try and work out this problem。



![](img/0f214ce75d73a1cdc200c101262f879e_146.png)

![](img/0f214ce75d73a1cdc200c101262f879e_147.png)

![](img/0f214ce75d73a1cdc200c101262f879e_148.png)

All right， welcome back， so when we're looking at most one woman。



![](img/0f214ce75d73a1cdc200c101262f879e_150.png)

![](img/0f214ce75d73a1cdc200c101262f879e_151.png)

Well， we have。This is our problem where we have 13 people and we have five ways we can choose from the 13 people that is the overall population and then what I'm going to subtract is the situations that I can't have right？



![](img/0f214ce75d73a1cdc200c101262f879e_153.png)

![](img/0f214ce75d73a1cdc200c101262f879e_154.png)

![](img/0f214ce75d73a1cdc200c101262f879e_155.png)

![](img/0f214ce75d73a1cdc200c101262f879e_156.png)

If I selected。All the people from the men。Right。

![](img/0f214ce75d73a1cdc200c101262f879e_158.png)

60。

![](img/0f214ce75d73a1cdc200c101262f879e_160.png)

um。And。

![](img/0f214ce75d73a1cdc200c101262f879e_162.png)

I selected four people from the men and one from the women。



![](img/0f214ce75d73a1cdc200c101262f879e_164.png)

Then this is my condition of no women。

![](img/0f214ce75d73a1cdc200c101262f879e_166.png)

This is my condition of one woman， and so this is how many people I have total。

 so this means that at most one woman could be selected from the group。



![](img/0f214ce75d73a1cdc200c101262f879e_168.png)

![](img/0f214ce75d73a1cdc200c101262f879e_169.png)

![](img/0f214ce75d73a1cdc200c101262f879e_170.png)

All right， let'm me to give you another example。

![](img/0f214ce75d73a1cdc200c101262f879e_172.png)

So for this example， we are going to have an eight letter。



![](img/0f214ce75d73a1cdc200c101262f879e_174.png)

wordord。And in that eight letter word， there will be five consonants。



![](img/0f214ce75d73a1cdc200c101262f879e_176.png)

![](img/0f214ce75d73a1cdc200c101262f879e_177.png)

And three。Vowels。

![](img/0f214ce75d73a1cdc200c101262f879e_179.png)

In this word。How many。

![](img/0f214ce75d73a1cdc200c101262f879e_181.png)

Words。

![](img/0f214ce75d73a1cdc200c101262f879e_183.png)

Can be formed。How many words can be formed， and I'm going to give you some choices。



![](img/0f214ce75d73a1cdc200c101262f879e_185.png)

Okay， so option A。

![](img/0f214ce75d73a1cdc200c101262f879e_187.png)

Is that we will have 21， choose  five。

![](img/0f214ce75d73a1cdc200c101262f879e_189.png)

Times。

![](img/0f214ce75d73a1cdc200c101262f879e_191.png)

five。Choose3。Option B is that we will have 21， choose5。



![](img/0f214ce75d73a1cdc200c101262f879e_193.png)

![](img/0f214ce75d73a1cdc200c101262f879e_194.png)

Times。five。Choose3。😔。

![](img/0f214ce75d73a1cdc200c101262f879e_196.png)

Times 8 factorial。

![](img/0f214ce75d73a1cdc200c101262f879e_198.png)

Permutation。Of。21。Cose5。😔，Times the permutation。

![](img/0f214ce75d73a1cdc200c101262f879e_200.png)

Of。five。And three。

![](img/0f214ce75d73a1cdc200c101262f879e_202.png)

So， three。And answer D。

![](img/0f214ce75d73a1cdc200c101262f879e_204.png)

Is none。Right， none of the above， none。

![](img/0f214ce75d73a1cdc200c101262f879e_206.png)

Of。Above。Okay， so I would like you to pause the video and try and work through this problem or randomly pick an answer you have like。



![](img/0f214ce75d73a1cdc200c101262f879e_208.png)

What probability of being correct？

![](img/0f214ce75d73a1cdc200c101262f879e_210.png)

All right， welcome back so in order to work through this problem， right。

 how many words can be formed， Well， how many consonants can we choose right Well we have。



![](img/0f214ce75d73a1cdc200c101262f879e_212.png)

![](img/0f214ce75d73a1cdc200c101262f879e_213.png)

OfIf there's 26 letters in the alphabet and there's five consonants。

 there are 21 choose five different consonants that we can select。



![](img/0f214ce75d73a1cdc200c101262f879e_215.png)

This is for the。

![](img/0f214ce75d73a1cdc200c101262f879e_217.png)

Consonance。So we have that and then for each of those we have times。



![](img/0f214ce75d73a1cdc200c101262f879e_219.png)

F， choose three different vowels。

![](img/0f214ce75d73a1cdc200c101262f879e_221.png)

![](img/0f214ce75d73a1cdc200c101262f879e_222.png)

And then we have how many units that we can arrange or permute in whatever way we like。 Well。

 we have 8。 So we have to do 8 factorial different permutations。 So our answer is answer B。

 I did not mean to line through the。

![](img/0f214ce75d73a1cdc200c101262f879e_224.png)

![](img/0f214ce75d73a1cdc200c101262f879e_225.png)

![](img/0f214ce75d73a1cdc200c101262f879e_226.png)

Three there， sorry for that。Okay。

![](img/0f214ce75d73a1cdc200c101262f879e_228.png)

How many。Words。

![](img/0f214ce75d73a1cdc200c101262f879e_230.png)

Start。With A。

![](img/0f214ce75d73a1cdc200c101262f879e_232.png)

With the letter A， I'll give you some more choices for that over here。



![](img/0f214ce75d73a1cdc200c101262f879e_234.png)

A answer A could be 21， choose 5。

![](img/0f214ce75d73a1cdc200c101262f879e_236.png)

Times。4our。Cose to。😔，Time 7。H。Excuse me， Victoriactoria。Be。We have21 choose 5。Times。



![](img/0f214ce75d73a1cdc200c101262f879e_238.png)

For choose 2。Times 8 factorial。

![](img/0f214ce75d73a1cdc200c101262f879e_240.png)

We have 21， choose 5。Times。5， choose，3。

![](img/0f214ce75d73a1cdc200c101262f879e_242.png)

Times 8 factorial or we have。

![](img/0f214ce75d73a1cdc200c101262f879e_244.png)

21， choose 5。5， choose3 times7 factorial are your answers okay？



![](img/0f214ce75d73a1cdc200c101262f879e_246.png)

So why don't you pause for a moment and work through the problem and see how you do and then hit resume when you're ready to continue。



![](img/0f214ce75d73a1cdc200c101262f879e_248.png)

![](img/0f214ce75d73a1cdc200c101262f879e_249.png)

All right， welcome back。

![](img/0f214ce75d73a1cdc200c101262f879e_251.png)

So how many words start with the letter A？

![](img/0f214ce75d73a1cdc200c101262f879e_253.png)

We have。How many consonants to choose from We did that before， right。

 we have 21 choose five different consonants。

![](img/0f214ce75d73a1cdc200c101262f879e_255.png)

![](img/0f214ce75d73a1cdc200c101262f879e_256.png)

We have how many vowels in which to select from Well， in this case。

 we know one of the choices is going to begin with an a。 So really。

 we're selecting between the four remaining vowels， the other two vowels and the problem right。

 so our vowels now change to。

![](img/0f214ce75d73a1cdc200c101262f879e_258.png)

![](img/0f214ce75d73a1cdc200c101262f879e_259.png)

![](img/0f214ce75d73a1cdc200c101262f879e_260.png)

![](img/0f214ce75d73a1cdc200c101262f879e_261.png)

For choose 2 and because we know it's starting with an a。

 we're really only arranging the other seven letters， this is a circular permutation。

 so that is going to be eight letters n minus1 factorial or7 factorial in this particular case right so then that becomes our solution so where is that that is 21。

5，4，2 times 7 factorial so here we go for our answer answer a。



![](img/0f214ce75d73a1cdc200c101262f879e_263.png)

![](img/0f214ce75d73a1cdc200c101262f879e_264.png)

![](img/0f214ce75d73a1cdc200c101262f879e_265.png)

![](img/0f214ce75d73a1cdc200c101262f879e_266.png)

![](img/0f214ce75d73a1cdc200c101262f879e_267.png)

Okay。

![](img/0f214ce75d73a1cdc200c101262f879e_269.png)

嗯。So another example we will do here is。

![](img/0f214ce75d73a1cdc200c101262f879e_271.png)

Okay， there are。N couples。

![](img/0f214ce75d73a1cdc200c101262f879e_273.png)

Invited。To a party。

![](img/0f214ce75d73a1cdc200c101262f879e_275.png)

Okay， and couples invited a party with a condition。



![](img/0f214ce75d73a1cdc200c101262f879e_277.png)

And that condition is that every husband has to be accompanied by his wife。



![](img/0f214ce75d73a1cdc200c101262f879e_279.png)

![](img/0f214ce75d73a1cdc200c101262f879e_280.png)

Every。Husband。

![](img/0f214ce75d73a1cdc200c101262f879e_282.png)

Must be。

![](img/0f214ce75d73a1cdc200c101262f879e_284.png)

Accompanied。By wife。

![](img/0f214ce75d73a1cdc200c101262f879e_286.png)

Every husband must be accompanied by his wife。However。



![](img/0f214ce75d73a1cdc200c101262f879e_288.png)

A wife。A wife need not。

![](img/0f214ce75d73a1cdc200c101262f879e_290.png)

Be accompanied。

![](img/0f214ce75d73a1cdc200c101262f879e_292.png)

Bye。huusband。

![](img/0f214ce75d73a1cdc200c101262f879e_294.png)

Okay， Nina。How many。

![](img/0f214ce75d73a1cdc200c101262f879e_296.png)

Possible。Gatherings。

![](img/0f214ce75d73a1cdc200c101262f879e_298.png)

How many possible gatherings are there， and I'm going to give you some options。



![](img/0f214ce75d73a1cdc200c101262f879e_300.png)

Option。A。

![](img/0f214ce75d73a1cdc200c101262f879e_302.png)

Is the answer is。

![](img/0f214ce75d73a1cdc200c101262f879e_304.png)

2 n。Choose n。Times。😔，Two to the end。Option B is。3 to the n。Option C。Is2 n factorial？



![](img/0f214ce75d73a1cdc200c101262f879e_306.png)

Over。Two to the end。And option D。Is2 n， choose n。

![](img/0f214ce75d73a1cdc200c101262f879e_308.png)

Now this is a bit of a reach problem， so I would like you to pause the video and give it a shot。

 but if you get too frustrated， then hit resume on the video。



![](img/0f214ce75d73a1cdc200c101262f879e_310.png)

![](img/0f214ce75d73a1cdc200c101262f879e_311.png)

All right， welcome back， so let's look at what are the three cases that you have for outcomes right。

 so we have three cases。

![](img/0f214ce75d73a1cdc200c101262f879e_313.png)

![](img/0f214ce75d73a1cdc200c101262f879e_314.png)

That we can have for a couple right， so case number one is that you have a husband。



![](img/0f214ce75d73a1cdc200c101262f879e_316.png)

![](img/0f214ce75d73a1cdc200c101262f879e_317.png)

And wife attend。

![](img/0f214ce75d73a1cdc200c101262f879e_319.png)

Case number。Two is that you have the wife only attend in case number three is that none。



![](img/0f214ce75d73a1cdc200c101262f879e_321.png)

Attend。

![](img/0f214ce75d73a1cdc200c101262f879e_323.png)

Right， none attend， so for a given husband and wife combo。

 there are three choices for how they may or may not attend the party。

 either they both go together just the life or no one goes。



![](img/0f214ce75d73a1cdc200c101262f879e_325.png)

So if you agree with that。You have three possible options and you have n couples， so you have three。



![](img/0f214ce75d73a1cdc200c101262f879e_327.png)

![](img/0f214ce75d73a1cdc200c101262f879e_328.png)

Outcomes。Times 3 outcomes， times  three outcomes， this is like flipping a coin only instead of there being two choices。

 there are three choices， so we have three to the n possibilities， right？



![](img/0f214ce75d73a1cdc200c101262f879e_330.png)

![](img/0f214ce75d73a1cdc200c101262f879e_331.png)

Which is answer。

![](img/0f214ce75d73a1cdc200c101262f879e_333.png)

B， answer B。

![](img/0f214ce75d73a1cdc200c101262f879e_335.png)