# IBM【中英⚡面向项目经理的生成式AI 专项课程｜Generative AI for Project Managers Specialization】 p26 P26 03_思维链方法 [BV1DnxVziEnn_p26]

Welcome to this video on the Cha of Thought App。

![](img/8adfe62f9283bcfe8e6639aaa553d598_1.png)

After watching this video， you'll be able to define the chain of Dot approach and describe its applications in generative AI models。



![](img/8adfe62f9283bcfe8e6639aaa553d598_3.png)

The chain of thought approach is a method that involves breaking down difficult or complex tasks into smaller。

 more manageable steps through a series of prompts or questions。

Each prompt builds upon the previous one， guiding the AI model to think through the problem step by step and generate the desired response。

This approach enables the model to demonstrate its reasoning process and improves its ability to solve similar problems accurately。

By feeding the model questions along with their solutions。

 the chain of thought helps the model approach tasks in a structured and logical manner。



![](img/8adfe62f9283bcfe8e6639aaa553d598_5.png)

The approach is widely used in generative AI because it enhances logical reasoning and ensures that every step in the process is considered。

 leading to more accurate results。It also improves explainability。

 allowing users to trace how the AI reached its conclusion and simplifying debugging。 Additionally。

 it helps overcome the limitations of language models。

 which are not naturally designed for multi step reasoning unless prompted。



![](img/8adfe62f9283bcfe8e6639aaa553d598_7.png)

The two most common models in chain of thought modeling are few shot chain of thought and0 shot chain of thought。

 Viewew shot chain of thought gives examples to show how to break down a problem。

 While zero shot chain of thought encourages the model to think through the steps independently。



![](img/8adfe62f9283bcfe8e6639aaa553d598_9.png)

Let's consider an example to illustrate both methods。 We'll start with the few shot methods。

 The sample problem is about a store that sells oranges at $3 each with a buy to get one free offer。



![](img/8adfe62f9283bcfe8e6639aaa553d598_11.png)

The solution walks through the steps by recognizing that every third orange is free。

 so the cost of three oranges is the same as paying for two。Extend that logic。

 six oranges would cost the same as four， which comes to $12。Now。

 a similar problem is given to the system。 This time。

 the question is about a store that sells pen cases with a buy one get one free offer。

 and each pen case costs $5 using the same chain of thought reasoning。

 the system first understands the offer structure and then generates the response based on the reasoning provided as a sample example within the prompt。

 It is thus able to reach the correct answer， the cost will be $25 Since out of 10 pen cases。

 only five will be paid for。

![](img/8adfe62f9283bcfe8e6639aaa553d598_13.png)

In the zero shot method， no example is provided， and the system is encouraged to figure out the answer independently。

 phrases such as let's think step by step， or let's work this out step by step to ensure we have the right answer are added to the prompt to help the system device methods solve the problem independently。

😡，Let's take the same pen case problem and see how it is solved using the zero shot method。

 The prompt is given as follows。 If a store sells pen cases on a buy one。

 get one free offer and each pen case costs $5， How much would 10 pen cases cost。

 Let's think step by step。In this case， the system doesn't rely on a sample or example beforehand。

 Instead， it tries to reason through the problem on its own。 It starts by interpreting the offer。

 understanding that for every two pen cases， the customer pays for just one。



![](img/8adfe62f9283bcfe8e6639aaa553d598_15.png)

Then it applies that understanding to the problem。 It groups the 10 pen cases into five paid and free pairs。

 realizes that only five pen cases need to be paid for and calculates the total is $25。

 So without even seeing a sample first， the system is able to work through the logic step by step and arrive at the correct answer。



![](img/8adfe62f9283bcfe8e6639aaa553d598_17.png)

Chain of thought has several challenges to consider。

 B down responses into steps can slow down the model。

 which may not be ideal for fast applications like chatbots。 Additionally。

 this approach can make simple problems unnecessarily complex， making the AI seem less efficient。

 an error in the early steps can carry over， resulting in an incorrect answer。



![](img/8adfe62f9283bcfe8e6639aaa553d598_19.png)

In this video， you learned that the chain of thought approach breaks down complex tasks into smaller steps。

 improving logical reasoning and accuracy in AI models。

 The two main chain of thought methods are few shot。

 which provides examples to guide problem solving and zero shot。

 which encourages the model to think through the steps independently while chain of thought enhances decision making and explainability。

 it can slow down processing， complicate simple tasks and carry over errors from early steps。



![](img/8adfe62f9283bcfe8e6639aaa553d598_21.png)

。

![](img/8adfe62f9283bcfe8e6639aaa553d598_23.png)