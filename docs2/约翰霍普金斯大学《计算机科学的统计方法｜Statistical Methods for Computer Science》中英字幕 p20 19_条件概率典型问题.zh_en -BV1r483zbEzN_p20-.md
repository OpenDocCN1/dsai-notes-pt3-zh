# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p20 19_条件概率典型问题.zh_en -BV1r483zbEzN_p20-

Yeah。

![](img/334b1ce213110587572a44ae7ab11a05_1.png)

Alright， I have a question for you。If you you can choose between one of two abilities。

 I want you to think about this， you can choose between one of two abilities right you could either speak any language in the world。

 like you could just walk up to any country， any culture， whatever。

 and you could just start fluently speaking in whatever language that is right you can pick the language anybody so you can communicate with anybody on the planet that's ability number one。



![](img/334b1ce213110587572a44ae7ab11a05_3.png)

![](img/334b1ce213110587572a44ae7ab11a05_4.png)

![](img/334b1ce213110587572a44ae7ab11a05_5.png)

Ability number two is you could choose to play any musical instrument like you could go and just pick up the guitar。

 you could be like you know playing like a virtuos cell you're like awesome on the guitar you could go pick up some weird instrument in a culture you've never seen before and just pick it up and you're like awesome at playing the music。

 you can play any musical instrument， you play any band right so you can either play the musical instrument or the language what would you choose。

 what would your ability be。

![](img/334b1ce213110587572a44ae7ab11a05_7.png)

![](img/334b1ce213110587572a44ae7ab11a05_8.png)

![](img/334b1ce213110587572a44ae7ab11a05_9.png)

Think about it。All right， itd be interesting if you go if you're doing the online version of the class。

 go and post your answer and let's just tabulate what what people people's responses are just say musical instrument or language now of course I did this in class and so I was able to create a table right so that we have some data for our problem here so let's say here we have the ability。



![](img/334b1ce213110587572a44ae7ab11a05_11.png)

![](img/334b1ce213110587572a44ae7ab11a05_12.png)

![](img/334b1ce213110587572a44ae7ab11a05_13.png)

All right， ability here， ability。And so we have two abilities， we have the language。Language。

 and we have the instrument。

![](img/334b1ce213110587572a44ae7ab11a05_15.png)

Right。

![](img/334b1ce213110587572a44ae7ab11a05_17.png)

And in the class， right， we typically have males。

![](img/334b1ce213110587572a44ae7ab11a05_19.png)

And we have females。

![](img/334b1ce213110587572a44ae7ab11a05_21.png)

Females。And so the data that I collected is there are seven males and three females and one and four。

 and so we get a total。

![](img/334b1ce213110587572a44ae7ab11a05_23.png)

![](img/334b1ce213110587572a44ae7ab11a05_24.png)

Total。😔。

![](img/334b1ce213110587572a44ae7ab11a05_26.png)

So the total across this is eight people like the language， seven people chose an instrument。



![](img/334b1ce213110587572a44ae7ab11a05_28.png)

1en males and five females in the class for a total of 15 people。



![](img/334b1ce213110587572a44ae7ab11a05_30.png)

![](img/334b1ce213110587572a44ae7ab11a05_31.png)

Okay， so。The first question that we have is what is the probability that somebody would choose language。

 what is the probability that somebody would pick language in the class？



![](img/334b1ce213110587572a44ae7ab11a05_33.png)

![](img/334b1ce213110587572a44ae7ab11a05_34.png)

Well。Again， we're just going to look at how many create success out of how many possible。

 so there are how many people in the class。

![](img/334b1ce213110587572a44ae7ab11a05_36.png)

![](img/334b1ce213110587572a44ae7ab11a05_37.png)

15， how many people choose language，8？

![](img/334b1ce213110587572a44ae7ab11a05_39.png)

So that becomes the probability that language was chosen。



![](img/334b1ce213110587572a44ae7ab11a05_41.png)

We can look at something and say， hey， what's the probability you're a female， different issue。

 not ability now we're talking about gender， what's the probability you're a female in the class well again there's still 15 students。

 the probability that your're female is five out of 15 or one third。



![](img/334b1ce213110587572a44ae7ab11a05_43.png)

![](img/334b1ce213110587572a44ae7ab11a05_44.png)

![](img/334b1ce213110587572a44ae7ab11a05_45.png)

![](img/334b1ce213110587572a44ae7ab11a05_46.png)

