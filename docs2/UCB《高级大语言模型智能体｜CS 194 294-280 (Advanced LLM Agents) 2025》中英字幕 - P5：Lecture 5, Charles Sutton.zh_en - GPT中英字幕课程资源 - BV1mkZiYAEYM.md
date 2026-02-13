# UCB《高级大语言模型智能体｜CS 194 294-280 (Advanced LLM Agents) 2025》中英字幕 - P5：Lecture 5, Charles Sutton.zh_en - GPT中英字幕课程资源 - BV1mkZiYAEYM

The introduction， let me start just by before I get into the technical content。

 let me say good let me I'll introduce myself。

![](img/45e47edbfdb513df96f2c25bfc77cbd4_1.png)

So so my journey is like has Don said， I did a postdoc at Berkeley from 2007 to 2009 with Mike Jordan。

 which was fantastic back during my PhD what I worked on was machine learning deep learning didn't exist then and for natural language processing so back when none of this stuff really worked and then around the time I kind of I left Berkeley I started as a professor at  Edinburgh。

 I started working on kind machine learning for program synthesis。

 kind of cogeneration and software engineering problems these were very exciting to us at the time。

 but this is when we' just starting to get deep learning so kind of none of this worked and then I moved to Google in 2018 and it's only kind of very recently and when I've been at Google I've been working on machine learning for code generation and then kind of very recently like in the past year I've started to get interested in AI for security so why am I telling。

This theres kind of three reasons one is I always like to begin a lecture by professing my ignorance so my background is very much more on the deep learning side than on the computer security side so you're very welcome to ask me any questions you want about computer security because fortunately Don Song is sitting in the front row and we can get and many of group as well so we can get kind of expert answers to a lot of these questions even if I don't know them and the other。

Thing iss just like I like to have career advice。 I have a blog where I give people kind of defunct career advice and research。

 And because， you know， it's fun。 And the one thing when I look back is that， you know， I mean。

 your career is very long， right， if you see like in the past couple of years。

 like things are feebrile， you know， everything's changing every three months。 you know。

 it's not the technologies that are on top now， you know， they're not going be on top in five years。

 might not be on top in five weeks the way things are。

 So like having kind of just like change is normal。😊。

Knowledge is change and you want to learn how to change with them and the other thing that I think I is a。

Theme of this talk and something that I like the course is kind of like thinking across different different disciplines。

 right， So if you are working in machine learning， if you're working is sometimes applied research or product different research or in。

Or if you're in tech building products， a lot of there's going to be the kind of machine learning tech。

 And there's also going to be the problem that you're trying to solve。 And if you。

 if you know only the machine learning part of it and you don't think about， oh。

 kind of deeply about what。Prool you of trying this。

 you're kind of missing a trick like the more you understand the kind of AI for computer security。

 the more you understand it about computer security， or if you're building a product。

 the more you understand about where your customers want， it'll help you to do better technical work。

Okay， so that's the end of my sermon and now I will start actually talking about kind of coding agents。

 So there's going be three parts。 I'll say a little bit kind of in general about kind of agents for code like sweep Bench Sw agent type things that'll be the first part of the talk。

 then I'll start talking about AI and agents for computer security And then at the end I'll talk a little bit about。

Project that Da mentioned that I'm part of with a number of other people。

To do L agents for finding security buds and so but I'm going to start off with so I'm going to start off with being maybe a little bit philosophical about what LLM agents are since you're already partway through the class and you've already seen a number of examples of agents I wanted to give like LLM agent is a bit of a buzzword。

 So so I wanted to give kind of my perspective on kind of what that buzzword means other people would say potentially different things and that's okay。

 but this is kind of what I would emphasize in terms of what seems kind of fundamental。

 So I would say the so kind of this slide's a little bit abstract I'll talk start I'll start talking about actual stuff in a few minutes and one more slide。

 But for me if you asked me to define what an LM agent is without the kind of buzzword bullshit。

 whatever。 I would say look it's a multiter LLM was。

Right the final thing is kind of this react loop that we're going to talk about。

And what what makes this fundamental like why is this good one is that you get dynamic computation time So the point of like if you just give。

 if you just prompt an LLM question answer， it has to start generating the answer right away and maybe some of the earlier tokens kind of commit the LLM to an answer that it then has to like that it doesn't want to contradict。

Whereas if you give it kind of dynamic computation， if the LM can generate a thought。

 whether it's kind of a reasoning model or whether it's just prompted。

 that gives more computation time for harder problems。

The other thing which we're going to talk a lot about is kind of information from external tools。

So and that's kind of another part of the point of agents is that you can actually。

 oh I'm going to is that for example en codingding agents， you actually run the code。

 see what happens and and then write different code based on the output and it turns out that's incredibly powerful for kind of more complex code generation tasks。

And we'll see examples of lots of other things you'd want to use external tools for in a in kind of code generation software engineering type scenarios。

 The other thing that's maybe more from the。More from the kind of cognitive perspective of what's interesting about tool use is that tools give the agent the ability to test hypotheses。

 right， so the agent can like in the thinking part of a loop， say， oh。

 I think that when I run this code on this input， it will break it line 13 and they can actually do it。

 see if it was right and then kind of revise and later turns。

 like say something different if it turns out that this hypothesis was wrong。

And then and I think that's something we're kind of for some of these simpler tasks。

 you might not need that level of experimentation in the agent， but I think for more complex tasks。

 you will。And then the final thing this gives you， which I think is really good is like if you want the element to actually do anything。

 right， then it needs to interact with the external world and that's in one sense。

 that's what a tool is giving you。So the I guess so the main thing。

 maybe I disagree with what I wrote on the slides next like so you could think of when people talk about planning or chain of thought。

 you can view these as like special cases of dynamic computation type right。

 These are ways to use the extra computation that you get from having thinking tokens this de emphasizes multiageent a little bit's you know maybe that'll turn out to be really important to have different interacting agents with different prompts。

 but I think the you know my sense is that that's still emerging。 The jury is still out on that。Okay。

 so that is， okay， so that's the， that's gonna be the end of the philosophy for now。

 I'll inresperse philosophy。 maybe into the the rest of the the lecture。

 I'm going to start by not talking about agents。 though。

 I guess I've already started by not talking about agents。

 I'm gonna continue starting the agents lecture by not talking about agents。

 And the next thing that's not agents that I'm going to talk about is evaluation。

So so the reason that the reason that I'm doing that will become kind of I'll talk about that in a minute so before when we first started to see big but I let to talk a little bit first about say the prehistory of evaluating code generation in LLMs so when we there there was a big kind of moment in I guess four years ago now doesn't feel that long。

 but it was when we kind of saw a step change in the ability of LLMs to do code completion in cogeneration tasks。

 this was about the time the open AI codeX model came out kind of the GT3 kind of iterations and at that time there were a couple kind of evaluations of kind of code generation capabilities the people were doing at the time。

And EP that we did at Google and kind of human Eval from Open AI。

 and these are kind of broadly similar things。 And what these are is basically natural language to code。

 So these would each of these data sets would have。

 you know order several hundred examples where you would generate a small Python program。

 five or 1 lines of code and you wanted to do that given like a one or two settings prompt that says what the code is supposed to do and a series of assertions。

And at the time this was you know at the time that this came out like I'll say more later and these were both kind of generated by people so there were kind of human annotators kind of wrote the programs and the problem descriptions so I don't recommend using these evaluations anymore。

 they're kind of more like MNT but I think they let me talk about a couple of points that's why why I'm starting with this one and at the time that these came out it was kind of amazing that a language model could generate you know an entire function of 10 lines of code right that's not amazing anymore。

So one thing that's interesting about this I'll come back to later is I want to talk about kind of both how you would use these to do evaluations and why you don't use them anymore so we talk about how you use them to do evaluations so what we would do for these data sets is we measure pass K so how often given the kind of natural language prompt do we get a correct answer in k samples so if you go if so if you take if you like my fancy AI generated graphic there if you take a prompt and get say K samples from the model and just say kind of run the all on those a set of assertions that maybe the model the ones that model did see maybe a few hidden ones。

 the model didn't see and then say okay how often does the program pass those assertions and then if any of them pass you get a score of one for pass K for this example so the reason I'm telling you is this is there's some principles of this that even though we don't use MPPP。



