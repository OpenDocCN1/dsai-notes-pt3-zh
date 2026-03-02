# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p07 6_阶乘运算与恒等式.zh_en -BV1r483zbEzN_p7-

。

![](img/3a32161c95003c67936811c0ea0446aa_1.png)

All， we're going to switch gears a little bit。 We're going to do a little bit more work with some some factorial。

 So what I'm going to do is I'm going to introduce to you a。



![](img/3a32161c95003c67936811c0ea0446aa_3.png)

![](img/3a32161c95003c67936811c0ea0446aa_4.png)

An identity。

![](img/3a32161c95003c67936811c0ea0446aa_6.png)

That is very useful when you're working with factorials。 And so the identity says that N。



![](img/3a32161c95003c67936811c0ea0446aa_8.png)

Choose R。

![](img/3a32161c95003c67936811c0ea0446aa_10.png)

Is equal to。N minus1。Choose R。

![](img/3a32161c95003c67936811c0ea0446aa_12.png)

Plus。N minus-1。

![](img/3a32161c95003c67936811c0ea0446aa_14.png)

Choose。😔，R -1。And I believe that's Pascal's identity。



![](img/3a32161c95003c67936811c0ea0446aa_16.png)

What I'm going to do is I'm just going to basically prove that to you or analytically derive it。

 so a lot of times people use that as an exercise， but I guess I'm nice， it's a weakness that I have。

😊。

![](img/3a32161c95003c67936811c0ea0446aa_18.png)

![](img/3a32161c95003c67936811c0ea0446aa_19.png)

![](img/3a32161c95003c67936811c0ea0446aa_20.png)

So the way we're going to proceed with Pascal's identity is we're going to write out the right side of the equation as factorials。

 and then I'm going to derive the left side of the equation。

 So when we write out the right side of the equation， we're going to have n minus-1。



![](img/3a32161c95003c67936811c0ea0446aa_22.png)

![](img/3a32161c95003c67936811c0ea0446aa_23.png)

Factorial。Over， we're going to have n minus1 minus R。



![](img/3a32161c95003c67936811c0ea0446aa_25.png)

Factorial over R factorial。And then we're going to add this equation will be n minus1 factorial over。



![](img/3a32161c95003c67936811c0ea0446aa_27.png)

N minus1 minus R and a minus a minus1 is a plus1。

![](img/3a32161c95003c67936811c0ea0446aa_29.png)

Factctorial。R minus1 factorial。

![](img/3a32161c95003c67936811c0ea0446aa_31.png)

And now you'll notice that that negative one and that plus one they cancel out so that they're eliminated。



![](img/3a32161c95003c67936811c0ea0446aa_33.png)

Well， in order to combine both of these， what I need to do is I need to get a common denominator。

 and so what I'm going to show you is the common denominator is going to be n minus1。



![](img/3a32161c95003c67936811c0ea0446aa_35.png)

![](img/3a32161c95003c67936811c0ea0446aa_36.png)

Factial， I'm going to multiply both top and bottom by n minus R。



![](img/3a32161c95003c67936811c0ea0446aa_38.png)

![](img/3a32161c95003c67936811c0ea0446aa_39.png)

And then on the bottom here， I have n minus1。

![](img/3a32161c95003c67936811c0ea0446aa_41.png)

um。

![](img/3a32161c95003c67936811c0ea0446aa_43.png)

Pinus R。Factial are factorial， and I'm going to have n minus R。



![](img/3a32161c95003c67936811c0ea0446aa_45.png)

On the bottom。

![](img/3a32161c95003c67936811c0ea0446aa_47.png)

On this term， what I'm going to do is I'm going to multiply the top and the bottom by R。

 So I'll have n -1 factorial times。

![](img/3a32161c95003c67936811c0ea0446aa_49.png)

![](img/3a32161c95003c67936811c0ea0446aa_50.png)

R over R。 and in the bottom here。I'm going to have N。Minus r factorial， minus1 factorial。