What we're going to be talking about today is conditional probability。

 so we're interested in this question that says， what is the probability you are female given given that you have。



![](img/334b1ce213110587572a44ae7ab11a05_48.png)

![](img/334b1ce213110587572a44ae7ab11a05_49.png)

Decided to play an instrument。 So in the table， much like when we did the trees， right。

 we're going to exclude items that are not possible。 So I know that you chose an instrument。

 So that means we're only looking at this line， right， These people don't matter， right。

 they're their language speakers， right， So we're just saying of the people that chose the an instrument。



![](img/334b1ce213110587572a44ae7ab11a05_51.png)

![](img/334b1ce213110587572a44ae7ab11a05_52.png)

![](img/334b1ce213110587572a44ae7ab11a05_53.png)

![](img/334b1ce213110587572a44ae7ab11a05_54.png)

![](img/334b1ce213110587572a44ae7ab11a05_55.png)

What's the probability you are a female， Well， the denominator changes now。

 there's seven people that have chosen an instrument， and of that。

 there is four out of the seven that are female。

![](img/334b1ce213110587572a44ae7ab11a05_57.png)

![](img/334b1ce213110587572a44ae7ab11a05_58.png)

![](img/334b1ce213110587572a44ae7ab11a05_59.png)

Now， I'm going to point out something very interesting to you is you'll notice that these two probabilities are not the same。

 right， So the probability of being a female。

![](img/334b1ce213110587572a44ae7ab11a05_61.png)

![](img/334b1ce213110587572a44ae7ab11a05_62.png)

Is different if I have this additional information of knowing that you prefer to play a musical instrument。

 And so what that that means is。

![](img/334b1ce213110587572a44ae7ab11a05_64.png)

![](img/334b1ce213110587572a44ae7ab11a05_65.png)

The fact that these are not the same means that we have dependence。



![](img/334b1ce213110587572a44ae7ab11a05_67.png)

![](img/334b1ce213110587572a44ae7ab11a05_68.png)

Depenence right so that means that these are not independent events。

 there's some level of correlation or some relationship between the ability you choose and your gender。

 not saying it's causal， not saying that one drives the other。

 we're just saying that there is a relationship right so given what I've just done here right I would like you to answer the question。

 what is the probability that you are going to choose language， given that you are a male。



![](img/334b1ce213110587572a44ae7ab11a05_70.png)

![](img/334b1ce213110587572a44ae7ab11a05_71.png)

![](img/334b1ce213110587572a44ae7ab11a05_72.png)

![](img/334b1ce213110587572a44ae7ab11a05_73.png)

Okay， so at this point， I'd like you to pause the video， take a look at the table。

 keyboard you can see it， and work out that probability right there。



![](img/334b1ce213110587572a44ae7ab11a05_75.png)

So I'm assuming you've paused the video and you have worked out the problem。

 so we're given that we're a mouse， so we're only going to look in this column right。

 only in this column， so the denominator is what it's 10。



![](img/334b1ce213110587572a44ae7ab11a05_77.png)

![](img/334b1ce213110587572a44ae7ab11a05_78.png)

And now of these 10， what's the probability that they're going to speak a language while you have seven so you get seven tenths becomes the probability or 0。

7 if you're a millennial and you like to work with decimals。



![](img/334b1ce213110587572a44ae7ab11a05_80.png)

![](img/334b1ce213110587572a44ae7ab11a05_81.png)

![](img/334b1ce213110587572a44ae7ab11a05_82.png)

So the question I have for you， question， right？

![](img/334b1ce213110587572a44ae7ab11a05_84.png)

Is。

![](img/334b1ce213110587572a44ae7ab11a05_86.png)

Probability of a given B， right。

![](img/334b1ce213110587572a44ae7ab11a05_88.png)

Does that equal the probability of B given A Does the probability of A given B equal the probability of B given A。

 I want you to just stop for a minute， pause the video and meditate on that。

 Think about it a little bit right and hit play when you're ready to resume when you have an answer。



![](img/334b1ce213110587572a44ae7ab11a05_90.png)

![](img/334b1ce213110587572a44ae7ab11a05_91.png)

![](img/334b1ce213110587572a44ae7ab11a05_92.png)

All right， well， the answer to that is。No， right， That is not the case， right， That is not the case。

 And so， you know， we can just work out a simple counter example to that。 you know。

 we've already calculated the probability of being female given I。 So what is the probability of。