![](img/45e47edbfdb513df96f2c25bfc77cbd4_3.png)

Even eval anymore you probably shouldn't there's some principles of this that you do want to use when you divine evals one is that this requires an automated correctness check to work having that。

If if it's all possible for you to have that when you're defining an eval。

 you want to have that the other thing that's kind of nice about this。

 you don't see this as much in agents because it's so much more expensive to run is that you get to measure kind of explore exploit behavior if you can afford to do a pass a K eval right so if you had a model that like always produced the correct answer it was either always right or always wrong and theres no diversity in its output it's kind of pass it one would be the same as pass a K whereas like you know if pass a K kind of goes up sharply that's telling you well maybe the model's first solution is always correct。

 but it's giving you more diversity that's kind of interesting。

The other thing to point out here is kind of an interesting question like does pass K match what you want when you deploy the model and the answer is sometimes yes and sometimes no。

 if you are doing code completion， you probably don't care as much about pass K because I'm not going to show every time I hit the completion button you get to see 10 examples and pick the one that's right。

 that's probably not so good whereas if you're doing something more agentic it might be it might be fine it might be perfectly fair to say。

 I mean， it is perfectly fair to say oh in production。

 I'm going generate k samples keep the ones that pass the test cases and only show say a highly ranked one of them to the user。

 So sometimes this is this kind of reasonable sometimes it's a good metrics sometimes it's not So it's always interesting to think about for this particular way in which I'm evaluating a coding tool。

 does it match what the way I'm actually going to use it in production。

Okay this is maybe not I just putting this because I think it's cool it's a little statistical aside which you may or may not know。

 And since like machine learning used to be based on statistics。

 you see less of that work anymore I find it kind of interesting So if you are so how do you want to compute like say I care about past it 10 right how am I going to compute that well the naive thing you could do is I could say well take 100 samples from the model and say。

 okay what percentage of them actually passed So maybe it's 20% and then what I want to know is if I take 10 samples from this how much does it how likely I'm going to get it and so you could take 20% and plug it into that it turns out that's bad that's a really noisy statistical estimate So it turns out it's much better to say take those 10 samples and then say if take those00 samples and say if I take a sub 10 without replacement right how。

How often do I get at least one success and that's that's the estimate of this proposed in the Codex paper where they talk about human evil。

 I don't know， I just think that's cool。Okay so now let me so I've gone through this at length and the reason that I've gone through this is to get to this slide which is like what is the design of a good evaluation for coding agents or for agents in general and in 2021。

 I think these were probably reasonable evals at the time and there were kind of three and the reason is that they could drive model development the reason is the reason they could is that they were kind of just hard enough so they're not floor they're not at ceiling so that when you improve the base model you actually see a difference in these numbers and then at the time they kind of weren't leaked so they weren't already on the internet now probably not right they kind of too easy it's kind of too easy to over you could overfit to the assertions and they're certainly leaked So these are probably more like the Mist of code evals now the reason I go through this is when we look at other evals we can ask kind of the same same question so probably most influential so far kind so let's now。



![](img/45e47edbfdb513df96f2c25bfc77cbd4_5.png)

move to evaluations kind of used for agents so the most influential evaluation has been Sbech so let me kind of talk which I didn't maybe I have the citation on a different slide but it's easy to find is so what Sbech is a way of kind of generate it's a data set of real world coding problems that have been collected from Python repositories on GiHub so one example of an example from the data is here so the idea is that they would talk about filtering on the next step so so the idea is you would have a problem statement which is actually from kind of the statement from the GitHub issue tracker this is one thing I point out here is just kind of the issues will often contain kind of corners to a part of the code or that you want to modify and all of these examples have。

Have test cases that were part of the patch。And there's cases for which before the patch。

 the test case fails and after the patch the test case succeeds。

 so you have for each of these you have kind of a test case， you have an issue description。

 you have a change to the tests and you have a patch and so the the goal the of Swnch is generate the patch from the generate the patch from the description。

And these are okay， so I've talked about so there's some steps of filtering you do like its this fail to pass filtering and also the fact that you can actually install and run the projects。

 and I wanted to show in terms of looking at the domain。

 So so this has been kind of very influential because at the time that it was introduced it was kind of at the Goldilocks level that the kind of baseline LLms。

 we're getting like2 or 3%。 And then as soon as we switched agents we got kind of nontrivial boost So this was kind introduced it's kind it was interesting subset of real world tasks that was introduced just at the right time where this could drive model developed And so it's kind of been very influential。

 a lot of people have used it。 what I would point out from the things in the bottom is on the left is kind of a pie chart of which 12 projects these came from and you can see there's kind of like it's kind of a small。

Of domains right， These are Python packages that are kind of， you know， mathematical data analysis。

 you know， web right So there's kind of a。It's not covering the full range of software engineering tasks。

 but it is covering tasks that are interesting。嗯对喂。And to look at。You know， the set of files edit it。

 the set of functions edit it is kind of a big step above previous evals。

 but there's a lot again that it's not covering。

![](img/45e47edbfdb513df96f2c25bfc77cbd4_7.png)

The so there there's also and then there's also a kind of a small so one thing that's both kind of nice and not nice about this is that you have the issue descriptions that are that are coming the issue descriptions are the ones coming from GiHub so that means that you know sometimes these are under specified or their test cases that are just somebody was they're tangled somebody was fixing something in the code they wrote some more tests。

 but it doesn't actually test the problem so there's a subset where these have been where these have been removed。



![](img/45e47edbfdb513df96f2c25bfc77cbd4_9.png)

So now let me pop up and say， okay now let's ask the same question that we asked of the previous slide which is are these Ebes good and the answer is well。

 yes yes and no right so as we said this is a significant step up in realism and it came at the right time to drive the fields that's great what's wrong with it there are lots of things that are wrong with it。

 that's okay there are lots of things that are wrong with everything so what's wrong what's wrong here is that you know you can overfit to the test right the tests aren't an exact verifier so you can produce a patch that makes the test pass but isn't actually correct maybe even something word's been a little bit more is the natural languages out of domain in the sense that if you are interacting with an agent in your IDE and you want to tell it to make a change you're probably not going to use the same types of natural language because you would in a GitHub issue description right like maybe you've diagnosed the problem a little bit more if you're going to share it with other people。

And if you're just asking an AI in your IDE please fix this and might and some issues might going contain things about the solution right about what part of the code the issue should be fixed sometimes you know that sometimes you not and so we've talked about coverage a bit already and we've talked data leakage is you know when this data set came out a lot of people were kind of worried about oh these are all from Github this is in the training set of all the large models should we be worried about that and I think the answer is when systems are getting 2% on S benchch。

 no， we should not be worried about that when systems are getting 50% we probably should。

And then the other thing， whenever you do these kinds of historical data sets。

 I think something that people often don't realize is these commits are tangled。

 it's kind of often the case and therere on open source repositories that commit will not just fix the one issue that it claims to fix。

 but it'll do some other things like maybe it fixes another issue。

 maybe it does some other cleanup right so that kind of affects the quality of it certainly affects the test cases。

 but it also affects like if you're going to do supervised fine tuning on patches that might not be might not be such there's problems with that。

Okay， so the reason I'm going through this at such length is that I think in large part the quality of either the base LLM or the agent that you develop is going to be driven by the quality of the evaluation and the reason for this is I don't know。

 sometimes I like making analogies to statistical machine learning methods any kind of organization that builds either LLMs or LM applications it's just doing giant combinatorial optimization right。

 so you have you have a design space。 you have a bunch of knobs like we'll talk about the knobs for agents in a minute is and you are。