![](img/3a32161c95003c67936811c0ea0446aa_52.png)

Okay， so look what happens when I combine when I combine these terms right。

 if I look at this is n minus r minus1 factorial right。

 so now I have n minus R and then I have that term minus1 factorial right that's the same as having n minus R。



![](img/3a32161c95003c67936811c0ea0446aa_54.png)

![](img/3a32161c95003c67936811c0ea0446aa_55.png)

![](img/3a32161c95003c67936811c0ea0446aa_56.png)

![](img/3a32161c95003c67936811c0ea0446aa_57.png)

Factorial in mind denominator。

![](img/3a32161c95003c67936811c0ea0446aa_59.png)

And then I have our factorial。And then in the top， what do I have， I still have n minus1。



![](img/3a32161c95003c67936811c0ea0446aa_61.png)

Factorial。

![](img/3a32161c95003c67936811c0ea0446aa_63.png)

Times n minus r。Okay。

![](img/3a32161c95003c67936811c0ea0446aa_65.png)

In this other term that I have， right， I now have r times r minus1 factorial。

 That's the same as R factorial， right So if I have n minus R factorial times R factorial。



![](img/3a32161c95003c67936811c0ea0446aa_67.png)

![](img/3a32161c95003c67936811c0ea0446aa_68.png)

![](img/3a32161c95003c67936811c0ea0446aa_69.png)

And then in the numerator， I have n minus1 factorial times R。



![](img/3a32161c95003c67936811c0ea0446aa_71.png)

Okay。So now I can combine these and I have the same denominator。



![](img/3a32161c95003c67936811c0ea0446aa_73.png)

Common denominator， n minus R factorial R factorial。 So in the top。

 what I can now do is I can factor out this n-1。

![](img/3a32161c95003c67936811c0ea0446aa_75.png)

![](img/3a32161c95003c67936811c0ea0446aa_76.png)

Factctorial， so n -1。

![](img/3a32161c95003c67936811c0ea0446aa_78.png)

Factctorial， and what do I left with I'm left with n minus R。



![](img/3a32161c95003c67936811c0ea0446aa_80.png)

![](img/3a32161c95003c67936811c0ea0446aa_81.png)

Plus。Or。Well these cancel out leaving with n times n minus1 factorial， and just like we saw before。

 that is n factorial over n minus R factorial r factorial。

 which is n choose par right so that's a derivation of this identity that we're going to use So where do we use this identity。



![](img/3a32161c95003c67936811c0ea0446aa_83.png)

![](img/3a32161c95003c67936811c0ea0446aa_84.png)

![](img/3a32161c95003c67936811c0ea0446aa_85.png)

![](img/3a32161c95003c67936811c0ea0446aa_86.png)

Well we'll get to that in a moment， I want to talk a little bit more about other applications of this use right so we also have the binomial。



![](img/3a32161c95003c67936811c0ea0446aa_88.png)

![](img/3a32161c95003c67936811c0ea0446aa_89.png)

Theorem。

![](img/3a32161c95003c67936811c0ea0446aa_91.png)

Theorem。And we'll see these things kind of populate occasionally with these combinations。

 so the binomial theorem if you recall， would be something of like know x plus y raised to the n power so this might be you know you know x minus3 all raised to the fourth power how do you foil that out without half an actually enumerate the whole thing and so the binomial theorem says well we can do this by taking the sum as some factor K goes from 0 to n。



![](img/3a32161c95003c67936811c0ea0446aa_93.png)

![](img/3a32161c95003c67936811c0ea0446aa_94.png)

![](img/3a32161c95003c67936811c0ea0446aa_95.png)

![](img/3a32161c95003c67936811c0ea0446aa_96.png)

![](img/3a32161c95003c67936811c0ea0446aa_97.png)

![](img/3a32161c95003c67936811c0ea0446aa_98.png)

![](img/3a32161c95003c67936811c0ea0446aa_99.png)

And we have n choose K。

![](img/3a32161c95003c67936811c0ea0446aa_101.png)

