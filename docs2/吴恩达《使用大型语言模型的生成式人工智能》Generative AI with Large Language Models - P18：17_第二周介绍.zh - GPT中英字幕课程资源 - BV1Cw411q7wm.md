# 吴恩达《使用大型语言模型的生成式人工智能》Generative AI with Large Language Models - P18：17_第二周介绍.zh - GPT中英字幕课程资源 - BV1Cw411q7wm

Welcome back。 I'm here with our instructors for this week， Mike and Shelby。 Last week。

 you learn about Transformer networks， which is really a key foundation for large language models as well as the gen AI project lifecycle。

 and this week there's lots more to dive into starting with instruction tuning of large language models and then later how to carry out fine tuning in an efficient way。

 Yeah， so we take a look at instruction fine tuning So when you have your base model。

 the thing that's initially pretrained。 it's encoded a lot of really good information usually about the world。

 So it knows about things but it doesn't necessarily know how to be able to respond to prompt that questions So when we instruct it to do a certain task it doesn't necessarily know how to respond。

 And so instruction fine tuning helps it to be able to change its behavior to be more helpful for us。

 I saw instruction fine tuning as one of those major breakthroughs in the really history of large language。

😊。

![](img/54399d187778c11326cb23a51a213185_1.png)

MoelsBecause by learning off general text off the internet and other sources。

 you learn to predict the next word， but predicting what's the next word on the internet is not the same as following instructions。

 I thought it's amazing you can take a large languagegg model。

 train it on hundreds of billions of words off the internet and then fine tune it with a much smaller data set on following instructions and just learn to do that。

 That's right。 And one of the things you have to watch out for of course is catastrophic forgetting。

 and this is something that we talk about in the course。

 So that's where you train the model on some extra data and this fine tuning and then it forgets all of that stuff that it had before or a big chunk of that data that it had before。

 And so there are some techniques that we'll talk about in the course to help combat that such as doing in fine tuning across a really broad range of different instruction types。

 So it's not just a case of just tuning it on just the thing you wanted it to do。

 you might have to be a little bit broader than that as well but we talk about it in the course。

And so it turns out that there are two types of fine tuning that are very worth doing。

 one is that instruction fine tuning they just talk about Mike。

When a specific developer is trying to fine tune it for their own application for a specialized application。

 one of the problems with fine tuning is you take a J model and you fine tune in every single parameter in that model。

 you have this big thing to store around and deploy and there's actually very compute and memory expensive So fortunately they' better techniques in that right and we talk about parameter efficient fine tuning or PE for short as a set of methods that can allow you to mitigate some of those concerns right So we have a lot of customers that do want to be able to tune for very specific tasks。

 very specific domains and parameter efficient fine tuning is a great way to still achieve similar performance results in a lot of tasks on a lot of tasks that you can with full fine tuning。

 but then actually take advantage of techniques that allow you to freeze those original model weights or add adaptive layers on top of that with a much smaller memory footprint right so that you can train for multiple tasks Yeah in fact。

 one of the techniques that I know you've used a lot is。

Laura I remember when I read the Laura paper I thought oh， this just makes sense。

 This is gonna work right we see a lot of excitement demand around Laura because of the performance results of using those lower matrices as opposed to full fine tuning right so you're able to get really good performance results with minimal compute and memory requirements So what I'm seeing among different developers is many developers will often start off with prompting and sometimes you that gives you good enoughperform and that's great and sometimes prompting his a ceiling in performance and then this type of fine tuning with Laura or other pe techniques is really critical for unlocking that extra level of performance and then the other thing I'm seeing among a lot of you know O developers is a discussion debate about the cost of using a giant model which is a lot of benefits versus you know for your application fine tuning a smaller model exactly full fine tuning can be costproive to say the least so the ability to。

Be able to use techniques like PF to put fine tuning generative AI models kind of in the hands of everyday users that do have those cost constraints in their cost conscious which is pretty much everyone in the real world right of course if you're concerned about where your data is going as well so if it needs to be running in your control then having a model which is of an appropriate size is really important to bring and so once again。

 tons of exciting stuff to dive into this week let's go to the next video where Mike will kick things off with instruction fine tuning。

