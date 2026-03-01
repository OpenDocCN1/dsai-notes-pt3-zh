# 约翰霍普金斯大学《数据科学：时间中的决策｜Data Science Decisions in Time》中英字幕 p13 12_矩阵运算构建链式模型.zh_en -BV1NCuzzfEJa_p13-

As we move along in our consideration of Markov models。

 I'd like to share slightly more detailed Markov model。 This is really still mainly conceptual。

 but I think it helps to illustrate more of these ideas about how you might be to model the process of something going to failure and once you've got a model again。

 then you've got at least the ability to imagine optimizing。

 you've got the ability to design ideally anyway。 prevent a maintenance schedule or some other set of controls to try and keep the part or the ability to the bridge active for as long as possible。

 And again， this is very much in the spirit of Waled very much on the idea of sequential hypothesis testing。

 we're trying to make the most of the data coming in。

 we're trying to make the most of the decisions we can make as time goes along in order to help a particular part to stay active for as long as possible。

 So I hope you'll enjoy this next part。So we continuing with our metaphor of trying to prevent something like this or sitecon collapse from happening。

 We'll continue to look at Markov models as an approach for thinking about that。

 One way of thinking about that is this kind of a Markov model indicated here D1 all the way up to D and these are states where things are working well M or maintenance states F is a failure state So we can think about it it's like D for duty cycle。

 meaning that it's available the only standing bridges active。

 whatever it's taking on duty Each of these D states can transition and we can represent all of this as a matrix。

 So mathematically this is an eight state in this particular example matrix where we've got three good states follows the first three the next me maintenance states not the mu sub M along the diagonal and then the last two states are failure modes mu1 and mu0 So obviously what we're trying to optimize in the long term on this is a schedule of maintenance。



![](img/0c0a9541c1b005945b8ce1f62b71bf67_1.png)

hellps us to define what's going on Now obviously these eight states all have to have probabilities that sum to one this is the normal way of thinking about a model you're in one of these states with absolute certain probability what you want to do though is to optimize the likelihood that you in the first three states because those of the duty states those are the active states again those are the states where the building is standing in the bridge is active so we can optimize lambda sub m which is the maintenance states。

 the likelihood of going to the maintenance states in order to prevent the failure states by looking at our active cycle as being best when p1 and P2 and P3 are as large as possible again subject to all of these states sum to1 so this kind of a matrix model can be solved one could do this in Matlab or maple or any other sort of program here's an example for the ticket of paper that we've been talking about where we've got are three different total time to failures these are lambda zero so remember these would be like for the full component。

 the time to failure and then we've got an optimum you see。

Three these curves go up and optimize sometime between roughly 100 to 250 some days these are days along the X axises。

 and so those would be the optimal maintenance schedule along the X axis is Lambda ofam。

 and the idea would be to prevent things like what happened at surffside。

 these circles here indicate columns that may have failed。

 it may have been that they were designed poorly it may have been that there's other reasons this may not have been the only reason still under investigations to what caused the collapse。

 but the idea is that if there had been an ability to more actively do prevent a maintenance。

 the possibility of that collapse having happened would have been less and dramatically and again the failure modes that led to this collapse F1 and F0 are what we're trying to avoid。



![](img/0c0a9541c1b005945b8ce1f62b71bf67_3.png)

So I hope you've got some feeling now for how a Markov model could be really set up in some detail in order to define an optimal schedule again。

 this flows very naturally from our squ hypothesis testing ideas and I think it helps to illustrate the power of a good model also obviously one has to be careful not to depend too much on the model it is just a model for the real situation but to the extent that one can draw insight and to the extent that one can fit real data into a model type setting you've got tremendous ability down to optimize and that's really the larger part of these last few weeks is how does one take a perspective on data that helps you to see into the right kind of decisions by fitting a model to it by thinking carefully about what that model is telling us in terms of optimization and then maybe iterating in order to improve both model and optimization。

