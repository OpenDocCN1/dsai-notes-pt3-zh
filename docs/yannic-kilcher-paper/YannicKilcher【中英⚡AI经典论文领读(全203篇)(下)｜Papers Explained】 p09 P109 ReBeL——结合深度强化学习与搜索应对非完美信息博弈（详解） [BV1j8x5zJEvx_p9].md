# YannicKilcher【中英⚡AI经典论文领读(全203篇)(下)｜Papers Explained】 p09 P109 ReBeL——结合深度强化学习与搜索应对非完美信息博弈（详解） [BV1j8x5zJEvx_p9]

Hi there。 Take a look at this variant of the game。 Rock paper scissors。

 It's like usual rock paper scissors， except with the added complexity that when either player chooses scissors。

 Then the rewards and the losses are doubled。 So， for example， you see right here。

 player 1 chooses rock and player 2 chooses scissors。

 So both the reward for player  one and the loss for player 2 are double the size。 Now。

 you might know that in original rock paper scissors。

 the optimal strategy is to play one third of each of the three choices at any time。

 So you basically take a。Fair three sided coin dice。 Does that exist， I'm not sure。 And you throw it。

 And whatever side is up， that's what you play。 However， here， since one of the options is different。

 The sort of optimal strategy shifts。 and interestingly， it shifts as follows。

 What you want to do is you want to play rock and paper， both with 0。4 probability。

 And you want to play scissors with only 0。2 probability。That is pretty interesting。

 You might intuitively conclude that you want to go more where there are more rewards to be had。

 but of course， also you lose more so you might also conclude well。

 it doesn't make a difference ultimately， but。Why does the why does the sort of optimal strategy shift such that you want to decrease your likelihood of playing scissors Let's just quickly analyze this game before we jump into the paper because this game is sort of a microcosm of what the paper of today is about。

 So the paper of today is called combining deep reinforcement learning and search for Ierfect information games by Noam Brown andton Bton。

 Adam Lehr and Qiqeng Gong of Facebook AI research So this paper brings basically what Alpha Go or Alpha0 has done for perfect information games it brings this to the domain of imperfect information games and we'll see what the difficulties are in this and what can be done to solve it and not only do they have an algorithm。

 but they have the interesting theoretical results that。



![](img/06b1a7215063c43f4855ab10b5474f1e_1.png)

![](img/06b1a7215063c43f4855ab10b5474f1e_2.png)

![](img/06b1a7215063c43f4855ab10b5474f1e_3.png)

Under some conditions， namely under the condition that neural networks do something useful will actually converge to naa equilibriums in these games。

 So that is pretty cool。 so practical and theoretical paper right here As always。

 if you like content like this don't hesitate to share it out and tell me what you think in the comments。

 This is not my field。 So I might get quite a bit of stuff wrong right here。

 also if you haven't seen the Negranu poker challenge。 So I think it's the last video I did。

 be sure to check that out just to see how you have to think about situations like this。 Allright。

 let's get back to this rock paper scissors example right here。

 interestingly to note is that these dashed lines here means that player 2 cannot decide which of these states they're in So player2 doesn't know what states are in for player 2。



![](img/06b1a7215063c43f4855ab10b5474f1e_5.png)

![](img/06b1a7215063c43f4855ab10b5474f1e_6.png)

![](img/06b1a7215063c43f4855ab10b5474f1e_7.png)

![](img/06b1a7215063c43f4855ab10b5474f1e_8.png)

![](img/06b1a7215063c43f4855ab10b5474f1e_9.png)

![](img/06b1a7215063c43f4855ab10b5474f1e_10.png)

This is all basically the same state it'd be really easy right if player one plays first and then player two sees what player one does and then they they just act they always win。

However， player two doesn't， so they have to sort of decide what to do independent of which state they're in。

 especially this is a this is a symmetric game right。

 this is a two player game because as two players it's zero sum because whenever one player wins a reward the other player loses the same reward and it is also。

is that makes it symmetric， so all both players play at the same time。

 though that is not necessary in general， but here it's the case。All right so。

This means in this particular case， whatever strategy player1 has， player two must have as well。

 so we'll just do the analysis for player one。

![](img/06b1a7215063c43f4855ab10b5474f1e_12.png)

![](img/06b1a7215063c43f4855ab10b5474f1e_13.png)

So let's say you deviate from this optimal strategy， right。

 we claim that this here is the optimal strategy playing 20% of scissors。

 Let's say player1 doesn't believe it。 player 1 deviates from it and says。

 nah there is so much reward there。 I'm going get some more of that。 So they up this right。

 They up this to like， let's say point I don't know， point3，3。

 like doing the classic  one third or even higher， right， they up this， go more scissors。 Okay， and。



![](img/06b1a7215063c43f4855ab10b5474f1e_15.png)

![](img/06b1a7215063c43f4855ab10b5474f1e_16.png)

![](img/06b1a7215063c43f4855ab10b5474f1e_17.png)

They probably want to take this mass because they have to take it from somewhere。

 They probably want to take this from rock and paper。

 Let's say they just take it equally from rock and paper towards scissors to up the probability that they play scissors。

 So from paper and from rock， they go towards scissors。



![](img/06b1a7215063c43f4855ab10b5474f1e_19.png)