![](img/334b1ce213110587572a44ae7ab11a05_94.png)

![](img/334b1ce213110587572a44ae7ab11a05_95.png)

I given female right。 Well， if I'm a female， I'm dealing with this column。 So that is fifth。



![](img/334b1ce213110587572a44ae7ab11a05_97.png)

What's the likelihood I chose an instrument for fifth。



![](img/334b1ce213110587572a44ae7ab11a05_99.png)

So clearly4/ fifths is not the same as4/ seventhth。

 so just as a counterex I can show that this is not true right so just because a depends on B B may depend on a but not in the same way right so they're not so when you see these conditional probabilities it is not the case right this is a flat no is not the case that probability A given B is the same as the probability of B given A I just wanted to dispel that。



![](img/334b1ce213110587572a44ae7ab11a05_101.png)

![](img/334b1ce213110587572a44ae7ab11a05_102.png)

![](img/334b1ce213110587572a44ae7ab11a05_103.png)

![](img/334b1ce213110587572a44ae7ab11a05_104.png)

![](img/334b1ce213110587572a44ae7ab11a05_105.png)

Okay。So I'm going to give you another question， right， this time I'm going to give you。



![](img/334b1ce213110587572a44ae7ab11a05_107.png)

Who wants to be a millionaire type question， right？



![](img/334b1ce213110587572a44ae7ab11a05_109.png)

What does。

![](img/334b1ce213110587572a44ae7ab11a05_111.png)

What does。the probability of l given m，Min。😔。

![](img/334b1ce213110587572a44ae7ab11a05_113.png)

What does it mean， Okay， I'm going to give you two choices， right？



![](img/334b1ce213110587572a44ae7ab11a05_115.png)

Right A is。That70% of males。Right70% of males choose language。



![](img/334b1ce213110587572a44ae7ab11a05_117.png)

![](img/334b1ce213110587572a44ae7ab11a05_118.png)

Right。😔，B is 70 percent。Of those。

![](img/334b1ce213110587572a44ae7ab11a05_120.png)

Chuing。😔，Language。😔。

![](img/334b1ce213110587572a44ae7ab11a05_122.png)

Ping。😔，Wdge。😔。

![](img/334b1ce213110587572a44ae7ab11a05_124.png)

Or mail。 do you see the difference so we already to calculate a probability of L given an M is 70% right or seven tenths？



![](img/334b1ce213110587572a44ae7ab11a05_126.png)

So my question to you is what does that mean Does it mean that 70% of the men choose language or does it mean that 70% of the language choosers are male。

 I'd like you to pause the video， meditate on that for a minute and then hit play when you're ready to resume。



![](img/334b1ce213110587572a44ae7ab11a05_128.png)

![](img/334b1ce213110587572a44ae7ab11a05_129.png)

![](img/334b1ce213110587572a44ae7ab11a05_130.png)

O。Well， let's take a look at this problem right I'm not going to jump to the answer right。

 so 70% of males choose language。

![](img/334b1ce213110587572a44ae7ab11a05_132.png)

So of males，70% of males。 So here we are。 Here's of the males。



![](img/334b1ce213110587572a44ae7ab11a05_134.png)

Right70% choose language。 Well， it looks like it could be true，70%， All right。

70% of those choosing language of those choosing language of those choosing language。



![](img/334b1ce213110587572a44ae7ab11a05_136.png)

![](img/334b1ce213110587572a44ae7ab11a05_137.png)

![](img/334b1ce213110587572a44ae7ab11a05_138.png)

Right。Well，7 out of8 are male。

![](img/334b1ce213110587572a44ae7ab11a05_140.png)

That's not 70%， so the correct answer if you spend a little bit of time thinking about it is going to be this one and it is 70% of males choose language。

 right。

![](img/334b1ce213110587572a44ae7ab11a05_142.png)

![](img/334b1ce213110587572a44ae7ab11a05_143.png)

70% of males choose language right so you need to think about what these conditional probabilities mean。

 you're probably not used to dealing with them so they can be a little bit counterintuitive。



![](img/334b1ce213110587572a44ae7ab11a05_145.png)

![](img/334b1ce213110587572a44ae7ab11a05_146.png)

![](img/334b1ce213110587572a44ae7ab11a05_147.png)

Okay。So。Let's calculate a couple of these other probabilities right what I'd like you to do as an exercise right now is calculate the probability of being a male。