And you say okay， what if I what if I set this knob this way， what if I add this tool。

 what if I change the system instruction this way， what if I clean up you know this part of the post training mixture and then you try it and you see how the numbers change so if your if your numbers aren't good your' hill climbing on the wrong thing and I think that has a direct impact on how whether the quality of your evaluations has a direct impact on the final system。

 whether it does what you want。And so the things you want to think about are like， you know。

 some obviously like， I think the main one that seems to be a level of difficulty。

 you have to be in the sweet spot also you want things that are realistic that test what you care about and。

That aren't leaked be leaked and the other thing like all evaluations have a shelf life right like once they start out you're kind of they start out like with say MP human eval。

 they start out being kind of hard and unleaed and then like a couple years later。

 they're easy and leaked so it's just like you have to keep making no ones continuously。Okay。

 so I hopefully I've spent enough time so I am kind of going into kind of。

 you know technically simple stuff at length， but I think it is important to actually building these things so now I can actually kind of talk about code agent which is kind of a good thing to do in a lecture and codingding agents。

And you know， one that I thought was kind of kind of a particular milestone was。

Swee agent so this was kind of one of the early ones that was kind of specifically designed for s benchch style tasks in some sense。

 in some sense this talk is going to be very repetitive because I think that we're all working with the same set of three or four ideas right in the kind of the base models or in the kind of you know application layer on top of it。

 which an agent is an example of this。Like crank and there's a certain thing like if you want to do an agent for I don't know you fixing AV issues versus an agent for kind of making patches to repositories。

 it's going to be a lot of the same types of engineering that you do first thing going to do is define find an eval and the second thing you're gonna to do is kind of create something that looks like sweet agent so what Sw agent is it combines like a bunch of different things that kind of you know people have all done kind of before but it's going of a powerful combination so one is that it's going to give you thatre we're going to instruct the model in such a way that it does kind of chain of thought in the sense that it explains what it's going to do before it does it there's going to be a set of tools that are specific。

Software developed and the agent is going to get execution feedback。 So that way。

 like I've said before， if if you have if you you can get information about what happens。

So the main loop， which is is going to be kind of what I call the react loop and I put those emoji on there for a reason。

 react loop from the react paper a couple of years ago。

 oh because I think this kind of loop is it kind of at the heart of what it was saying about agents of kind of this idea of kind of chain of thought plus tool use so all you're doing is basically it's basically like a very simple loop where you say you at every point you have what we call a trajectory right some text that the LMm is generated so far at every step we ask the LM to generate more text and then that text will end a tool call in whatever format that you like and then you get the tool call you actually run it every tool is basically to a first approximation of Python function that output puts more text like I'm not going to talk about multimodal agents because we don't really need them for there's been less work on multimodal agents for code so far。

And then whatever the output is you just append to trajectory and then you repeat right and that's that's that's it so the and this this kind of loop we'll talk about alternatives to this kind of control flow as well。

 but that loop alone is kind of very powerful it's at the heart of a lot of what these things are doing。

And in principle the LLM can generate whatever text that it wants right。

 we would hope that it's something that actually helps it decide what tool call to use。

 and so we instruct it， you know it's a system instruction in the beginning。

 I guess I should have initialized this with what we call like a system instruction and that's going to tell you that says it。

 please explain what you're doing and so then it will。😡。

So the one of the main design decisions here is like， well。

 what tools do you want to use one option that you could imagine is okay。

 we'll just give the agent access to a Linux shell and an IDE。

Then a person can do on that on that machine， you can write whatever code it wants。

 This seems I'm not saying this will be true forever right now。

 this still feels a little bit futuristic right you know， two weeks from now。

 who knows right but and this is kind of another theme when we talk about the design of agents。

 maybe this is one of the things I forgot to read on the slides is that the design of the agent harness and the tools you have to coesign it with whatever the model can do right so when you're doing if you're doing prompt optimization to try to decide okay how do I summarize the output of this tool well。

 probably the way you're doing it is you're adapting either knowingly or if you're part of the or unknowingly。

 you're adapting to whatever the model is seen post training data right because the more the closer like you want whatever format to use to be things the model is familiar with。

So where we are now is like okay maybe right now option one is a bit ambitious so let's do something different let's make things easier for the model so what we'll do is we'll say we'll design tools in such a way that there's going to be a small number of them that are kind of that are kind of good for this task and they'll have out inputs and outputs that are friendly。

To the agent and there's kind of a really catchy term they use in the Sw agent paper。

 this is like an agent computer interface instead of a user interface。

 so instead of HCI that be a science of HCI， that might be going a bit far。

 but there are design principles here。

![](img/45e47edbfdb513df96f2c25bfc77cbd4_11.png)

So so what are they doing in Su agent oh okay yeah before I get to that so like I said。

 a tool is just a Python function or a code that the agent can call and to get a string from the context what do you want what do you want these things to do is when you're thinking about them well they should be easy to describe to the agent right so you don't want to like make up technical terms right that like if you're writing when you're designing a piece of software you can invent vocabulary。

Different objects and the thing here like you want like the closer you I've heard this。

 I think some of the the guys， I think I heard this from the people who developed copilot is so there's a lot the initial probably still but certainly the initial version of copit there's some really clever prompt engineering to make things work with the LM of that time I'm sure this still is and one thing they talked about。

 they call it like the little red Ridinghood principle right that when you're doing prompt engineering。

 you want the you want to kind of lead the model down familiar path。

From course training data and I think that's I think that's true here as well that you want kind of to be able to describe what the tool does in a way that the agent will have understood like there are plenty of web pages that talk about talk about goat jump to this line of code right that's something that's natural。

The other thing is you want the agent you want the actions to be compact right like you don't want something where the agent has to call four or five tools to do one logical thing the other thing is you design the output of the tools right so you might say you know it might make a difference how do you handle trailing new lines in the output of some tool or if the output if you're doing a code browser tool and there are many。

 many results like how do you summarize that like different those different options and and the other thing you want to think about is a guardrails is like state so like if you're talking about code editing right then you know you could imagine something where say the agent adds the first thing the agent does is add a stupid syntax error to some file and it doesn't realize it and so then the rest of the trajectory the agent is just messed up because no matter what it does it hasn't fixed a syntax error right so you want to kind of try。

To have some error checking to avoid， especially for like stateful tools like code editing。

 getting the agent into a state bad state that's easy to get out of。



![](img/45e47edbfdb513df96f2c25bfc77cbd4_13.png)

Okay so so what tools do they have in Su agent one is well I think they did have a Linux shell。

 but that's maybe sometimes useful but not so useful but often like these tools are helpful I would say there's like three types of tools you could think about in kind of agent in this style of agent one would be kind of information gathering that doesn't help the agent solve it gathers information right in the case of in the case of code this would be kind of doing code search and kind of viewing code files so you can so this would be and so you see some of the design like like this would be things like oh find this term in this file find this term na file in this directory notice that it's kind of a nice shortcut right you could imagine having just doing LS in the Linux shell and then doing then the agent could do search file in any of these。

That seems cumbersome， right？And then， you know， how do you deal with files that are too long for context here。

 what you can do is call the open open to see part of a file and then have a specific kind of scroll commands。

Um the so the second kind of thing going to do is acting， right， which is just in this case。

 you know， make edits or create new files and then you can get feedback by saying， okay， I'm done。

 please submit the patch。So and I think in general， if you want more complex tools。

 I think most tools will kind of fit in to some kind of to fit into this， you know。

 there are guardrails here that like， you know， if you make a dumb edit that。

Kind of untax error a lender error， it just gets rolled back for you so and you can do there things like this。



![](img/45e47edbfdb513df96f2c25bfc77cbd4_15.png)

So I mean， give you a sense of kind of what the I couldn't fit a full。

 I will show some trajectories throughout this， I couldn't fit a full Swage and trajectory on here the but here's kind of an example of the kind of explanations you might get right that you say。

 okay oh now I know what to do we need to add a check to ensure that all of these things are the same let's edit the code and so it says oh。

 replace these lines of code with this。Um theum or if you want to do like a kind of file search。

 you might perhaps you want to， u u， you know， you might like lead the lines。

 you might provide line numbers like these are kind of like you need the line numbers so that you can use them in a subsequent command。