And we have x raiseds to the K power times y raised to the n minus K power。

 and this is the binomial theorem。 So you know if you were to work out a problem like you know x plus3 to the third power。

 you know， can you work that out with this with this theorem， I'll give you a simple one。

 if I wanted to do something like just x plus y。

![](img/3a32161c95003c67936811c0ea0446aa_103.png)

![](img/3a32161c95003c67936811c0ea0446aa_104.png)

![](img/3a32161c95003c67936811c0ea0446aa_105.png)

![](img/3a32161c95003c67936811c0ea0446aa_106.png)

![](img/3a32161c95003c67936811c0ea0446aa_107.png)

Squared， right， this is a very easy one for us to work out。 We have x plus y。



![](img/3a32161c95003c67936811c0ea0446aa_109.png)

X plus y， right we can see that foiling that is going to give us x squared plus 2 x y plus y squared。



![](img/3a32161c95003c67936811c0ea0446aa_111.png)

![](img/3a32161c95003c67936811c0ea0446aa_112.png)

If I use this formula， however， what I have is I now will have the sum going from K equals0 to 2 is my N。

 and I will have。

![](img/3a32161c95003c67936811c0ea0446aa_114.png)

![](img/3a32161c95003c67936811c0ea0446aa_115.png)

2。Choose K。

![](img/3a32161c95003c67936811c0ea0446aa_117.png)

X to the K， y to the 2 minus k and。

![](img/3a32161c95003c67936811c0ea0446aa_119.png)

If we were to work this out， when k is 0， okay2 choose0 is1， there's one way to get0。

 and so this is when k is0。 So if I substitute0 into x raised to the0 is a1 y squared。

 that's just y squared。

![](img/3a32161c95003c67936811c0ea0446aa_121.png)

![](img/3a32161c95003c67936811c0ea0446aa_122.png)

![](img/3a32161c95003c67936811c0ea0446aa_123.png)

![](img/3a32161c95003c67936811c0ea0446aa_124.png)

This is when k equals0。 now when k equals。

![](img/3a32161c95003c67936811c0ea0446aa_126.png)

One， right， I now have two choose one。 How many ways can I do to choose1。

 Well that ends up being a2 and x raised to the first power is x and y raised to the two minus1 is1。

 y。

![](img/3a32161c95003c67936811c0ea0446aa_128.png)

![](img/3a32161c95003c67936811c0ea0446aa_129.png)

And then。When k equals 2， I have two choose2， there's only one way to get2 choose2 x raiseds to the second power。



![](img/3a32161c95003c67936811c0ea0446aa_131.png)

![](img/3a32161c95003c67936811c0ea0446aa_132.png)

Y 2 minus-2 is0。 that makes it a1。 So you'll see that， you know the terms are reversed。

 but we get the same thing。 So that's how you would end up using the binomial theorem。

 And what we see is this choose notation actually is featured as a coefficient in that summation。



![](img/3a32161c95003c67936811c0ea0446aa_134.png)

![](img/3a32161c95003c67936811c0ea0446aa_135.png)

![](img/3a32161c95003c67936811c0ea0446aa_136.png)

right so that's another application We can also use this with multinomial coefficients。

 and I'm going to do another example here for you， so for multi nomial， multinomial。😊。



![](img/3a32161c95003c67936811c0ea0446aa_138.png)

![](img/3a32161c95003c67936811c0ea0446aa_139.png)

![](img/3a32161c95003c67936811c0ea0446aa_140.png)

Coeics。And I'm going to show you this with an example。

 so let's say that there is a police department。

![](img/3a32161c95003c67936811c0ea0446aa_142.png)

![](img/3a32161c95003c67936811c0ea0446aa_143.png)

And it has 10 officers。

![](img/3a32161c95003c67936811c0ea0446aa_145.png)

Okay， and it's going to have a certain restriction where they want five officers on patrol。



![](img/3a32161c95003c67936811c0ea0446aa_147.png)

