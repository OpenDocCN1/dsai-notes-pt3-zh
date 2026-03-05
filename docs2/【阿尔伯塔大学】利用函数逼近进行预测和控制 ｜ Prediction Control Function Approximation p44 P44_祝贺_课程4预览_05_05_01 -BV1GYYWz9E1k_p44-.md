# 【阿尔伯塔大学】利用函数逼近进行预测和控制 ｜ Prediction Control Function Approximation p44 P44_祝贺_课程4预览_05_05_01 -BV1GYYWz9E1k_p44-

![](img/52f0a7d71f56c09a3e325c1347fd3342_0.png)

In coursese 3 we showed you how to use reinforcement learning with function approximation we covered how to approximate value functions and policies using neural networks and fixed basis approaches like tilecoding。

We discussed how function approximation allows for generalization。

 which helps the agent learn faster。But we might lose on the ability to discriminate between the values of states。

The function proxi may no longer be able to get all the values right。

The agent then has to decide how to balance accuracy across states。

 how to allocate its limited approximation resources。

 we introduce objective functions to specify how to balance approximation error and discuss gradient based algorithms to optimize those objectives。

Using all this new knowledge， you are ready to implement a complete reinforcement learning system。

You will study a problem that highlights some of the challenges you might face when applying RL in the wild。

In Cose 4， you will be putting together your knowledge from courses one， two。

 and3 to land a lunar module on the Moon。When Adam and I start working on a new problem。

 we start by having meetings to brainstorm about how to best frame the problem and gather ideas about potential solutions there's rarely one right solution Throughout we will reason with you how we might approach designing an agent for this problem。

We will start by discussing how to formalize the problem as an MDVP。

If someone just told you design an agent to land this lunar module。

 you would have to figure out how to turn that goal into a problem formulation。

 so that of course is where we begin。Then we'll think about how to choose an appropriate learning algorithm an important part of this is actually thinking about all the details of the algorithms involved This includes determining how the agent explores the type of function approximation architecture。

 details inside the function approximators such as the number of features it produces and the list goes on。

A big part of this course is understanding the importance of all these details。

And how to try to gain some insight into how your algorithm behaves with different choices。

Practical implementation begins with understanding。So let's not just see you're talking about it。

 let's dive right in and get our hands dirty with moon dirt， of course。