So you can design the tools to kind of fit together in this way typically what you will see for this agent。

 you would typically see the tools are called in the order that you would expect like if there are some identifiers used in the issue description。

 then the agent can call the code browser tools to find kind of code that's relevant to it at some point one of these thoughts will say。

 oh， let me make this change and you see edits and then you might see like kind of multiple edits and then a submit。



![](img/45e47edbfdb513df96f2c25bfc77cbd4_17.png)

but the agent is restricted to do that right this is just as far as the model is concerned。

 there is just a string and the model is continually appending to this string。



![](img/45e47edbfdb513df96f2c25bfc77cbd4_19.png)

So okay， so let me say I'll say a little bit about the results and the Swbech data。

 So the first thing is I did kind of sit up and say。

 well sweetbech was really hard when it came out and so if you look at you know whatever the state of the art LLMs at that time and say what percentage of the I think a couple thousand issues in Sbech were resolved by the model。

 it's like one or three% and I can do tell a kind of fun。

 I don't know it's fun for me I don't know if it's fun for you story there。



![](img/45e47edbfdb513df96f2c25bfc77cbd4_21.png)

Which is that when Swwebech first came out， you know。

Thought it was kind of thought it was a pointless evaluation because it was just too hard like how do you he climb on a model when you're getting one or 3% so it turns out I was wrong and the reason that I was wrong about that is because it because agents are actually really good so like when you put an agent loop on top of the space models you go from like 1% to 12% right and I think now now the state of the art in full sweep benches is quite a bit higher than that。

So it was so this， so it's like the fact that。Theags came out bench came out as part of the reason part of the codevelop that happened the one thing to point out is you might one thing I can kind of experimentally criticized here although I think there's a good paper the results are good is the you know an agent is going to have to generate more tokens right to get this kind of same level of performance So you see that as represented the dollar average cost per successful trajectory in the second column so the fact you know you would like to know you would like to see computation normalized results like it would be interesting like if I ran 10 times as much do I expect if I ran 10 times as many if I generate the same number of tokens on average from both you know here I think like you know agents work it's fine but I think when you're comparing other changes to the agent you might say well there might be some changes to the agent that look really。

Good， but it turns out what you're doing is getting higher。Is getting like maybe you add。

 I don't know some kind of repep tool that puts lots of tokens in the environment。

 And if it helps that's great。 but it might be that， oh。

 it's helping because it adding more tokens to the average trajectory And if you didn't have the tool and just generate it more trajectories。

 you could get the same the same point on the kind of cost performance curve。

 So it's something you know you want to think about that when you're running these comparisons。

 there was something that I wanted to say about the shell only agent。😊，Which I don't remember。

 oh well， okay， maybe we'll come back later。Okay， so so that's kind of maybe the kind of the first kind of very dynamic react style agent。

So now I want to talk。About a different kind of agent design。That's kind of the other extreme。

 which is called agent less， you know， it's kind of like。

 yeah so so this is kind of like in terms of like where this is the other extreme in terms of how much control flow do you hand write So the I So what we've talked about is kind of dynamic where the control flow is I'm upending to a string Everything else。

 the LM decides the LM could， in principle， implement whatever algorithm it wants on top of on top of these tools。



![](img/45e47edbfdb513df96f2c25bfc77cbd4_23.png)

The other extreme is just procedural， so basically I will write some say Python code that does something natural for solving program repair tasks and every time where it's kind of like where I might say oh okay。

 so first I'm going to iterate through every file in the project and then I'm going to that file is relevant to the to the issue description whatever and so whenever you get to point the algorithm where you need to say quote unquote magicic happens。

 you call the LN。And so so this basically like you have code， you have the logics and code。

 but then you're asking the ALM to make the to make certain decisions in the middle of the control flow。

 so that's basically what agent list is doing so。So there's kind of three。

 I say hard coded I don't mean that in a pejorative way kind of three steps。

 one is like you figure out what you want to edit， then generate a patch and then validate the patch and I will give you a colorful diagram that says the same thing。

So so what you're going to do is you'll have is that you'll have this workflow where at various points you call an LLM so you'll start by saying okay。

 you have some codebase， you textify the structure of the repository you prompt the model to say oh。

 which file should I look at so then you get the model will give you list of kind of topend files and then and then each of those you could say okay。

 here is a here is a skeleton of the kind of methods and classes within each of those files then you call the LLM again to say oh where does it look like I should edit and then you can do that one more time to get a set of lines that you might want to edit。

So at each one youre so at every point you have kind of an end best list of potential things that you might want to edit and then you go through and say。

 okay， now for each one of these， let me independently give this to an LM and say， hey。

 here's a description of the issue， generate a patch and then what you can do is and then once you have that you apply the patch。

A， let me see which one's piss。 Now， one thing that's kind of important about Sw agent is you don't know what the test cases are。

 right， So the agent itself has to come up with its own tests that hopefully describe the issue。

 All the agent has， is it has the previous tests， which might not。

 which probably don't test the the bug it's trying to fix because if they did。

 the test would fail and the bug wouldn't be there So the so the agents going have to generate going to have to propose its own tests and then run the test and the proposed patches And so that gives you a。

So that gives you a set of patches that are kind of plausible that in the sense it's a technical term it means that they pass the agent generated test case and the and then we kind of rank them and then one of them we submit so the。

Okay， so there's a very big table so。At them that I'm not going to read the entire table to you。

 this is a subset of the sweet benchch leader board at the time the paper came out。

 the order is now changed changed， but at the time that this came out was and this was one of the best open source agents and it still is the order is slightly different。

 but it's still kind of near near the top。the so what I want to。

 so the thing I want to take away from this。Is what are the advantages and disadvantages of different agent designs？

So under one the more dynamic sgen type approach， the LLM gets to choose what problem solving strategy it's using。

 So， you know if the LLM， if if if the model produces a patch that's nearly right and then there is a whatever one of the tests fail then the model then you can extend that trajectory。

 the model can decide， oh， do I need to do some more code search in order to figure out。

 oh that this thing is failed why I wasn't able to get the patch right or maybe I just want to make a small change to the patch that's going to make it correct right the model has this has the flexibility to decide what strategy it's going to do whereas whereas on the other side for the more procedural one。

If you have a case where you know the problem can be solved with the simple workflow。

 then why make the LLM figure out what to work？It's right。

And let the model spend more time actually trying to solve the problem and you kind of avoid tool use errors because the tool use is happening on top of the LLM rather than within the LLM。

 and you know you can avoid things where the LLM makes some initial mistake and then the whole trajectory goes off the rails。

So the say， I missed one thing there， okay， yeah。So none of these come down to how do you want to budget the set of compute。

 the amount of compute that you have at test time， Like if you imagine that I have one kind of partial patch where it's failed。

 I it a better idea to kind of extend that trajectory and try to fix that patch or is a better idea to throw it away and generate a new one right。

 Age list is more going to be like generate and test whereas。

Where dynamic could choose and the second part of this is that this may be a case where the kind of winner between the the two of these depends on what type of。

What's the word depends on what type of problem you're considering right So for simpler for simpler smaller patches generating and text test might be better kind of I'm speculating here。

 but the perhaps for longer， more complex changes。 We will start to see and move for that。

 We will start to see more advantages to having more flexibility in the problem solving side So that's the so you think there's kind of a continuum in terms of we've actually talked about three different coding agents so far。

 one which I didn't talk much about was just give the agent Linux prompt。

 So that's kind of there's almost all the controls in the model then or you could do something like Sw agent or agent list there's kind of a continuum here。

 and it may be that has the base model capability changes has the amount of。

And as the complexity of the task changes， the design point here that you do might want to change。