![](img/3a32161c95003c67936811c0ea0446aa_148.png)

They want to have two at the desk。

![](img/3a32161c95003c67936811c0ea0446aa_150.png)

And three in reserves。If I like to respond to emergencies or something right so they're going to have 10 officers staffing。



![](img/3a32161c95003c67936811c0ea0446aa_152.png)

![](img/3a32161c95003c67936811c0ea0446aa_153.png)

So how many？Divisions。

![](img/3a32161c95003c67936811c0ea0446aa_155.png)

Of three groups。

![](img/3a32161c95003c67936811c0ea0446aa_157.png)

Is possible。All how many divisions of three groups is possible Well， what we would end up having is。



![](img/3a32161c95003c67936811c0ea0446aa_159.png)

![](img/3a32161c95003c67936811c0ea0446aa_160.png)

嗯。We either have 10。

![](img/3a32161c95003c67936811c0ea0446aa_162.png)

Choose five for patrol。Five， choose three for the reserves， and then that leaves two。

 choose two for the desk。

![](img/3a32161c95003c67936811c0ea0446aa_164.png)

![](img/3a32161c95003c67936811c0ea0446aa_165.png)

Or if you wanted to look at it in a different framework， right？



![](img/3a32161c95003c67936811c0ea0446aa_167.png)

You would have 10。Choose5。

![](img/3a32161c95003c67936811c0ea0446aa_169.png)

You would have。5， choose the two for the desk。 And then that leaves you3 for three for the reserves。

 So let's just look at how these are how these are derived and make sure that you understand that these are equivalent。

 So if we have 10 factorial。

![](img/3a32161c95003c67936811c0ea0446aa_171.png)

![](img/3a32161c95003c67936811c0ea0446aa_172.png)

Right。

![](img/3a32161c95003c67936811c0ea0446aa_174.png)

And that's going to be over 10 minus。5 factorial。嗯。And over five factorial。



![](img/3a32161c95003c67936811c0ea0446aa_176.png)

And。Then my next term is5 factorial over5 minus3。

![](img/3a32161c95003c67936811c0ea0446aa_178.png)

![](img/3a32161c95003c67936811c0ea0446aa_179.png)

Factorial over3 factorial。And then two factorial over。Two minus2。Sactctorial over。



![](img/3a32161c95003c67936811c0ea0446aa_181.png)

Two factorial。

![](img/3a32161c95003c67936811c0ea0446aa_183.png)

We'll see that this is0 and then that just leaves two factorial over two factorial， so it's one。

 so that last term drops off right， there's only one way to do that。 If we look at this version。

 we have 10 factorial over 10 minus5 factorial5 factorial。



![](img/3a32161c95003c67936811c0ea0446aa_185.png)

![](img/3a32161c95003c67936811c0ea0446aa_186.png)

![](img/3a32161c95003c67936811c0ea0446aa_187.png)

We have five factorial over5 minus2。Factorial over three factorial there。

And then we have the same thing here， three factorial over3 minus3 factorial，3 factorial， this is0。

 these cancel， so then really this term is the same in either way。

 and so what we see is5 over 5 minus2 is 3。

![](img/3a32161c95003c67936811c0ea0446aa_189.png)

![](img/3a32161c95003c67936811c0ea0446aa_190.png)

![](img/3a32161c95003c67936811c0ea0446aa_191.png)

And5 minus3 is2- I'm sorry this should have been a two factorial， I apologize。



![](img/3a32161c95003c67936811c0ea0446aa_193.png)

Because it was choose 2。 So this two is here。

![](img/3a32161c95003c67936811c0ea0446aa_195.png)

And this is a three here， so you see that these terms are equivalent either way。

 so when you're working with these kind of selection problems for division。

 the order in which you do these actually does not matter as far as a division problem goes。



![](img/3a32161c95003c67936811c0ea0446aa_197.png)

![](img/3a32161c95003c67936811c0ea0446aa_198.png)

![](img/3a32161c95003c67936811c0ea0446aa_199.png)

