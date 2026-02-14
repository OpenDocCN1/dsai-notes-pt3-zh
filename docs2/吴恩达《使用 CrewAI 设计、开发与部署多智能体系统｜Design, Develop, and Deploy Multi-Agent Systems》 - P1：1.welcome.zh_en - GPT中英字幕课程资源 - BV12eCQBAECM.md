# 吴恩达《使用 CrewAI 设计、开发与部署多智能体系统｜Design, Develop, and Deploy Multi-Agent Systems》 - P1：1.welcome.zh_en - GPT中英字幕课程资源 - BV12eCQBAECM

Welcome to this course on multiagent systems with Tru AI where you learn to design。

 develop and deploy these powerful systems This is built in collaboration with Joemoura at true AI one of the most important skills in AI today is how to build agent AI workflows and multiagent systems where you take a complex tasks and break it down in the subts for different specialized agents execute lets you very efficiently built fairly complex workflows In this course you learn about the core fundamental thinking frameworks that host you approach complex tasks and how to break them down into multiagent systems look at exciting examples including Core and building a deep researcher and building a meeting preparation assistant and much more delight to have Joe back with us here again to teach Thank you so much for having me I'm so excited about this and honestly there's a lot that we're gonna go over this course we're going to talk about how you can as an AI buter use。

😊，The CI framework so that you're building something that is ready for production eventually once that you're ready to bring it there。

 but we're going to talk about how you build them with agents and flows， how you track performance。

 how you implement memory how you control versions monitor traces and continuously improve how the agent loop we actually introduce a lot of features come dis course to enable like lowlel control so you can focus on the fun parts of building agent So this course is not only about identifying the use cases。

 but also building these agents and get to value as fast as you can and that's one of the reasons I'm so excited about this one of the reasons I always enjoy cha Joe about agent workflow is Joe's an early visionary that started building CI in which I'm privilege to be a minor investor started building Ci long before multiage systems was popular and what as means is the thing Joe more than vast majority of humans on this planet has seen so。

Implementations， practical， valuable commercial implementations， at scale， very valuable businesses。

 and so I know he's looking forward to sharing all those lessons with you。😊。

So I think of the basic process of looking around your life。

 your work to try to identify what are the things that are amenable to rapid prototyping experimentation with a multiagent system and then also how they use query I to quickly build a prototype and whether the tools this an MCP service web search all the way through when you have something that works。

 whether the lessons to take that prototype which may run great on your laptop to scale it to thousands or tens of thousands or more uses。

 hopefully without too much pain in too many pitfalls along the way10 percent and I think you got the nail in the hand there where literally as you're building these use cases。

 what make them interesting is the fact that they're non-deterministic is the fact that this agents can tap into so many different sources so they're not only using cognition but they're also have this ability to selfheal and to react at anything that you throw at them at runtime but that can not come at a cost of not giving you reliable。

Repeatable outputs so that's something that you should watch for。

 So in this course you're gonna learn how tore building blocks for these moyag systems。

 including not only agents tasks and crews， but you learn how to customize and optimize their agents with memory tools including MCP execution hooks and guardrails you also learn how to add a layer of lowlel control with Ki flows in states that allows you to not only task your application using metrics but also inform you how to even train your agents using human feedback and improve your application over time and in the final module。

 you've also hear from several companies that have been using moyag systems and createi and production So even if this is your first time working with agents or createi you get a lot of the course and if you took or earlier courses partnership with the learning AI I think of this like a phase3 where you're building these things not only for scale but quality and reliability。

And I'm very excited about that。 So one of the challenges that I know you spend a lot of time thinking about is reliability very often we can build a quick and 3 prototype for workflow it works in demo for that one input we try on our laptop maybe it works well for 10 inputs。

 but then you go from 10 different examples to0 in production to0 does this mean that well it 80% reliable it doesn't really work it turns out that for teams that know how to drive agent development process。

 this agents only work in demo only the time the loss of two is to breakthrough that10% And what we have seen is that there's a spectrum of things that you can do in order to improve the agents and in order to improve the reliability that you're getting from usingi training to use guardrails to usei testing the way to actually find2ium model we really want to go there So all that goes into agents memory and we're gonna talk all about this throughout the course。

 So it's very。😊，The gen is not get it back in the model if anything people are going to use more agents every day。

 but in order for that to happen， there needs to be at least three main things One is needs to be extremely easy to boot and we're going to talk about how you can easily get this agents built out and needs to be trust worth it that goes back into this idea of reliable and repeatable outcomes and also needs to be manageable so you can get to scale eventually and the scale is not only about running a median agents in an flower it's about making sure that you're building this building box that can be reused so you're having your custom tools to be reused across many use cases or even your agents themselves and that's very exciting about this course I find that having that discipline process building your multiagent system and then thinking through what are the observability mechanisms so that you can figure out when it's working is not working and then also to drive that discipline process to repeatedly。

You quickly identify the errors and then fix it with some of the tools be a prompting fine or something else that is hardly a more reliable recipe than most people realize。

 which is why with this set of knowledge is actually not easy but pretty easy than is's widely appreciated to build pretty reliable multiagent systems Now there is a lot of buzz and a lot of hype about agent AI and about multiagent systems and with all this buzz and noise。

 what we want to do was get together to create a definitive course on how to use QI to build multiagent systems so that when you finish this course you understand whether the cold building blocks。

 whether the mental frameworks， how to put them together and then also how to go all the way from prototyping to taking your multi-agent system to scale and there do a very powerful skill that I'm confident will let you build a lot more stuff than was possible before。

And having known Joe for a while， I can promise that this course will also be a lot of fun。

 and I'm excited to see what you build with this。 So there's a lot to cover。

 Let's go on the next video and get started。😊。