Okay， so there are， I think three more kind of coding agents I wanted to talk about but these kind of go faster and faster because they are kind of more similar to each other so another one of the kind of highest performing open source agents right now is this one autocode rover which is from this University of Singapore there's I think the last time I checked I think it was open hands was the biggest。



![](img/45e47edbfdb513df96f2c25bfc77cbd4_25.png)

Was the highest highest on the Sw Bench leader board that might have changed。

 but I think there's a lecture from last semester on that， so I won't go into it。

So for autocode Rover， the two things I wanted to talk about here are the first one is that has a different set of search tools。

 so it's that rather than being oh let me find this string in a set of files it's actually indexing the the methods and classes in the files in the same way that the ID would so you can have the search tools are things like you know find a class with this name。

 find a method with this name in this class class so that kind of changes the type of code browsing behavior you see it can do kind of more explicit command click。

I also wanted to talk about the。

![](img/45e47edbfdb513df96f2c25bfc77cbd4_27.png)

The the kind of control loop here， which is that it's sort of a concatenation of dynamic agents so there's kind of there are two phases to this one is kind of try to collect kind of kind of information gathering。

 try to do code retrieval and then the second part of it is actually generate the patch and each one of the the separate trajectory with a different system instruction a kind of different set of tools and then you and then you run them one error。

For the other so it is kind of like kind of it's kind of an in between point between agent list and Sw agent with kind of some procedural control。

 some that's more dynamic and and the other thing that you get from having these two agent loops is kind of information hiding like if there were particular if in like one for code searches probably doesn't matter so much。

 but there might be other types of agent you design where you care about this。

 which is that if you have a you might want one of these kind of agent loops to come up with an answer and then you want to throw away the intermediate reasoning。

 just get the answer that it came up with and give that to another agent loop that's something because you're worried that if you keep irrelevant things in the context。

 it will confuse things。So let me then the I think I have two so oh I didn't want okay what's fine So the other no。

 I'm gonna to do things out of order。 The one I will come back to those don So you can take this you could take this kind of procedural control to another extreme say can say's do filtering you can have a state machine So this so repair agent is another kind of recent one where's you know it's a similar the way so these are four kind of program repair tasks。

 the different data set it not sweep benchch， but that's not so important the kind of main thing is for doing program fixing is the design of the agents given by the state machine so where you know we kind of design the what are the steps that we think you do when you investigate and repair a bug each state is you know has a kind of specific system instruction that says please try to do。



![](img/45e47edbfdb513df96f2c25bfc77cbd4_29.png)

![](img/45e47edbfdb513df96f2c25bfc77cbd4_30.png)

Try to understand the bug if you're in the state。And depending on which tool the model does next at the end and then the model is then given the system instruction the model is going do some thinking。

 I'll put a tool call depending on which tool call is is chosen you move to a different state of the state machine so if you're currently in the collect information state。

 then when you do a code search you stay in that state and you can do more code searching if you call the kind of a right fix that's a tool that moves you into a different state and changes your system instruction so that's kind of a different way to get dynamic control with more information hiding。



![](img/45e47edbfdb513df96f2c25bfc77cbd4_32.png)

Okay， so the final thing I wanted to talk about， which is you know try there is。

 although there are so what I've been talking about are more kind of kind of academic agents there although there are a lot of industrial coding agents there's less technical detail about them。

 so this is one of the of the ones that I know that's kind of like a research agent moving towards being used in industry。

 so this is kind of a research agent at Google called passcerine。

And these are kind of several of so I'm not involved in this work。

 several of my friends in the kind of developer toolsols org built this and so this is an agent that is designed to solve kind internal kind of coding issues that Google developers have and what makes the Google codebase kind of different and it is that everything is in a mono repo so this thing is rather gigantic and therefore we have kind of special the build system is a taken into effect account the fact that there's a mono repo that's so big that we can't kind of store all of Google's code in all laptops for example so so。

There was， I've talked in， I've talked about agents。

 So the first thing you have to do is kind of make an evaluation。

 If you want to have this kind of thing。 So what， what they did is there's kind of a sweep bench like loop where instead of using Github。

Poull requests， we use kind of internal bugs and fixes from our issue tracker system。

 so we'll take cases where there are bugs that were fixed and kind of some heuristics that these are kind of reasonable things that we want to use for an agent like like there's a change in test in tests and the kind of size the patch and so on and then we do a list of filtering to have kind of a curated tests set both of two different kinds of bugs one is ones where the bug report was written by a person but it had kind of a small enough patch size and so on and the other one is kind of automatically generated bugs so these are things that I'm going to talk about this a bit more in the computer security part of the lecture is that when we're doing testing of Google code sometimes we will run sanitizers so these are kind of dynamic analyzers that kind of sit underneath the code that's running and check that certain。

baad things aren't happening so one bad thing that could happen is a buffer overflow so there's a particular sanitizer called address sanitizer which you can use it well you can use at home as well where you know it tries to detect at runtime whether you're executable is reading or writing out of bounds and if it does it causes a crash so you know internally when these kinds of bugs happen it creates automatically report an IrishU tracking system so we have a number of reports like this。

And。So this research agent is kind of a react exile dynamic agent like Sed Su agent。

 the difference is the tools are actually our Google development tools。

 so there's an API to kind of Google code search our build system which is called Basil and is kind of and you can kind of view and edit files。

So so that is so thats that's kind of passorine and one thing I wanted to point out since I've talked about Evals is what are the differences between this curated evaluation set and say S benchch these top three plots are kind different they are cumulative distribution functions of different statistics of Sbench versus our internal evaluation for passorine and so sweetbech is the blue one and then the other two are kind of the machine or human subset so generally what it is especially so this one is like how many identifiers are in the patch。

 how many files， how many lines and so for example especially the human patches from the data set kind of are larger effect more files kind have more data。



![](img/45e47edbfdb513df96f2c25bfc77cbd4_34.png)

what we see on SBnch， SweBnch is more similar to these kind of sanitizer reports。So the。

And then you know， there's there's also， maybe I won't get any reports about the you can look into how this agent performs。



![](img/45e47edbfdb513df96f2c25bfc77cbd4_36.png)

Okay， so so that is so that's going to be so this is maybe a good place to to stop for the coding agents part of it。

 so I'll get into AI for security next but the main thing to so I've talked about how agents drive the design of these systems evaluations drive the design of these systems the other thing is like all of these are kind of more similar than they are different I think we're all working in the same three ideas right now So and the other thing about these is the ideas I mean I don't mean this disparagingly the ideas behind all of these agents are fairly simple it's just the design space is large so there's kind of a large set of hill climbing that you do when you have this so we talk about so what is the design space So one is okay。

tools you want。 we've talked tove seen different examples of that。 How do you handle control flow。

 Is it dynamic， Is there a state machine do you kind of recursively call an agent within a lower level agent like whatever right do you just write the control flow and code And then there is kind of the design of the text like what do you write in the system instruction you can do kind the general things you do for prompt tuning you can tell the agent in kind of stronger or less strong language。

 how you want it to solve the problem， What order you want it to call the tools。

How you describe the tools， how you summarize tool outputs and so on。

All of these things have to have sandboxes right because you're running model generated code。

 So I guess there's kind of a right way to do that。

 but that's something you have to deal with If you want to have an agent that is communicating with external surfaces。

 right， all of these are hermetic。Right， if you were doing something like to presage the next set of the talk。

 like penetration testing as an agent， then you need to figure， oh。

 this is actually communicating with external or if you want an agent to manage your email。

 like how would you you have to think about， okay， how do you even kind of prototype that。

 when you have to communicate with external services and one thing we haven't talked about because these are research agents is you know。

 what do we do， how would you involve a human in the loop。

 like when when do you ask for clarification questions， when do you ask for approval。



![](img/45e47edbfdb513df96f2c25bfc77cbd4_38.png)

