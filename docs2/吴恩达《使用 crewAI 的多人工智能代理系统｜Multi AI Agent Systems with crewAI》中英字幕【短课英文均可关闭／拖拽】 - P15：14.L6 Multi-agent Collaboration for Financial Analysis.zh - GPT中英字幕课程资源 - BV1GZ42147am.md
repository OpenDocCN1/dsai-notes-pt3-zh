# 吴恩达《使用 crewAI 的多人工智能代理系统｜Multi AI Agent Systems with crewAI》中英字幕【短课英文均可关闭／拖拽】 - P15：14.L6 Multi-agent Collaboration for Financial Analysis.zh - GPT中英字幕课程资源 - BV1GZ42147am

Alright， so from the gap go， I'm going add some of our boil plate tone where I'm going import all the tree classes that we care about。

 the agent， the task and the crew。 Now we're also going to be using Serer for this So I'm going make sure that we are using GT for Trbo and that we're also using our Surper API T。

 you're going to be provided with oneer you can also just get one from their website they do offer free credits So we're going to be using two toolss here。

 The search2 and the Sce2 So we already have used those toolss in other examples。

 So we're probably familiar with that。 The search2 is allows your agents to search Google and the Sce2 allows your agents to look into one of the URLs that it finds and kind of like extract all the content out of that。

 So now that we have our two set up let's create our agents and we're going to use for agents here。

We're going to have a data analyst agent responsible to analyze the markets trying to find good opportunities for us to invest on we're also going to have or trading a strategy agent here that is going to look at those options and kind of like weigh in what are the movements that we should do regarding any stocks then we have the execution agent。

 This is the one that really thinks about the timing， the price， the entry points。

 it's going to help us set out that and then the final one is the risk management agent This agent is basically making sure that we understand the risks of buying the stock and balancing things out So again。

 this is not a recommendation investment in any shape or form is just one example of how you can use multiple agent systems to also interact with financial problems So we wrap upgrading more agents and we are ready to create our tasks。



![](img/fdddacce10a1834d4ab590dc79b82ca3_1.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_2.png)

This is not a financial recommendation in any shape or form。

 but I have personally seen in working with companies。

 even Fortune 500 companies that are actually doing risk analysis and financial analysis using crew AI to look through financial documents that are public and private in order to understand how are those companies doing So this is not a farfached when what people are actually building out there with that said。

 let's just start creating our tasks or first task is the data analysis basically monitoring the market trying to find good angles。

 good stocks that we could use the second one is the strategy it's once that it knows what is your tolerance to the risk and what is the stock selection it can decide on how to move on some of those stocks The third one is the execution task that's the one that is going to make the calls around the pricing the entry points the right。



![](img/fdddacce10a1834d4ab590dc79b82ca3_4.png)

Timing and now that And then the final task is the risk assessment task that wrap things up and make sure that it's taken into account the risk before making any recommendations。

 So now that we have created all our agents and tasks we are ready to put our crew together。

 but you're going notice a few few different things in this crew。 First thing。

 you're going to notice that we're importing a new class called process this process class allow you to basically set a different way for our agents to work together。

 you can see how we are using here when were creating our crew by setting this crew to operate higher artally by doing that we're going to have one manager that is going to delegate the work to the agents to perform their tasks So this agent it's going be a manager that crew I will create automatically for you。

 So in future versions of crew， you're going to be able to set your。



![](img/fdddacce10a1834d4ab590dc79b82ca3_6.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_7.png)

Manager yourself and you're going to be able to pass this agent as the manager agent。 Meanwhile。

 you can set what is the LLM that this agent will use and crew AI will create this agent for you internally so you don't have to worry about any of that。

 So in here you can already see some of the differences between using the regular sequential processes And now the hierarchical process。

 So let's create our group。Now that we have our crew ready。

 we can work on what inputs we're going to be sending to it So if you look through our agents and tasks and declarations。

 you're going to find a few variables namely the stock selection。

 the initial capital or risk tolerance or trading strategy and also use impacts so we can set all that from the cap go to make sure that we can use it when we're kicking off or crew and I would say feel free to kind of like stop the video offer is and play around with some of those numbers。

 bring your stocks， the stocks that you care about play around with the initial capital play around with the risk tolerance。

 make sure that you can really see how these agents behave differently given the different inputs that you can send to it All right we're ready to kick off the crew in order to do that we basically call the kickoff method and pass our financial trading inputs to it。



![](img/fdddacce10a1834d4ab590dc79b82ca3_9.png)

Let's do that from the Gago you can see that a crew manager kick things off so this is crew AI inner manager。

 It creates this manager automatically for you and it's going to use this manager to delegate the work around so you can see that it startss by delegating the work to the data analyst so that this agent can do some work around find information about Apple Inc from that point on it's gonna to keep delegating work to all the different agents up to the point that it completes all the tasks and give us a fully fld report on what we want to accomplish what are the moves that we should do what are the right values to get into the stock or whatnot So let's take along this execution you can see that the data analyst then decides to do web search for the current stock price and volume and when doing that it finds a bunch of results among the results it finds the Yahoo。