So the general form of that previous example is that if you have divisions that you're grouping。

 so you have like an object and you're going to take a division that is n1， and2 and3， right， etter。

 right， and you're doing these divisions， the general form is that you're going to have n。



![](img/3a32161c95003c67936811c0ea0446aa_201.png)

![](img/3a32161c95003c67936811c0ea0446aa_202.png)

![](img/3a32161c95003c67936811c0ea0446aa_203.png)

![](img/3a32161c95003c67936811c0ea0446aa_204.png)

![](img/3a32161c95003c67936811c0ea0446aa_205.png)

Shu。N1， the first grouping， and then that will be multiplied by n minus N1。



![](img/3a32161c95003c67936811c0ea0446aa_207.png)

![](img/3a32161c95003c67936811c0ea0446aa_208.png)

And you take the second grouping。Which is then going to be。



![](img/3a32161c95003c67936811c0ea0446aa_210.png)

And subtract the number you've taken for the first group， number you've taken for the second group。



![](img/3a32161c95003c67936811c0ea0446aa_212.png)

You select N3。And then you go， so on， right？

![](img/3a32161c95003c67936811c0ea0446aa_214.png)

All the way until you get to。

![](img/3a32161c95003c67936811c0ea0446aa_216.png)

N minus n1， minus n2， minus n3 minus。

![](img/3a32161c95003c67936811c0ea0446aa_218.png)

All the way to and are your last group， and then that's where you're going to pick。



![](img/3a32161c95003c67936811c0ea0446aa_220.png)

![](img/3a32161c95003c67936811c0ea0446aa_221.png)

Whatever the last division out of this group that you're going to pick so you know what we what we see is that when you start you know。

 working all of that out and I leave that to you as an exercise。

 what you end up getting is n factorial。

![](img/3a32161c95003c67936811c0ea0446aa_223.png)

![](img/3a32161c95003c67936811c0ea0446aa_224.png)

![](img/3a32161c95003c67936811c0ea0446aa_225.png)

And in the bottom， you have N one factorial and two factorial。



![](img/3a32161c95003c67936811c0ea0446aa_227.png)

![](img/3a32161c95003c67936811c0ea0446aa_228.png)

And three factorial all the way up to N R。

![](img/3a32161c95003c67936811c0ea0446aa_230.png)

Factial right and so this is how you select how many ways you can create different groupings or different divisions of a population as you're going through I'll give you an example here。



![](img/3a32161c95003c67936811c0ea0446aa_232.png)

![](img/3a32161c95003c67936811c0ea0446aa_233.png)

There are 32 teams。

![](img/3a32161c95003c67936811c0ea0446aa_235.png)

In the NFL。Right and of course we know that the Steelers are the best。

 it's great being a Steelers fan at Johns Hopkins in Baltimore and so if we were going to construct a single elimination right。

 single elimination。

![](img/3a32161c95003c67936811c0ea0446aa_237.png)

![](img/3a32161c95003c67936811c0ea0446aa_238.png)

![](img/3a32161c95003c67936811c0ea0446aa_239.png)

![](img/3a32161c95003c67936811c0ea0446aa_240.png)

Tournament for all teams in the NFL， right？

![](img/3a32161c95003c67936811c0ea0446aa_242.png)

How many outcomes？How many outcomes with total information？



![](img/3a32161c95003c67936811c0ea0446aa_244.png)

So I just don't don't want to know just how many winners are there because that's obvious like 32 potential winners。

 but with total information right， total recall right so what are the different sequences in in which these games can go right and then B is how many outcomes are possible right how many。



![](img/3a32161c95003c67936811c0ea0446aa_246.png)

![](img/3a32161c95003c67936811c0ea0446aa_247.png)

![](img/3a32161c95003c67936811c0ea0446aa_248.png)

![](img/3a32161c95003c67936811c0ea0446aa_249.png)

Okay。So if I divide the teams， right， if I divide into 16 pairs， right， if I look at 16 pairs。