Okay， so I think and I think I already talked about this。

 So that is kind of what I wanted to say about kind of general coding agents。

 So the next part of the lecture is going be more AI for computer security and then some of our own work in AI security So now I want to kind of finish by talking a little bit about AI for computer security which is kind of like maybe a more emerging area than AI for codegen was this oh no say that sorry I'm confusing my stuff。

 So let me start I'm just I'm going kind of dive in and talk about yeah。

 I don't talk about evaluations but。particular so I want to start like one type of work that I want to start by talking about is is kind of capture the flag competition so that's one So if you say。

 oh， I want to do AI for cute if you start by saying， hey， I want to do AI for computers。

Security questions are okay。 What problem do you want to try to solve within that And how do you so there is a particular type of competition that people have like at schools and and security conferences。

 things like that， which are called capture the flag what I like， I mean， what I like about these。

 at least as a stepping stone is that it gives some idea of the breadth of the type of real problems that you'd like to solve in in AI for securities。

 That's why， So that's why， again， gets interesting to。

Talk about there's different kinds of CTF competitions。

 and I am probably going to kind of butcher this description a little bit so I。

Feel free if you are a computer security expert in the audience。

 but the idea is there are different types of tasks that are like toy versions of something that you might do has a professional researcher and that the task is set up in such a way that for this particular type of jeopardy task where there' there's a special message which they call a flag and if you do the task for a while you will see something where you're like oh yeah that's the flag like hey on the flag or whatever that maybe it's not that but and so and then then you know you solve the task and you can submit it so like one example would be like there are kinds that are like digital forensics where they might say。

 okay here's a file system you know find the hidden message or they might give you more ins about what it is and then you have to know okay how do I kind of look through this file system do clever searches you know maybe more complex ones that might need to do stganography or I might need to like find a QR code or whatever。

So this would be more like kind of modeling digital investigations you know then there's like ones that are just cryptography where you have an encrypted message you want to decrypt it there are ones where you want to kind phone challenges you want to exploit kind of memory vulnerabilities if I want to kind of find find vulnerability and get a service there are ones where you want to kind of identify vulnerabilities or the web ones where you want to do kind of injection or kind of cross site scripting attacks and the reason I like to go through this is two one is you can kind of see how these map even though these are kind of games in some sense。

 you can see how they map to kind of real- worldd tasks that you might want an agent to do and the other thing that's nice is I think if you've been sitting in this class or even just in this lecture by the end of this I think if I just took one of those and gave like a random one of these to like any of you and said design and aM agent for this know。

Could it right， It's pretty obvious why you would want an agent to do any one of these tasks。m。

 so I mean， again， like like we're saying for coding like a kind of toy game benchmark isn't the same。

 it's not as complex， has a real world task， but I think if you can't do these。

 you're probably not going to be able to do the real world tasks either。

So and I think we're currently at the stage of agent development where CDF tasks are still a challenge。

So there are kind of several different data sets， like some of them are kind of recent with kind of historical CTF competitions of different difficulties。

So like this top one， the NYU one is maybe the most recent one。

 there's also one with from kind of high school level competitions。

 and you know each one of these will contain kind of the task description。

 kind of sandboxing environment and away a rateer that will automatically check like whether whether you found the flag or not。

嗯。😊，So that gives you something to start with。 And I want to go through kind of one recent paper to show okay。

 how would you use an agent for one of these tasks So this this one called enigma it's going to be the last maybe the second to last agent I'm going to show you they do all run together after a while。

 So so this is so this is an agent to solve this type of these capture the flag competitions。

 So it is a it is a react style loop。 So here's an example。

 And the do I say in the next slide Yes I do So this is just an example of running some of the tools like you can do you can edit files and so on。



![](img/45e47edbfdb513df96f2c25bfc77cbd4_40.png)

![](img/45e47edbfdb513df96f2c25bfc77cbd4_41.png)

So so the types of tools that you have， there are the kind of the general suite agent suites。

 so you can do file search， you can edit code， you can do you can have a command line。

 but there's a few one of the things I liked about this a few kind of interactive tools that the agent can call。

 which you probably want for security scenarios one of which is having a debugger。

 So there are just different tools that are like kind of stateful tools as a way this is designed。

 I'll show you a different debugger design in a minute where the debugger says there's a command debugger start。

 debugger stop， debugger step。 And those are just different toplevel commands that the agent can use and also there are tools for connecting to servers and again。

 these are implemented three different tools that change the trajectory state So the agent can ask to start a connection。

 stop a connection or send the line。And the other thing that is it kind of does it kind of a natural idea that you don't see very much is a lot of these。

 like if you need to like examine a binary file as part of your digital forensics。

 like you're going to。Run up your context length very quickly So there is one like for long tool outputs。

 there is this kind of natural thing where oh， let me just ask an LLM to summarize this long output So the and then there are one thing which is kind of like a useful trick for when you're designing your own agents is well the first thing is always look at the trajectories right it's just like when you're doing regular supervisored learning always evaluation always look at the data。

 always look at the data right so here it's like always look at the trajectories right you want to see what mistakes the agent making and use that to design the harness so like know one thing that's here is like there are kind of bullet points in the system instruction that says oh yeah I noticed the agent screwed up on this let me add a bullet point that says please don't screw up in this way and then it makes that error less often。

😊，Okay， so this had where okay let me so this is so this is then kind of agent kind of versus on the left versus no agent on the right and we see overall you kind of a similar set of increase that you saw from like the initial Su agent results like going from basically nothing is solve like3 to4% to like double digit percentage So it's kind of nice when you see the so it seems like maybe this is the same thing as a sweet sweet bench kind of leaderboard but at a different point in the curve。

Okay， so that's basically what I wanted to say about more general capture the flag challenges。

 so I I wanted to talk end by talking about a kind of specific security task。

 which is kind of vulnerability detection so。So this would be like， you know。

 if you want to exploit a computer system to get， you know。

 unauthorized access or something like that。 one， one way you could do this is by targeting bugs right in this kind of software or hardware or network layer or whatever。

 So so I'm going to talk specifically about so a vulnerability is basically a bug in the system that has security implications。

 So I'm going to talk specifically about software vulnerabilities both because I'm talking about coding agents and because that's。

 I think where most of the most of the work has happened so far。

 So some examples like you know reading out of bounds or kind of crosss scripting or something like that。

 where there's kind of it could be a potentially a small bug in the program that the attacker can use to to do bad things。

So， so let me take， let me take an example of like an out of bounds right。

 which is kind of a particular。Bad good have。 So there is a kind of taxonomy of these different kind of software bugs that you can go to。

 And if you go to the taxonomy and say， okay， what kind of bug is it out of bounds right。

 it'll show you C code that looks like the code on the right where it says， oh， okay。

 like one kind of illustrative version of this bug is oh。

 if you have a function that returns negative one on error。 And then I use that as an index。 Well。

 the negative one is going to get cast to it could get cast to something unsigned。

 which is now going to point someplace way off into oblivion。

 and then you'll kind of write something to memory。 you didn't want want to。

And then when you look at that， it really seems like detecting vulnerability should be pretty easy right because you just want to kind of find this data flow and find things that aren't within the bound So here's another example of an of an out of bounduns right So this is an example of a kind of function from the Linux kernel I mean I know the first example was probably relatively simple you might have seen the bug right away I know do you see the bug in this one。

That's a joke。So so what this is is I mean actually it's not like。

 I mean it's too small for you to see， but this part of it isn't like if you kind of make reasonable assumptions about Linux kernel macros。

 this part of this code is not that difficult to understand so what's happening here here is this function is copying some data from a network packet。

 if you look at the two arguments to I don't know what I guess our CVV stands will receive but the first argument is the actual packet。

 the second argument is a header and what it is doing is on I just I have it in my notes this line here it's doing a mallic the size is this thing size which it's pulling from the header。