![](img/fdddacce10a1834d4ab590dc79b82ca3_11.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_12.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_13.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_14.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_15.png)

finin this links and decides to dig into that it reads the website content by using our author too in order to get all the information from the Yahoo website from that point on。

 it now knows what is the Apple's innc and the actual value and the close value from April 24 and also understands everything about the stock that it was able to extract from the Yahoo finance Now that information goes back to our crew manager that will decide what to do next in this case it's delegating work to our trading strategy developer and you can see how it's passing some of the information that it learned about the Apple stock price。

 the increase on the after hours， everything that the previous agents learned it's now being sent to this new agent and all of that is being coordinated by the crew manager that is autonomously delegating the work so you can see。



![](img/fdddacce10a1834d4ab590dc79b82ca3_17.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_18.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_19.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_20.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_21.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_22.png)

These agents now actually go for trading strategy insights。

 trying to kind of learn a little bit more about how Apple is doing and then he decides to look into a specific website itself in order to extract information from that so you can see throughout the execution how this pattern repeats where like the agents who learn through research and digging into this websites information about the stock and the company and send that back to the manager and the manager kind of decides where to go from there to the point that it completes all the tasks that we want to complete So let's tag along and see what the final result actually is So you can see through this execution how a lot of delegation is happening the crew manager keeps learning through all this delegation and delegating even further to now delegating where to the data analysis asking to provide analysis on the recent market trends and price movement。



![](img/fdddacce10a1834d4ab590dc79b82ca3_24.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_25.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_26.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_27.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_28.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_29.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_30.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_31.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_32.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_33.png)

So you can see that throughout our lessons we have been building more complex crews we started with simple crew to write an article and now we're building fully flged crews that are able to do stock researcherses and risk analysis and look into websites that extract information and delegate work and do work in parallel there's a lot going on there and this is honestly super exciting because it open up so many opportunities So I would definitely say play around with this make sure to play with some of the attributes change some of the crews change some of the agents and tasks make sure that you build something that you find valuable and give it a try and share it online people are super excited to see why people are building with crew AI and multiple agents nowadays Allright so our crew finish it and the task output is the comprehensive risk analysis report for Apple trading。



![](img/fdddacce10a1834d4ab590dc79b82ca3_35.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_36.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_37.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_38.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_39.png)

Strategies so you can see that it kind of like started with an overview and it mentioneds that you should utilize a technique called 20 day and 200 day SMma So you can see that throughout the execution and we kind of like scan them because it's a longrun crew but throughout the execution it learn about all those different market trends and ways to kind of like assess the risk and decide what is the best entry point but it mentions things like RsI or MAD either to identify potential to enter the market it also mention like for you to establish stop wins and stop loss as a way to also do risk management identify some risks mentioning that you should be watched for it also mention operation challenges and also mention market volatility impact So how can that impact your decision in there The conclusion is that you have a good strategy。



![](img/fdddacce10a1834d4ab590dc79b82ca3_41.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_42.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_43.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_44.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_45.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_46.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_47.png)

To basically invest in Apple， however， you should be careful about how you deploy it so you can see in here that the result just kind of like more of a review。

 there is a lot of go during the execution that we could dig into and it did offer some recommendations on how we should try to think about entering this this stock specifically and how we should analyze it。

 What I would invite you to do now is pause the video and play around with these age this are very complex crew It has a lot of moving pieces is using the hierarchical process so play around with some of that maybe make it sequential see what it changes。

 maybe remove some of these tasks or maybe change some of these tasks that it's likely to see what you can get out of it but this is a very interesting use case on how you can use crews to do throughout analysis on stocks and links and text and methods it's very interesting group to put out together。



![](img/fdddacce10a1834d4ab590dc79b82ca3_49.png)

![](img/fdddacce10a1834d4ab590dc79b82ca3_50.png)

All right， so let's go back to our slides real quick。



![](img/fdddacce10a1834d4ab590dc79b82ca3_52.png)

So by now， you have acquired a complete understanding of how MuT agent system works in all of their components。

This is more of a simplistic representation of crew AI specifically。

 but this is very similar to what you find on other frameworks out there you have crews。

 you have the agents， you have dos you have the processes you have tasks and the end goal is to produce a good outcome out of that so you probably learn all the moving pieces and should feel ready to start putting more complex crews together so on our next lesson we're gonna put together a more complex crew that you can actually start using today and that can help you find your next job opportunity so I hope to see you that and congratulations on other progress so far make sure to try things out instead up jumping straight the next lesson make sure that you play with the Jupyter notebook and I see you in a second。

😊。

![](img/fdddacce10a1834d4ab590dc79b82ca3_54.png)