![](img/06b1a7215063c43f4855ab10b5474f1e_20.png)

Now。Player two。Obbsserves this right。 They can just play against player1 for a while or what we're going to assume is that everyone announces their strategy publicly。

 It's the same thing。 you can just observe someone for a while or they can just announce their strategy will treat this equally so player 2 observes player1 playing scissors too often So player2 knows they are very often in this situation right here in this right state。

 they can't directly observe， but they infer I must be very often in this right rightmost state where player 1 chooses scissors and therefore you see player two's payoffs it's zero here minus2 here and two here so they'll say well I or also have this optimal strategy of 0。

4。4。2 what I can do is I can simply knowing that I'm a lot in this state。

 I can simply take some mass from paper and put it on rock。



![](img/06b1a7215063c43f4855ab10b5474f1e_22.png)

![](img/06b1a7215063c43f4855ab10b5474f1e_23.png)

![](img/06b1a7215063c43f4855ab10b5474f1e_24.png)

![](img/06b1a7215063c43f4855ab10b5474f1e_25.png)

![](img/06b1a7215063c43f4855ab10b5474f1e_26.png)

![](img/06b1a7215063c43f4855ab10b5474f1e_27.png)

I play rock way more often。And I reduce the amount I play paper， right， scissors doesn't matter。

 but now I lose to less often， and I win to much more often。 And player 1， in turn。

 loses too much more often and wins much less often right， So player  one wanted to get more reward。

 but they're sort of being punished by player2 for playing this too often。 Now you can say， well。

 player 1 can do the same thing， knowing that player 2 plays rock too often now， right。

 they've taken away math from paper towards rock， knowing that player2 has taken rock player 1 knows that either they're here or they're here。

 right。

![](img/06b1a7215063c43f4855ab10b5474f1e_29.png)

![](img/06b1a7215063c43f4855ab10b5474f1e_30.png)

![](img/06b1a7215063c43f4855ab10b5474f1e_31.png)

![](img/06b1a7215063c43f4855ab10b5474f1e_32.png)

![](img/06b1a7215063c43f4855ab10b5474f1e_33.png)

![](img/06b1a7215063c43f4855ab10b5474f1e_34.png)

And in this case， player 1 can say。Alright， you play rock too often obviously if I play scissors。

 then I'm going to I'm going to lose， but I've already decided I want to play scissors much more so they're trying to make it up right here。

 So what they can do in this case is they can say。When I play paper。

 I win one instead of if I play rock 2， I win 0。 So I know player 2 is playing rock way more often than they should。

 So I'm going to punish player 2 by playing paper more often。 So let's erase this arrow。

 Let's say we play scissors。 Sorry， we play scissors。 No， let's not erase this。

 We play scissors by moving from rock。 And we also move from rock to paper。

 Like we're almost never playing rock。 We're just playing scissors more often because that's what we started with。

 and we're playing also now paper more often。 So now we basically do the same thing that player 2 did to us。

 We are。

![](img/06b1a7215063c43f4855ab10b5474f1e_36.png)

Uppping the likelihood of this thing happening and decreasing the likelihood of this thing happening。

 So now we can say now also I play paper more often。

 now I also win more often here and you lose more often。

 but you see because the rewards are doubled over here the fact that player two can achieve this。



![](img/06b1a7215063c43f4855ab10b5474f1e_38.png)

![](img/06b1a7215063c43f4855ab10b5474f1e_39.png)

Is much more meaningful than the fact that player 1 can achieve this Okay。

 and that's why player 1 will be punished harder for deviating here。

 So that's sort of how you reason about these strategies。

 So if player 1 will play this  point2 too often they will be punished harder than player 2 for deviating in response to that。

 And the same counts for the symmetric part。

![](img/06b1a7215063c43f4855ab10b5474f1e_41.png)

![](img/06b1a7215063c43f4855ab10b5474f1e_42.png)

![](img/06b1a7215063c43f4855ab10b5474f1e_43.png)

![](img/06b1a7215063c43f4855ab10b5474f1e_44.png)

![](img/06b1a7215063c43f4855ab10b5474f1e_45.png)

![](img/06b1a7215063c43f4855ab10b5474f1e_46.png)

This is a very important concept right here， namely。



![](img/06b1a7215063c43f4855ab10b5474f1e_48.png)

You can see player two， strategy depends on player one strategy。

 even though you could conceptualize this game of player one plays a move。



![](img/06b1a7215063c43f4855ab10b5474f1e_50.png)

And then they play a move， but they don't show it yet， right？ They play a move。

 They take like a picture of their hands doing rock paper scissors and they just don't show the picture yet。

 And then player two plays a move。 So now we're basically back in we're in this game where it's sequential in nature And usually in a sequential game。

 you can just do a sub game analysis So you can just say， okay。



![](img/06b1a7215063c43f4855ab10b5474f1e_52.png)

![](img/06b1a7215063c43f4855ab10b5474f1e_53.png)

![](img/06b1a7215063c43f4855ab10b5474f1e_54.png)

And do a subga analysis， but the subga analysis depends on the strategy of player1 because you don't know the situation。

 This is different than a full information game。

![](img/06b1a7215063c43f4855ab10b5474f1e_56.png)

![](img/06b1a7215063c43f4855ab10b5474f1e_57.png)

And this is illustrated。