And then online let me see it's 40 oh yeah 44， I think it's like it's doing a mem copy from something in the packet to this thing that's allocated based on the size So what you can see here is that both of these things were read from the network and there hasn't been checking down of the size So that means that oh you could actually there's no the actual payload might not match the size and the header and so if it doesn't then the buffer that's allocated will be too small and who knows how much you're going be writing So the reason so that's so this is actually kind of kind a real vulnerability in the and the kernel and the two things that I want to point out why this is hard one is a bit of a needle and a haystack right there's could be lots of functions like this in the Linux kernel and it could be kind of difficult to craft inputs that reach them I have to know which network protocol this thing is handling and so on and so this。

that actual data flow that breaks is fairly simple。

 but kind of identifying it from a lot of things that look similar。

 but are perfectly safe is very difficult。 And the second thing is this function on its own。

 it's not vulnerable or nonvul。 that's not even a well definedfined question to say is this function vulnerable because if the caller check did the bound checking this function be fine right so you actually can't understand whether this function is vulnerable or not without kind of knowing globally what's going on。

Okay so that's why AI for vulnerability detection is hard in fact in fact this slide is basically a criticism of the next slide so the next slide is so we have this really nice source of data which is the kind of vulnerability database so there is a place where if you have public software and you discover a vulnerability you can kind of get a unique trafficking number write a description and you know give links to the patch any other information about the advisories and there are kind of thousands of these of these collected。

So this seems like great for machine learning， right， because all I need to do is say， oh。

 let me kind of download all of these vulnerabilities and dial。😊，K of the patches。

 and I'll try to have some classifier that says whether things are vulnerable or not。 So this very。

 so I'm I'm exaggerating my criticism of this， but it's a very natural thing to do， right。

 The first thing you see a big data So you see a big data sit on the Web is let's download and use it。

 it's what you should do。😊，And so there's a bunch of authors who' have done this and kind of created data sets that say。

 oh， that the idea is that I'll take examples of code where we' found a vulnerability。

 we've not found a vulnerability and you try to have you can measure kind of detection or patching kind of based on this seems like a natural thing to do。

Unfortunately it's what I would have done too。I got started and there is problems with it。

 the main the first problem is like how much of the code you put in the input right。

 Like we saw in the previous slide， if I just look at one function that's been patched， you know。

 that might not be where I might not know just looking at that function。

 whether there's a problem or not or just because if I take a function。

 the patch that might not be what does it mean for a line of code to be vulnerable right there's a line of code where an incorrect memory access happens Sure。

 but that that line of code might be correct right the part that's incorrect might be something upstream did something wrong。

So the patch might be very far from the line of code that crashed。 So the idea。

 even if a line of code or a function being vulnerable。

 something I'd argue it's not a meaningful concept。

Then the other thing like if you want it so there is a question about like how much context do you want to give and I'm not it's a very difficult question to answer or another question how do you handle tangled commits so I kind of mention this a little bit in sweetbech like if you want to use this as a patching data set well lots of times a patch will do more than just fix the vulnerability that's a very common case so kind of learning kind of difficult The other thing is like maybe this is easier like kind of judging correctness of patches is kind of tricky is like if you can run the code you could probably judge correctness if you're trying to do it statically then that's difficult right because there are many ways to patch of vulnerability and the fact I gave you this example of of a vulnerability description like these are vague they will give you some information about where to start they'll be vague they'll be noisy sometimes just because people are busy they make mistakes sometimes because。

You don't want to give out too much information about the security of vulnerability。

So I think these are really difficult issues， it's really difficult to come up with a static evaluation of vulnerability and detection in this way and I think these issues are fundamental。

 I think people have done a lot of great work trying to get around them to make the data sets cleaner and cleaner。

 but I think these data sets are really hard to use。

So what I so I would recommend instead for working on this kind of problem is do something dynamic。

 so you need something like a sweep benchch eVval where you can actually run the code on an input that exposes the vulnerability。

So there so there are kind of there are some data sets I left one out。

 that's one of the things you're supposed to ask me about。

 So like I'll just tell you about it now so there is so there is like a DARPA sponsored competition going on now the finals are later this year for like AI based vulnerability detection there was kind of older one 2016 it's also kind of interesting both because you can get the kind of programs and also I think the story of it is interesting if you want to look it up there is more recent security evaluation from meta that contains some it tests various parts of security for AI and AI for security。

 but there is like a memory of vulnerability thing。

 there is a more recent thing that I like which I forgot to put on the slide which is A RVO RO it's it's for some past vulnerabilities thatve been found by fuzzers containerized so that you can run。

So you can ask checking of whether you found or fixed。First of all。

So there is I'm about to talk about one more agent I promise。

 but there is a lot of a huge amount of research on automated techniques for vulnerability detection like some AI but also kind of nonAI so probably the most commonly used technique for automatically finding vulnerabilities is called fuzzing so that is like you run the programs on many。

 many random inputs you can choose them like a genetic algorithm type search so you can flip bits in the inputs you can mix and match them and so you try to find an input that causes like vulnerability to happen like an out of bounds right。

Those are like those are really important in practice like security critical software is commonly is fuzzed extensively so and so this is this is kind of important technology。

 but it's also it also asympotes like if you run a fer for long enough on a。

On a softwareul package like it will， you don't like continually find bugs even if they exist and there are kind of famous examples of bugs where they've been found exploited in the wild。

 these are packages that are commonly fuzz， but it was a difficult part of the code for the f to reach。

There's a lot of work on， so I think there's an opportunity for AI to try to we keep fuzzing things。

 but try to find deeper bugs maybe that require kind of complex invaris that fuzzers can't reach。

People who work on static analysis for vulnerabilities vulnerability detection that's you know it's kind of there's a lot of interesting work that's been done in that space。

 the downside is kind of combinatorial explosion and kind of a false positive rate it's kind of very it's very difficult to define it's kind of a very very difficult business to be in。

Um， and then like on some of these other data sets， I've talked about like， you know。

 once you collect the vulnerability data sets on the previous slide， the ones that I don't like。

You can try finding an LLM on them and so a lot of papers。

The papers that I ci it will show you some results for that。

But you know we wanted to do something different， so we thought there was kind of an opportunity to try to use to try to kind of you leverage AI in a more interesting way and so that's this project that I'm involved in which is called the Big sleepleep one thing I've noticed having named a project this is that most people do not have the same knowledge of classic cinemama as I do so the big sleep is it's a famous movie from the 40s but starting Humphrey Bogar and if you like old movies I recommend there's a story about why this is named that that I won't get into so so this is a collaboration between some of us in Google Deepmind and some security experts from Google Project Ze so these which you know this is a kind of a really a nice security group within Google that tries to find vulnerabilities that tries it does they they try they also succeed in kind of finding vulnerabilities in open source projects。

And if you look at other things on their blog， you can see kind of how intense some of the vulnerabilities that they find are。

 So with this kind of group of collaborators， we've been kind of creating this， this agent。

And the thing that motivated us about this was thinking about or one way to motivate this is by thinking about kind of the experience of our collaborators in Project zero as a human security researcher auditing code to try to find a vulnerability they don't think of it like a classifier right。

 you don't just read some code as a person then say yes， no。

 I think it's vulnerable right So instead what you do is you can read the code， try to understand it。

 you have some hypothesis about what would be going wrong and then you try to run the code in a debugger or something gains some information about whether your hypothesis is correct and and we wanted to see and we think that if an AI is going to be successful。

 that it should do that too so and this kind of naturally suggested NHienttic approach where you'd have kind of a code browser that and a debugger。

So one way you can。Think about this as analysis versus static if you are if you're trying to train just an LLM。

 you know， maybe with some maybe with some reasoning tokens or whatever to examine code。

 do some reasoning， come up with a vulnerability， that's kind of like static analysis you haven't run the code。

 whereas if you do an agentic approach that's more like running a fer。

 it's more like dynamic analysis。So what we're focusing on a particular type of security issue in the big sleep and that we're focusing on memory safety of vulnerabilities and the idea is kind of given given a code base the goal of the agent is going to be like a fuzzer to generate an input that when it's run on this program under test causes bad memory behavior like an out of bounds read or something and what some of this is so you get some of the advantages of a react style loop but the other advantage compared to static analysis approaches and even compared to say something like code editing is in some ways this is a simpler problem than code editing and the reason is we have an oracle So if we can so I mentioned sanitizers to you earlier in the lecture so when we are running the program and this agent we are going to run it in a sanitizer in a debugger so the goal of the agent is。

