# ExamPro《生成式AI训练营｜Free GenAI Bootcamp》中英字幕（deepseek - P7：-07-Sentence Constructor - Tech Spec.zh_en - GPT中英字幕课程资源 - BV1SFEWzLEab

![](img/cd2fdb3bd0e57fc1885afd1551069000_0.png)

All right， so we are under the Jennyai boot camp Wiiki on the left hand side under projects and we're looking at the Japanese sentence constructor。

 and this project is going to be level 100。 so we're going to walk through this document so that we are prepared for what we are going to do next。

 which is actual implementation。 So this is level 100。 This means that it's for beginners。

 The reason I market as beginners is because there is no programming involved。

re 100% using AI powdered assistance and writing natural language as we would to get a agent to do what we wanted to do。

 The goal of this here is we are building a chat agent that acts as a teaching assistant to guide students from translating a target English sentence to Japanese The teaching assistant is not there to provide the direct answer but only guidance so that is what we want it to achieve。



![](img/cd2fdb3bd0e57fc1885afd1551069000_2.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_3.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_4.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_5.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_6.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_7.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_8.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_9.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_10.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_11.png)

Now let's talk about technical uncertainty。 So whenever we're working on a project we should be thinking about what the technical uncertainty is and we want to be able to provide an explanation at the end of the time that we put into the project This is what you should be documenting and yours is going to look different from other folks because you're going to be using different types of technology on different hardware or different approaches so the information that is the outcome there is going to be different big of this is research and development you are researching as you develop things and then you're documenting those answers So here I've written what I would like you to expand upon you might add your own here as well。

 but let's go read through them so first is how well can an AI power assistant perform a very broad task So these AI power assistance they can do basically everything the question is is to what point does this thing break down or what is its boundaries of what it can do and that falls up to next question is would a very broad task be better performed by。



![](img/cd2fdb3bd0e57fc1885afd1551069000_13.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_14.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_15.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_16.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_17.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_18.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_19.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_20.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_21.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_22.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_23.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_24.png)

Dividing it into subtask with specialized agents。 So we're building a Japanese sentence constructor。

 We're basically building a Japanese teaching assistant so that when you are not working with your main teacher。

 you have something else that you can practice with。



![](img/cd2fdb3bd0e57fc1885afd1551069000_26.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_27.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_28.png)

But we know LMs the larger the larger the task， the harder harder can be for them perform。

 And so I'm assuming that we're gonna see parts where we're gonna go， oh。

 maybe this should be a smaller task or we could have took in this agent and turn it into three。

4 agents right does using AIR assistant make for a good place to rapid to rapidly prototype agents。

 So I guess the question that I'm trying to ask there。 And maybe this should be numbered。

 So it's a little bit easier for us to follow along here it switches over to numbers。

 So we're right now in number3。

![](img/cd2fdb3bd0e57fc1885afd1551069000_30.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_31.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_32.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_33.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_34.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_35.png)

But you know the thing is is that these AIP systems， they're not just vanilla large language models。

 they're not a single model， they have a bunch of orchestration underneath and so if you build something there。

 can you take what you build and replicate it somewhere else in the case that your organization wants to do direct integration which is the next question how could we take the agent we built in an AI system and reimplement it into a stack that allows for direct integration you'll notice that sometimes the way I'm word these questions are very similar。

 but I think that by having questions that are word similarly you get sometimes a different result and so I will ask a question in multiple ways in different ways as a CTO to try to make sure that I'm really getting a good answer back So we have that so how much do we have to rework our prompt documents from one AIP assistance to another so imagine we are working with anthropic cloud and then we decide oh my company doesn't want to pay for anthropic cloud it's too expensive？



![](img/cd2fdb3bd0e57fc1885afd1551069000_37.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_38.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_39.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_40.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_41.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_42.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_43.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_44.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_45.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_46.png)

Now we're going move over to Open AI or maybe we're afraid that down the road that they're going to increase the price because open AI said they're going to do that how can we take the somewhere else right and so that might be something we might want to evaluate what prompting techniques can we naturally discover discover working in the confines of an AI power assistant so you know when we say prompting techniques or prompt engineering。

 there is a lot of stuff out there a lot of prompt engineering should say a lot。

 but there are techniques that only work when you have the ability to orchestrate your LLM with other tools but we are in the confines of putting just text in a box and so there's gonna be prompting techniques that we can't do and what you find out as you work with prompt engineering is that there's just things that you naturally do and you kind of figure out you figure out the meta that kind of works for you and so that's what I'm saying is just use it naturally without having to do a ton of research on prompt engineering。



![](img/cd2fdb3bd0e57fc1885afd1551069000_48.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_49.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_50.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_51.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_52.png)

If there are techniques that I know of then I will call them out and if you do want to do research you absolutely can specifically for A power assistance。

 but it's not really complicated basically you know think about giving instructions to a person that doesn't perform well。

 you can basically iter really figure out as we work through this okay but documenting what those things that you did is very useful because you might discover some type of technique that no one's ever tried before and you're getting good results this is how the stuff works you just try and you measure the result and you know you pass that knowledge on。



![](img/cd2fdb3bd0e57fc1885afd1551069000_54.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_55.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_56.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_57.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_58.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_59.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_60.png)