![](img/3a32161c95003c67936811c0ea0446aa_251.png)

![](img/3a32161c95003c67936811c0ea0446aa_252.png)

![](img/3a32161c95003c67936811c0ea0446aa_253.png)

Right， then what I have is I have this same division problem right where what I really have is I have。



![](img/3a32161c95003c67936811c0ea0446aa_255.png)

![](img/3a32161c95003c67936811c0ea0446aa_256.png)

You know， 32。Factorial。And I have。

![](img/3a32161c95003c67936811c0ea0446aa_258.png)

2。

![](img/3a32161c95003c67936811c0ea0446aa_260.png)

Times 2， times 2 times， right？Because you know， two factorials just two all the way up for all 16 pairs。

 which is equivalent to 32 factorial over。

![](img/3a32161c95003c67936811c0ea0446aa_262.png)

![](img/3a32161c95003c67936811c0ea0446aa_263.png)

Two pairs，16 right so when when there's no ordering of the pairs right。

 then what I have is I have you know the the。

![](img/3a32161c95003c67936811c0ea0446aa_265.png)

![](img/3a32161c95003c67936811c0ea0446aa_266.png)

Have 32 factorial。

![](img/3a32161c95003c67936811c0ea0446aa_268.png)

Invied by two to the 16th power。There are 16 factorial possible combinations of the team。

 so for each ordered pair， there are two possible winners， right？



![](img/3a32161c95003c67936811c0ea0446aa_270.png)

![](img/3a32161c95003c67936811c0ea0446aa_271.png)

![](img/3a32161c95003c67936811c0ea0446aa_272.png)

For each pair。Two possible winners。

![](img/3a32161c95003c67936811c0ea0446aa_274.png)

![](img/3a32161c95003c67936811c0ea0446aa_275.png)

Right， so two possible winners， thus， you know， you know。

 when I look at how many ways there are to get winners， right， I end up with 32 factorial over two。



![](img/3a32161c95003c67936811c0ea0446aa_277.png)

![](img/3a32161c95003c67936811c0ea0446aa_278.png)

![](img/3a32161c95003c67936811c0ea0446aa_279.png)

To the。16，16 factorial， and there's two to 16 possible winners， right。

 because one team's going to win and there's 16 different games。 So these cross out。

 and I'm left with 32 factorial over。

![](img/3a32161c95003c67936811c0ea0446aa_281.png)

![](img/3a32161c95003c67936811c0ea0446aa_282.png)

![](img/3a32161c95003c67936811c0ea0446aa_283.png)

16 factorial。Okay， so similarly then for。16 teams now going into the next round， right。

 for 16 teams because this' is a single elimination。

 I'll have 16 factorial over8 factorial by the same logic。

 So then by the generalized rule of counting， what I end up having is 32 factorial over 16 factorial times 16 factorial over 8 factorial times 8 factorial。



![](img/3a32161c95003c67936811c0ea0446aa_285.png)

![](img/3a32161c95003c67936811c0ea0446aa_286.png)

![](img/3a32161c95003c67936811c0ea0446aa_287.png)

![](img/3a32161c95003c67936811c0ea0446aa_288.png)

![](img/3a32161c95003c67936811c0ea0446aa_289.png)

Over four factorial times 4 factorial over two factorial times two factorial over one factorial right。

 and so we end up having these cancel out。

![](img/3a32161c95003c67936811c0ea0446aa_291.png)

![](img/3a32161c95003c67936811c0ea0446aa_292.png)

Which ends up equaling 32 factorial， which kind of makes sense for what you would think right if there's 32 teams。

 how many ways can you kind of order them from number one to number 32 and you end up with 32 factorial。



![](img/3a32161c95003c67936811c0ea0446aa_294.png)

![](img/3a32161c95003c67936811c0ea0446aa_295.png)

![](img/3a32161c95003c67936811c0ea0446aa_296.png)

![](img/3a32161c95003c67936811c0ea0446aa_297.png)

Right。