act generate an input that causes the program to crash and when it crashes we know you found a security bug so you know whereas if you're doing cogeneration you don't know what the you don't know what the true tests are so you have some part at the end where you have to figure out oh which patch do I choose here it's like if you find a bug you find a bug。

And one thing that's nice about， well， let me actually say to the agent before I start telling you about how good it is。

 So so what we're gonna to do in big sleep， it's gonna to be a react style agent。

 The goal of the agent is to generate an input that triggers a sanitizer crash。

 We have access to three different types of tools。 So one is like a code browser tool。

 So this will be kind of similar to what I said about autocode rover that we actually index the program。

 we know what all the identifiers are。 So our tools are like the type of。😊，Pools。

 you do an IE navigation。 So like given the name of a method， jump to definition。

 or we can also follow across references。Then in order to generate inputs。

 we do that using we don't actually ask the agent to generate text directly。

 we ask the agent to write a Python program that generates the input and the reason we do that is like if you want to do a buffer overrun or something you know we don't want the agent have to generate 2048 A's we'd rather generate a Python program This is a times a right it's just simpler So we tell the agent please generate a Python program that sends a strikerites a string to a particular variable。

 we send that string to standard in。And then we can run the target program in a debugger。

 so we've talked about the the Enigma agent also had a debugger。 The design of this tool is similar。

 but a little bit different。So in our tool right now。

 the agent doesn't call the debugger interactively what it does is it can say first it calls the Python interpreter to set up an input and then when it calls the debugger。

 it just runs the whole program and it can optionally specify a list of quote unquote break points So a breakpoint is file line number and an expression optionally and what it does is we tell the agent that break points but the really watch points So we'll run the whole program without stopping on the whole program without stopping and at the end we tell the agent here are the break points that were hit and here's the value of the expressions you asked me for So this way this gives the agent another way to check whether what it generates an input。

 whether it's doing what it expects， whether it's having the control flow that the agent expects from the input。

Okay， so let me show you an example of a trajectory so I don't know what that meant so this is a let me this is an example of a program from the meta cyber sec Eval benchmark that I kind of briefly mentioned in the previous slide so there is a system instruction that I haven't told you that kind of explains the task the agent describes the tools and presents a problem solving strategy and some guidelines to the agent so the first thing agent is can to do is say okay please show me the main method。



![](img/45e47edbfdb513df96f2c25bfc77cbd4_43.png)

So here all of the the as I said， the control flow is completely dynamic。

 like react style and there's no the agent has to use the code browsers tools to see the code。

 So then it gets a thing of the main method。 And typically what the agent does is it summarizes the code sometimes longer。

 sometimes less whenever it sees it and then it'll decide okay， I see an identifier there。 okay。

 you can't see there's a reader class because I snipped it out but somewhere in this there's a class called reader。

 So the agent is okay， let me look at the reader class。



![](img/45e47edbfdb513df96f2c25bfc77cbd4_45.png)

And so it says， okay， let me look it looks at this and it'll do a bunch of terms of code browsing。

And after a while， the agent gets tired of code browsing and it decides， okay。

 I think I've found a vulnerability now。 So what it does then what we've instructed it to do is to write a report that explains what the vulnerability is and what happens how to exploit it。

 So the agent will generate this text after it's seen enough code where it says， oh On line 70。

 you use string copy， but you didn't use bound checking。

 So if I created input of this type then then this is in love saying a typical buffer overflow or classic buffer overflow really likes that。

 so this this is could be exploited in this way。 Here's my report Now let me generate an input。



![](img/45e47edbfdb513df96f2c25bfc77cbd4_47.png)

![](img/45e47edbfdb513df96f2c25bfc77cbd4_48.png)

And so the input is going to be。So Python now this is a Python code and here's an example of like what I said where you can construct a long input the the agent can you know it can it's helpful to have access to the library because。

 you know， if you want to。If you want to kind of generate， sorry， I'm having English。

 if you wanted to agent to generate binary strings， for example。Can call。

 you know number to bytes it can it can also if it knows things about particular input formats。

 So if you have a。A program that takes JSON or images has input。

 then the Python program can generate that。So in this case， after it generate some Python input。

 it calls the debugger function， it says， oh。These were like tumors that it thought was related to the vulnerable code path。

 So it says， oh yeah， please show me those。And so now we run the program in the debugger and the agent is sad because the program exit without crashing generally that's what you want。

 but not if you're doing a security audit so now the agent's like okay。

 it didn't trigger the bug that it thought it did so it can's let's keep iterating and so so then it writes some things about why why it messed up so here it says oh the program failed earlier than anticipated it because I forgot to do such and such and so let me update the input so that I don't make this mistake and it might iterate through do that multiple times and then and run the debugger again after each one and then at some point it says oh the program crashes yay。

 it crashed and then it gives some information and then that means the agent has succeeded。



![](img/45e47edbfdb513df96f2c25bfc77cbd4_50.png)

So so where are we， where where are we right now， So I'd say the current kind of state of the agent is like we have kind of ways of testing it on kind of capture the flag challenges like。

 like， for example， this open。two benchmark and and there it's kind of reasonably effective。

 there's still a lot that we need to do to scale it up。

And we have found one real world of vulnerability that we've disclosed and that is kind of an SQL light。

 So one thing about this it's kind of one of the advantages of agents for this type of security task is you can put any information that you have in the context。

 So in this case we did a type of variant analysis。

 So so it turns out that when you find a security bug a vulnerability in project。

 there are often many similar vulnerabilities at different places in the same project So those are called variant and some like a very large number of vulnerabilities that we see exploited in the wild are variants of bugs that have already been fixed So what we did here is we took kind of a recent bug that had been fixed in SQL light and we added the information about it into the context and then said I don't know try to find something similar。

And you eventually and it did。One thing I want to comment on this is one thing that was kind of working in our favor。

 This is maybe like a best case in some sense， because in I mentioned the kind of little red writing code principle。

 the agent has seen a lot of SQl queries right in the pretraining data。

 So if it sees kind of one SQl query that to that used to break the system。

 it's kind of easy for it's kind of reasonable that that LLM could generate similar queries。

And the other thing I mentioned fuuzzsing， it turns out we did go back with general purpose fuzzers and try to see。

 okay， now that we know where the bug is， can I get a kind of state of the art。

 general purpose fuzzer to find it and in some reason。

 it was and it was pretty hard to find like after 150 hours， we weren't able to find it。So yeah。

 so that's kind of our status so far。

![](img/45e47edbfdb513df96f2c25bfc77cbd4_52.png)

So finally。Let me pop up and say so I had to summarize the security part of the lecture。

 So I think this is kind of a wide open area。 we're just getting started。 there's a lot to be done。

 I think it's an exciting application area for AI because agent genetic techniques seem really natural here。

 you need to interact with servers you need to run tobugggers and it's also and it's also kind of a really nice testbed for code understanding methods right that to find a security issue and to say。

 oh yeah， this is a software of vulnerability you've got to think really carefully about the corner cases that the developer maybe didn't think of or and you have to track data flow along stretches of the program So if you're doing network or system security you have to do that across multiple interacting parts programs in a system So it really does require you to kind of understand at a deep level what programs are doing。

 which makes it kind an interesting challenge model challenge。Task for LLMs。 And， you know。

 I've talked， you know， in depth about some capture the flag stuff and some vulnerabilities。

 but there's kind of a huge space here that we're kind of only starting to get into。

 And there's a lot of real and kind of and this is the time we're starting to scale it up。

 So it's kind of an exciting time to be part of this area。😊，Okay， so this is。

 that's kind of all I have to say I'm kind of happy to take some more questions。 Thank you。



![](img/45e47edbfdb513df96f2c25bfc77cbd4_54.png)