We have that。 are there any interesting innovations unique to specific AI power assistant for our business goal？

 So the thing is is that these AII assistants are all trying to build their own moat right so if I use open AI。

 it actually has a voice feature that works really， really well。

 It's a voice to voice model or if you're on anthropic cloud it has projects where it's very easy upload knowledge bases。

 all these things have additional functionality that could be leveraged for our solution if we choose to do so really the reason we're evaluating this is that we're asking and maybe it's not super clear。

 but like maybe at an even more higher level， we're saying you know will AI power assistance assistance。



![](img/cd2fdb3bd0e57fc1885afd1551069000_62.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_63.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_64.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_65.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_66.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_67.png)

Replace。Real teachers， right， That's really what we're trying to get at here。



![](img/cd2fdb3bd0e57fc1885afd1551069000_69.png)

And so， you know， if there are additional features that we might want to explore with a specific one and see how far we can get with some of these tools。

 that's what we want to figure out here。 What were we able to achieve based on the AI power systems choice and our hardware or budget limitations you watching this course you're gonna be using something different than me So I can pay for a lot of these services。

 you might not be able to， you might not have access to certain ones you might have a preference to only work with open source models you might have a really powerful machine and you don't want to pay $20 to one of these things or you're just trying to use the free tier of any cloud service and doing the best that you can。

 So my point is is that we're all gonna be using the different stuff and do the best that you can do with the tools you have and report back if all you can utilize is the free tiers of these things and it's very limited and it's not a very powerful model that's fine。

 It's the information you come back with it's important。 It's not whether you achieve the result。

 It's like if all you can use is G40 mini。

![](img/cd2fdb3bd0e57fc1885afd1551069000_71.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_72.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_73.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_74.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_75.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_76.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_77.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_78.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_79.png)

And you don't have the GP401 reasoning， know the more expensive one that's paid or using Gemini 1。

5 flash， the free one then the information come back is still valuable it's just that you know the result might not be great。

 It might be obvious like oh yes， I can't do much with a free model with these ones I did list out here ama plus web UI Now technically this isn't an AI powered assistant。

 What this is it's giving you a web UI for single downloadable models。



![](img/cd2fdb3bd0e57fc1885afd1551069000_81.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_82.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_83.png)

Whereas these ones are more complex。 but like if you have a machine。

 like let's say you have a Mac M1， you download  laama， you run webui。

 which we actually show you how to do in the Jeni essentials course。

 maybe that's what you're gonna use because you can't afford these other ones。

 do whatever you can Maybe you try a Libra chat Libra chat is similar to web Ui but it is a platform that's online。

 And what it will allow you to do is just plug into anything。

 So it has a bunch of different models here。 And so maybe this actually would be a good way to evaluate multiple models at the same time。

 but these are not the same thing as the AI powered assistance。

 right these are using the open the open source models and there's not stuff wrapped around it。

 So you know I put asterisk on these because they're technically not AI powered assistance but if for whatever reason。

 this is what you're limited to because for whatever reason or it's your personal choice。

 then I'm gonna understand that it's gonna be acceptable。 There's one also called Leon。

 I didn't fully get it to work just yet， I have to play around a little bit more with it。



![](img/cd2fdb3bd0e57fc1885afd1551069000_85.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_86.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_87.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_88.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_89.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_90.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_91.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_92.png)

But this one supposedly promises that's an open source personal assistant。

 and you can plug a bunch of stuff into it。 And one really cool thing that I saw here is that it had a Gipod button。

 I could not believe that it could run a Gipod， but I was trying to install。

 It was taking too long to install。 But I might come back to this and evaluate it。

 And so this one is supposedly is an open source one。 So when I provide this list to you。

 I'm going say must be used。 I'm gonna say examples E G， but it has to be an AI powered assistant。

 Allright， So hopefully you understand AI power assistant is something that's online。

 You're not adjusting top P top K。 you're not doing anything programmatic。

 It's just whatever you can put in a box。😊。

![](img/cd2fdb3bd0e57fc1885afd1551069000_94.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_95.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_96.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_97.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_98.png)

And any wizzywig features that they have。 that's what you're going utilize。 Okay， normally。

 I'd like to do an architectural diagram and actually provide even more detailed information about what we're building。



![](img/cd2fdb3bd0e57fc1885afd1551069000_100.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_101.png)

But the problem is that if I start writing here， I'm writing the prompt document and that's not a bad thing。

 but the thing is that I want to go through this with you and make an exploratory as if we're doing it for the first time。

 now I've obviously built this before over multiple months and I found some really interesting things but just understand that this document here is a bit lightweight。

 normally I would have more information as exactly what we wanted to achieve。

 and also an architectural diagram。 but it's so simple。

 there's no need for an architectural diagram and I cannot provide those details of exactly what we wanted to do we will work our way through it and also just because you might not know the Japanese language。

 And so I want to talk about those points as we build it。

 So hopefully that is a good introduction and the next video we will jump into implementation okay。



![](img/cd2fdb3bd0e57fc1885afd1551069000_103.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_104.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_105.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_106.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_107.png)

![](img/cd2fdb3bd0e57fc1885afd1551069000_108.png)