![](img/334b1ce213110587572a44ae7ab11a05_149.png)

Calculate the probability of choosing language。

![](img/334b1ce213110587572a44ae7ab11a05_151.png)

Calculate the probability of being a male。Given language。



![](img/334b1ce213110587572a44ae7ab11a05_153.png)

And we've already calculated the probability of language given a male okay so calculate these three items。

 so hit pause in the video， calculate these three items and hit play when you're ready to resume。



![](img/334b1ce213110587572a44ae7ab11a05_155.png)

![](img/334b1ce213110587572a44ae7ab11a05_156.png)

。Okay， welcome back， I'm assuming you have done this exercise。

 and I'm going to ask you to verify for yourself that that should be 10 over 15。



![](img/334b1ce213110587572a44ae7ab11a05_158.png)

![](img/334b1ce213110587572a44ae7ab11a05_159.png)

8 over 15。

![](img/334b1ce213110587572a44ae7ab11a05_161.png)

And。7，7 over 8。

![](img/334b1ce213110587572a44ae7ab11a05_163.png)

seven over 8， okay。

![](img/334b1ce213110587572a44ae7ab11a05_165.png)

So we're now going to look at a slight variation， which is what is the probability probability that you are male and。

Language。Male and language And what I'm going to argue is that being male and language is the same as the probability of male。



![](img/334b1ce213110587572a44ae7ab11a05_167.png)

Given language。Times the probability of choosing language， okay？So let's look and see if that's true。



![](img/334b1ce213110587572a44ae7ab11a05_169.png)

Well， what's the probability of being male and language well male？



![](img/334b1ce213110587572a44ae7ab11a05_171.png)

And language is 7， So that is 7。Out of 15 people。Right。



![](img/334b1ce213110587572a44ae7ab11a05_173.png)

Well， what is the probability of being male given language， Well， the probability being male。

 given language， right， so being male， given that we're dealing with the language speakers。

 I'm sorry right here right the probability of male。



![](img/334b1ce213110587572a44ae7ab11a05_175.png)

Given that we're a language speaker is seven eighths。



![](img/334b1ce213110587572a44ae7ab11a05_177.png)

![](img/334b1ce213110587572a44ae7ab11a05_178.png)

And what's the probability of being a language speaker， that's 8 out of 15， right？



![](img/334b1ce213110587572a44ae7ab11a05_180.png)

8 out of 15。 And do you see what's happening here， the8， right？Cancel out。 the8s cancel out。

 and you are left with。

![](img/334b1ce213110587572a44ae7ab11a05_182.png)

7，15s， which is the same as your value there。 Well， I would also contend that if that's true。

 then the probability because hand this could be either way， right， This could be L and M， right。

 probability of L given M。

![](img/334b1ce213110587572a44ae7ab11a05_184.png)

![](img/334b1ce213110587572a44ae7ab11a05_185.png)

Times the probability of M。

![](img/334b1ce213110587572a44ae7ab11a05_187.png)

If we work that out。Well what's the probability L given M is seven/ tenths。



![](img/334b1ce213110587572a44ae7ab11a05_189.png)

And the probability of M。

![](img/334b1ce213110587572a44ae7ab11a05_191.png)

You calculated was 1015th。

![](img/334b1ce213110587572a44ae7ab11a05_193.png)

So when we actually cancel that out， we still get 715s。 and so in general， we call this Bay rule。



![](img/334b1ce213110587572a44ae7ab11a05_195.png)

![](img/334b1ce213110587572a44ae7ab11a05_196.png)

Bs rule， and we say that the probability of A， given B。



![](img/334b1ce213110587572a44ae7ab11a05_198.png)

Equals。er。Probability of B given a。Times the probability of a。Over the probability of B， right。

 What do we do here， Well， if I replace this with。A and B。



![](img/334b1ce213110587572a44ae7ab11a05_200.png)

And this B and A。

![](img/334b1ce213110587572a44ae7ab11a05_202.png)

RightWell， the probability here of a given B， right all I have to do is divide both sides by this probability of B。

 and I get the other side right， so that is how we actually end up getting to this formula。



![](img/334b1ce213110587572a44ae7ab11a05_204.png)

Of。😔。

![](img/334b1ce213110587572a44ae7ab11a05_206.png)

Bay's rule， and so we're going to do a lot more with that formula。

