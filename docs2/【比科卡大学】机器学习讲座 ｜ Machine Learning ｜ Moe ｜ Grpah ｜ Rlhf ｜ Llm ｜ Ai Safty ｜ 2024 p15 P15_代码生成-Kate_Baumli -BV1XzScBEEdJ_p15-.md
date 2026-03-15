# 【比科卡大学】机器学习讲座 ｜ Machine Learning ｜ Moe ｜ Grpah ｜ Rlhf ｜ Llm ｜ Ai Safty ｜ 2024 p15 P15_代码生成-Kate_Baumli -BV1XzScBEEdJ_p15-

![](img/da6ba9f8d804a927e35dfbc8d49ef072_0.png)

Hello， hello。 Good morning。 Im so excited to be with you guys today。

 I hope you've enjoyed the whole week of。😊，Oh， great， yeah。H hello， great。

Hope you've enjoyed the week of learning about machine learning and are excited to kind of continue that learning journey beyond this week。

😊，Yeah， so just to reintroduce myself， I'm Kate， as we said。

 I'm a research engineer in a Deepmind and I've been there for about five years now。

 and I feel like yesterday and today I've been reflecting a lot on how much has actually changed in the last five years and when I started doing research was looking at specifically and still am a looking at reinforcement learning but a lot of the questions and a lot of the things that we were always hoping for and kind of talking philosophically about are things that we're actually able to do in certain applications now and a lot of things just work So it's a really really great time to be involved in machine learning specifically I've always been interested in looking at how do we get agents that are you know doing the general reinforcement learning。

 having knowledge that transfers to different task that you're not just learning one thing but you're learning a general suite of knowledge and what we we always say kind of back in the day when we're working。

A lot of simulated environments to study these techniques for reinforcement learning was we're looking for and trying to build these environments which have properties of the real worlds that we can leverage to build these open-end kind of general policies and a lot of the struggle was kind of trying to build that。

 And then that's actually what led me to looking at codegen。

 because we're now in this regime where we can ask a lot of these questions in not only a domain that is in the real world and fits all of these properties that that have this kind of。

Property of the general knowledge transfer， which we'll get into a little bit。

 but also have real world applications that we can can can affect real users now。

 So without further ado， let's get a little bit into the talk。This works。嗯。Yeah。

 so today we're talking about codegen， but I hope this will serve as a useful lens through which to kind of put together a lot of this stuff from this week and looking at kind of generally how do we approach machine learning problems for a real world application。

 What are the knos that we can turn strategically like where can we get data what can we do if we don't have it and how can we measure our success and define the problem in a way that allows us to make progress。

😊，So first of all， why code generation， I kind of touched on this already a little bit。

 but and maybe maybe one of the first ones， one of the obvious ones is the kind of economic utility of software engineering software engineering is a $700 billion US dollar global industry as a $2024 which is just an unfathomable amount And so if you like money then that's great and what this really says to me is that codegen and software engineering it's something that's everywhere。

 it's ubiquitous， its touches every corner of our lives and people find it useful enough that this is what's going on every single day。

And that's because code is not just the text in the terminal window。

 so we call it code precisely because it translates to some measurable， observable。

 executable outcome and this is in some sense true of all language。

 language is language because it is symbols that represent something in the real world。

 but code has the special property that we can immediately see the outcome。

 and we have representations of what this code means and what this code does and we can leverage that and a lot of really interesting ways when we're talking about building models to do this。

 And so this is not only what makes code economically useful。

 but it also provides signals that we as machine learning practitioners can take advantage of when we're trying to optimize signals or create data or find data there's a lot of structure that we can leverage there So that's。

One of the most exciting things。 And then code is this modular， rich， infinite and openended space。

 So there's infinite possibilities of things that we can do with code and code starts from a number of these core regularities and rules and from that expands this ginormous amount of complexity。

 And that's the property of the real world that I was talking about that allows us to create knowledge because we can find these regularities and capture them and transfer that knowledge to doing something else。

 So we kind of have the potential to truly try a lot of these research ideas towards artificial general intelligence that that we've always dreamed about。

😊，And maybe the most sci-fi of the kind of reasons and one of the super exciting things is the better that our models become at writing code。

 the more we can leverage that to building the next generation of models。 So you know。

 the extreme end of that spectrum looks like you know。

 this kind of maybe provocative picture that I put here of a model writing its own source code directly and continually optimizing itself。

 but that also looks like taking out certain stages of the pipeline that are very tedious to do。

 or that would help things scale a lot more。 For example。

 writing code to serve as executable verifiers for other language tasks。

 or simply can help AI developers along their journey with。😊，You know， documentation。

 lookup or helping to write code faster and more efficiently。

And I've got this quote from Steve Jobs here， which kind of elucidates one of the other reasons that everybody should learn to program a computer because it teaches you how to think。

 And that's true for you and me。 but that's also true for our models and the fact that learning how to write correct code forces you to reason properly。

 It forces you to be logical in your thinking and to enumerate what what it is that you're actually doing。

And so just one more time before I get into the actual kind of details。

 the special properties of code that we're going to see that we're gonna leverage a lot during this talk and why code to me is quite interesting to work on is I think the biggest one is that it can be executed and you can use the feedback and that kind of rich feedback from executing code in so many different ways from evaluations your training signals to data generation and data filtering。

And finally， that because it's represented on the computer in a certain way。

 you have multiple layers of representation that you can use depending on what your goal is。 So。

 for example， any piece of code can be translated to， to an abstract abstract syntax tree。

 which is kind of describing the core elements of what's really going on in that piece of code。

So imagine you are an interviewer and you。Want to know what the person in front of you has done and you say so tell me about your experience at your last job and they say。

 oh， I wrote code。 they haven't really told you much about what they've done And that's because code generation is such a broad space。

 code can be done for anything。 And there's a million different things that people mean when they talk about code generation。

 And so I haven't really enumerated what I mean when I'm talking about code generation。

 So your next questions might be something like hey， well， what did you write code for。

 What was the purpose of that code。 what language were you using， what kinds of tasks。

 There's all these different steps in the software engineering process。

 like know the most obvious one is， I tell you what kind of code to write， it should do this。

 It should have these properties and then you translate that into code。

 But you can also think about all of the other things that when you write code that you have to do like debugging going from a failed。

Of code to one that's passing all of your tests or documentation， code explanation， refactoring。

 test generation， So there's all these different steps of the process。

And mostly what I mean by code generation is the first thing。

 and this is generating functionally correct code based off of some functional specification。

 So that functional specification can look like a natural language sentence of exactly what we want。

 and it can even be slightly ambiguous sometimes So that's thing that we'll have to tackle perhaps a bit more of a structured way of representing this would be if I give you like say a code signature。

 a function header and tell you with a doc string what this function should do。 And then I say。

 okay finish this function based off of these parameters it should output a boolean。

 I could also write code in one language and then have you translate it to another another language。

 that's another functional specification or we can do something like test driven development where I write a test that has all of the behaviors that I might want to look at。

And then you have to come up with a function that meets those standards。

 This one can be a bit tricky because a lot of the times it's really hard to actually write down everything that we mean when we're talking about a function。

 And so if you're not careful， then sometimes test cases or things that can be hacked。

 And then finally the one that I was talking about earlier of fixing errors。

 Now the actual purpose of the code。 the functional specification is maybe implicit in what's going on in the rest of the code。

 and the fact that something is clearly going wrong。 So there's kind of two specifications there。

 when it' fixed there error， what the implicit one is whatever the purpose of the initial code was。

Now， to kind of lay this out just a little bit more。

 I always like to think of things and what are the axes that we can kind of poll to， to， you know。

 create data or when we're looking at measuring capabilities， What are the different kind of。

 what's the Cartesian products。 Like what is the space that we're looking at here。

 And although we are talking about this kind of general space of code generation。

 I think it's really important to。Enumerate a lot of the time what we mean。

 because then we can do things like measure it and make sure that we're not focusing only on one particular area and expecting not to transfer to some other area。

 so。The the first one is the structure of the code temp to generate。

 Are you generating a single line of code， Are you generating a few lines of code or an entire function or know a class。

 a file， a full repository are you generating contiguous code。

 or are you generating some sort of like patch or a diff that should work with an existing repository and you're changing that code in some way。

 the language or programming environment。 that one's fairly easy。 you have your language。

 but you also have potential imports or libraries that you're rely on that you want to be able to your model to be able to use。

 And then what is the definition of correctness in this space。 And how are we measuring that。

 So as I was talking about before， usually this has to do with what happens when we run the code。

 Most often， that's what we're gonna be talking about is like the code is correct because it did the right thing when I ran it。

But this also could regard you know， something like human liability or style so， for example。

 in ID D code completion， where you're trying to create suggestions It could look like what is the most useful thing for me to suggest to a human as they writing their code。

 And so the functional specification in there。 And the way that we know it's correct is whether or not the human accepted it and found it useful over a longer period of time。

 And then how do we actually verify this correctness， are we looking at human judgment。

 are we looking at know， test cases that are kind of human judgment distilled into a very particular formats。

And then finally， we， we saw this on the last slide。

 How is the problem specified as a natural language， Is it a do string， is it code signature。

 Is there some code context， So this is kind of the space of tasks that we're looking at that we want to be able to solve。

 And so keeping these in mind as we go through， we'll look at some case studies along the way of the presentation that have different flavors of these。

 these things。😊，So onto evaluations。 So I used to think that evaluations was maybe some of like the most boring part of the pipeline。

 you want tona get to like building the models that can solve the thing。 But evaluations is actually。

 I would say like one of the most impactful things you can do because you can't measure something you're not gonna be able to optimize it。

 And if you can't define what you care about。 So looking at code evaluations and a lot of different ways that we can judge correctness。

 And none of them are perfect。 But I think together。

 we can come up with ways for different types of code to judge the correctness of this。

 So throughout this talk， a lot of what you'll realize is that know codegen code is just language right So a lot of the methods end up being very similar to a lot of other language methods but have some special extras and some things that you can leverage。

 So on this slide， we've got a few things that。😊，Are used widely for all language。

 maybe with a couple of tweaks。 And then the one on the right。

 this kind of execution test cases is specific to cogeneration。So the first one， human judgment， I。

I asked Gemin I to make me this stresses game in Python。 And then I have a link here。

 I probably won't open it to not mess with the technical links。

 but it actually output it like a really， really， really long。Class of chess game。 and。

I couldn't tell， like， is this right， I would have to kind of run it to find out。 So human judgment。

 especially in the way that we talk about it a lot of the times with human readers for language models。

 It's a very tedious task to ask them to do。 and not every human has that kind of expertise or the time or the bandwidth or the kind of energy to look through in code review every piece of code written by a model。

And。Especially when we train our models with things like R LHF。

 what I've noticed working with codegeneration models a lot is that sometimes you ask for something and it' it looks so right because it was trained with a signal of a human saying。

 yes， make it look good to me on first glance。 And so if you do that enough。

 and you're actually fooling yourself with with thinking that it's correct。

 if you're just kind of looking at something outright。

 So human judgment is actually really hard to get right in this case。

 It's very tedious and and humans are known to make a lot of mistakes when looking at code because it's a very mentally intensive task to tell if something is correct or not。

Now， this extends also to model judgment。 Maybe in this case。

 we get away from some of the tediousness of the human fatigue of looking at something for so long。

 And in this case， I pasted the the code back into another instance of the model。 And I said。

 you know， fund any bugs in this code。And I actually was able to point out some interesting things that I hadn't noticed in the first pass。

 like mostly somewhat service level things of。Inconsistent indentation or some stylistic things。

 But also looking at。Edge cases， like there's a potential infinite loop in one of these methods。

 there is something that you're not fully capturing the notion of what chess is because there is incomplete castleling rights。

 implementation。 I don't actually play chess really。 So I don't know what that means。And so。

 so we get a little bit further here， but we're still bound by what the， you know。

 the knowledge inside of the model。 And we would still need to train the model beyond this to。

 to to capture these kind of logical inconsistencies。Beyond that， so model judgment is， I think。

 a really great thing to use。Another thing that is sometimes used language modeling are these kind of automated reference based reference solutionbased metrics。

 so I have a good implementation and given that that's like a good implementation how good is this other implementation how close is it and this can be really difficult in any language。

 but especially with code where you know there's so many different ways that you can achieve the same functionality and so there's this metric called blue which is basically looking at a weighting of common n grams so basically like how many sliding window token sequences to these two solutions have in common and that can get you somewhere but obviously especially in code you're not necessarily using the same words So there's a couple of iterations on this So there's a metric called code blue which extends blue to also injects the code syntax via an abstract。

At abstract syntt tree and data flow， so looking at another representation of the piece of code to see maybe that is a more fundamental representation of what this is actually doing and that's more comparable between different solutions this only gets through so far though because there are completely different like algorithms that move your data in very different ways but then end up achieving the same results。

And so say your solution， your reference solution is good。

 but it's like maybe a brute force way of doing something。

 this might not necessarily find the difference in the algorithm it might penalize for that actually even if the model solution is better。

And then there's another metric called Bt score， which again。

 this is something that's used outside of cogeneration。

 which is basically a similarity metric between the embeddings of the tokens in some transformer space between these two solutions So what that does is the the model is a pretrained model。

 it has understanding of how the context relates to the tokens。

 And if the that model's understanding of one solution is very similar to another。

 then maybe there're actually。Quite similar。 And then there was an update on on this specifically for code called code B score。

 which uses models 1 trained specifically4 code， which we'll get into code specialist models in a little bit。

 but also includes some other tweaks to make this work well like including the natural language specification in this embedding So that your representation is more about how the code relates to the functional specification。

 And that way you can look at the difference between how my reference solutions code relates to the specification versus my model generated codes。

 You can get maybe more rich signal there about whether or not these two things are doing doing the same thing。

And finally， maybe the gold standard for some cogen tasks is executable evaluation。 So again。

 this is one of the special properties of code that we're seeing this leverage here for the first time。

😊，That we can execute our code against， say， some reference test cases。 And then we can tell。

 is it passing， is it failing。Now， this requires a sandbox to do this safely because you're generating kind of completely unknown model generated code。

 So you want to make sure that you're doing this in a way that it's not going to affect the rest of your。

 you know， the code that you've got stored anywhere else and that it it's kind of isolated。

And it also requires an unambiguous problem statement。

 So in order to be able to reliably execute my model's code。

 I have to tell it how I'm going to execute it， because say， you know。

 I'm going to execute in my test case， the function fo， if my。

 if my model generates something in a function called bar， then it's gonna 0 on the test cases。

 even if the implementation is correct。 you have to be specific in the way that you are specifying these things in order to test them correctly。

 which is fine， but also can sometimes be at odds with the way that we use models in the real world。

If I'm using a language model to generate my code， I don't necessarily care what the function is called。

 I care about that it generates something at all。 And so this can kind of there's a tension there between fully specified so that we can execute it。

 and we know exactly what to do with it and use that structure versus not wanting to be too structured in general and also wanting to measure this kind of ambguous thing。

 So that's just something to keep in mind。 And then as a part of that unambiguous specification sometimes we can show like oh here's an example of a test case that I'm going to test you on so that the model knows okay。

 I need to put my know my code in a function， and I need to have these variables。

 these arguments and return a certain type。And so there's this distinction between public test cases and private test cases。

 public being that the model can see what's in the test cases。

 but we also need to be careful not to like to also withhold some private test cases So the model doesn't overfit its solution to the test cases because you're never going to be able to enumerate every possibility in test cases。

 that's why you're generating a function。 You want it to have this open-end behavior So you want to make sure that it is not just saying。

 you know if the input is this， then I'll output that for enumerate all of your test cases。

 So having some private test cases to to evaluate the model on as super useful。嗯。

And a couple of these executable evals in their research papers。

 they showed actually very low correlation between what I had on the last slide。

 which was the semantic you know， matching to a reference solution and this kind of functional correctness。

And I， I put just on the right here some examples of very common evaluations that people use that are under this category。

And I would say most of the evaluations that I use in my day to day have this kind of execution test cases flavor。

 so just to quickly go through human EVval was one of the first human eval and apps or some of the first executable benchmarks that people released in 2021 and human EVval contrary to the name。

 no humans are harmed during this Eval it's just because humans wrote the evaluations in the first place they were the test cases and the prompts and everything they're human source。

 but it's really just automated test cases for function generation and then a lot of the other evaluations beyond this look like trying to address some of the issues with maybe low coverage。

 so EVval plus synthetically generates a lot more test cases to go with things like human Eval to make sure that we are testing like a high coverage。

test cases。There are some competitive programming benchmarks with the Sver。

 Swbench is looking at this kind of executable correctness but in a full repository can you fix localize and fix errors in a repository。

 and then there's some data science focused ones like DS000 and arcades class Eval focuses on like it sounds classes。

 and then live code benchch is one that came out know somewhat recently。

 and is's interesting because human E which for a lot of the time is what most people would use to differentiate these models all of the solutions are on Github and there's a lot of contamination。

 as you can imagine， that goes on when you train your model on all of you know Github means that you can't reliably trust even if you try like decontamination things because maybe variable names are different And so live code bench。

Continually updates a leaderboard in real time so that you can actually look at for certain cutoff dates what how does the model perform and a lot of the times you will see like a drop off after a model you know training day or something like that so figuring out ways to reliably。

Test the code these model rights is， is quite a lot of work and very rewarding work。

 So that's kind of the overview of some of these metrics。 And finally。

 when we're measuring correctness as per test cases， because code is so。Specific。

 you can imagine all of the space of， let's say the vector space of all of the code that you could write。

 And so that code that is similar to each other in， you know， say token space is close together。

 And then if you look at you know， the correctness landscape of this even one token that you have off might cause a sharp drop off so that your solution is almost correct。

 it's literally one token away。 But that one token is causing an error that's causing all of your task cases to fail。

 And so you're getting absolutely no signal from this。

 So a lot of the times because this is such a difficult task。

 what people will report instead of just my model past or failed is this pass I k metric。

Which came out with the human evolve benchmark。And it's basically what it sounds like。

 instead of generating one solution， I generate， I have my model generate K solutions。

 And then I look at， do any of those tasks。 And you if you're using different values of K。

 which is what's shown on this plot here， you might want to use a different temperature so that you're。

 you're creating more diverse samples if you have a high K。Versus if you only have one shot。

 you probably wanna get your model to output But the thing that it's most sure is correct and doesn't have that temperature。

And hybrids of these kind of evaluation schemes are possible。

 and I think we need to do that for all of these different kinds of code that we might want our models to tackle So you can imagine making the human judgment。

 making the human job a little bit less tedious by maybe I have some test cases and I execute the code on them and then the human can inspect the behavior or maybe there's not predefined test cases。

 but the human has the ability to write a test for the model or interact and say。

 what's what's the output if I do this and test those things same thing with model judgment or even you can use that execution output somehow to compare reference solutions as well。

 So this is kind of the general space， but I imagine a lot of these things are actually going to be stronger together to measure the capabilities or our models。

And getting a little bit more into some of the methods。So this is， this。

 this portion of the talk is structured very much like。We've got LOM recipe。

 so the Santa recipe before LOM is pretrain them on a large corus of data in between them on some smaller。

 but still know somewhat large high quality data do maybe some RLHF to kind directly correct some of the models mistakes or shape its behavior in some way。

 and then we have inference time methods like best end where you can sample multiple things and then choose the best one or retrieval augmented generation。

 which is basically just when you find either heuristically are the model finds some context to put for a specific generation so that it you're kind of prompting it in a certain way to get a good answer and you can retrieve that based on like similarity of a database of solutions to the problem that you're currently using search or kind of tool use at inference time。

 So all these things that once you've already trained the model。

weightights are fixed that we can do to get the best behavior out of our model。

And then you can basically do all that but for code and yeah it basically looks like what you would expect you pretrain your LLM on a large corpus of code data。

 you instruction tune on some code data， you do RHF on code prompts that be quite a boring talk if that's all I discussed。

 but that is most of the pipeline。 So just kind of putting that out there and so we can understand that this is mostly very similar。

 but there's also some specific challenges that we run into when we're using models for code generation because of the specific challenges of writing code so we need models that can handle really long context for understanding what is going on in the rest of my repository or that can fill in the middle。

 not just kind of generate left to right but usually when you're programming you want to go back and right code between some other parts of the repository And like I said previously。

A lot of times we need to create many samples because this property of like the sharp drop off of correct code solutions。

But we also get， and I would say I I'll probably focus a bit more on this。

 some code specific opportunities。primarilyrimarily with code execution that we can。

 we can execute the code and we can use that signal for data filtering for optimization signals。

 for synthetic data generation， for inference time， feedback。

 So you can imagine the model debugging its own code and getting feedback from a compiler to say no。

 that's not right。 Try again。And you can optimize the code performance。

 things like the speed of the code to latency。So this is kind of the。

 the basic area and kind of going back to the standard recipe。 the。

 the main thing that we're going to need is some data。

And so probably one of the most obvious data sources is we're lucky enough to live in a world where open source code is available and primarily all in one place so actually on Gitthub we have 300 million open source probably permissly licensed repositories。

 this is the data as of 2023 from their kind of state of theoctaverse report and so that's a really。

 really great starting point to leverage all of the open source code that humans have written and understand yeah what it takes to kind of write that kind of code。

😊，And。There's different structures that we can have for this data as well。

 So you can imagine like the most obvious thing is just the plain code tokens as they come。 But also。

 there's some special metadata on Github。 and you can leverage something like the transformation of code and Github is not one kind of static thing。

 But there's also issues that people report and people at pull request。

 So it's changing all the time。 And so this kind of dynamic flavors。

 things that you can leverage to get data in that way as well of this kind of like how do I transform a piece of codes。

So other data sources and kind of most of these data sources。

 you would need to either acquire some sort of license or pay for in some way。

 But just kind of for completeness， we can understand what are all the kind of code what is the code data that exists。

 there's things like competitive programming competitions， academic materials like coding lectures。

 bootcs exercises， stack overflow where we've got a lot of great conversation about code and questions and solutions and things like that。

 you can also purposely like use human data generators to create your own data。

 And thens I would say a lot of the world's code lies in enterprise software。 Obviously。

 that's not readily available in most cases， most of these things。 like I said， are not。

 but maybe if you have a company that you have a lot of enterprise software。 and then you want to。

Some tools on it， that's also potentially like a data source。So okay。

 let's say you have your code data and now you want to train your model。

 One question that you might ask is， should I just turn on the code data or should I start with。

 should I mix it with kind of natural language data Should I start with a foundation model。

 So there's this question of like， is there transfer。

 Like is is it worthwhile to train on natural language data， if all I care about is code。And so。

I think this is kind of a back and forth in some ways。

 But the way the things kind of stand right now， I think most people are converging on this idea that that。

 yes， starting from a foundation model is usually a useful thing to do if you think about like when we write code。

 especially if we want to write code that adheres to some natural language specification。

 it's useful to understand what that's saying。 And there's a lot of reasoning behavior and natural language data that we can maybe use to help write our code。

And a somewhat related question is should we create one model for to do everything or is there any merit to creating a code specialist model。

 And I think there are a lot of code specialist models right now because if all you care about as code then you can use your model capacity just for that then you can tend to get better performance So there is a benefit to creating these kind of code specialist models on here is the code lama diagram。

 they actually have in this paper they release not only a code specialist model。

 but then a code instruction specialist model and a code python specialist model to really get the most for the applications that they careed the most about。

 So obviously this depends on your use case and what you care about because there's tradeoffs with these things but that can be a useful thing to do one reason that you might want to put your code data into your normal model is that there also is kind of a transfer going the other way。

 So training on code tokens improves you know your。capabilities in other non coding tasks。

 This goes back to that kind of Steve Jobs quote that I had at the beginning about coding， teaching。

 how to think。So one other thing to consider when you've got your code data and you're want to kind of start this。

 this LLM training is that code data availability varies a lot by language and also probably by a lot of other things。

 But language is the most maybe glaringly obvious one。 There's a lot of， Python data。

 but not as much asll。And so balancing the programming language distribution can help performance on rare languages by a significant amount。

 So like， on average， you know，12% higher pass K。 And there's a trade off here of。

 I think the the improvement on these rare languages is like a lot is like 50% or something。

 I can't remember what the exact number。 But the the you know， high。

 high availability languages drop a little bit， which is kind of what you would expect if you're doing this kind of balancing。

 So all those considerations to think about But if you want a kind of code generalist model and this is something that you might be interested in doing。

 because you don't want your model to think that coding just looks like Python。So another thing。

 another kind of consideration when you're formatting your data you're bringing things together is in filling。

 which can allow you to train your model to do more than this kind of simple like left to right generation。

 but to fill in the middle between code contexts。 So that's useful for if you're building a in IdeE code completion tool or repository level coding tasks where you need to edit code and models don't out of the box have this kind of capability because most of the data that they're trained on is this kind of left to right flavor。

 So specifically formatting your data in this way so that the model knows know where it can how it can infi how it can break this kind of causality。

 sometimes that we're used to in most other language data can can improve performance on a lot of coding benchmarks。

嗯。Now we'll get into a kind of a case study on competitive programming。

 So I talked a lot about the human Eval benchmark previously。

 which is a very kind of maybe entry level programming like it's a function generation thing and what's nice about it self-contain。

 It's quite a saturated benchmark now and competitive programming is kind of one step beyond some ways because you still have a very welldefined problem。

 you still have somewhere where you have a lot of data sources and you can execute it reliably because you know what the format of the problem is but the problems range in difficulty to being much。

 much harder。So competitive programming， I think， has been around since like the 1970s。

 and it's exactly what it sounds like here kind of dueling other people to see how you compare on on generating code for very hard problems。

 And there's often a lot of like time and memory constraints for these。

 I put an example problem up here。😊，I won't go into reading it。

 but basically these word problems that specify some you know varying level specification gives some example input and output and then like I was talking about with the public and private test cases previously there are a lot of websites like code forcess which host these competitions and then you can go in and submit your solutions you can submit like a certain number of solutions and they have some private test cases that you as the programmer are not ace that you don't hack your solution you can be sure your solution is generally tack tackling whatever the kind of function the desired functionality is so this is an external competition that you know people are participating in and that's often a really good way to structure some machine learning research because you have this kind of gold standards external judging factor that can help you really understand are we making progress with these models。

So over the last couple of years， there's been from some of my colleagues at Deep Mind。

 this competitive programming with Al code effort。 and here is kind of the diagram of that system and we'll go into like a few different components of the system so we can understand how we've。

Yeah how they've been successful at competitive programming。

 So first zming into the top kind of block here， the basic structure is the top is kind of this general fine tuning like we've seen And then the bottom is what we're doing at sampling and evaluation time and that's where we can leverage some of the code execution properties to make the most use of our data。

😊，And so this is the kind of zoom zoomed in on that top component from the last slide。

 looking at the fine tuning stage。 So as we were saying before。

 starting from the generalist language model base So starting in this case from Gemini Pro and then doing a couple of different stages of fine tuning to create a family of models on a competitive programming data set from codehors called code contests。

 which is basically a lot of examples of this structure of data with a lot of solutions per problem。

And they also use this， this objective called gold， which is basically an offline R L objective。

 So instead of doing kind of maximum likelihood next to and prediction。In code。

 we have and especially in competitive programming。

 like there's a lot of because we have so many solutions per data point。

 and there's a lot of different ways that you could answer the question。

 Some of them might be easier for the model to do。 Some of them might be farther away from what the model is able to do。

 And we only really need one solution that works。 So the objective of this is to create like any is to get any solution that passes the test。

 You don't need to cover the entire distribution。 And so what this does is this adds a weighting term onto your maximum likelihood loss that basically weights things that the model was already going to had some likelihood of predicting and down weight something that it wasn't going to predict in the first place。

 So it has this kind of this flavor of looking at what the policy was was going to do in the first place。

 And that allows it to focus and really focus on the precision instead of the recall to get good solutions。

 but not worry about getting every possible right solution because that's not what we actually care about。

And so there's two phases of fine tuning here on like a larger data set and then a data set that is made sure to be like very。

 very high quality that has the same kind of structure。And then you have these kind of models。

 And then where actually a lot of the kind of success comes from actually。

 is this next phase of sampling and evaluation。So looking at taking in the problem。

 this is that test time， you' you have this competitive program problem。

 you wanting to send it some solutions。 you can take your models and then do a lot of samples。

 So in this case， looking at something like 1 million samples per problem And so you get know1 million examples from this different family of models and I don't think I said this on the last slide。

 but the purpose of doing this like family of fine tuneed models is just one model is that you get more diversity in the generations that you might get they sample for a C plus specifically trying to they basically tag say I want C+ solution because that tends to be the most efficient of the solutions in the training data。

 And then what they do is they can execute these solutions on the public test cases and potentially some synthetically generated test cases。

 So you have the input and output of these programs and you can。

Use that to create clusters of of solutions because you're only allowed to submit a certain amount。

 And so you can't submit all 1 million because that would be you could just kind of submit anything at that point。

 And so you need to make some decisions about what solutions are are useful。

So you can at least create these clusters to get this kind of diverse set of， of solutions。

 And then you can use a fine tuned reward model to choose which of these is most likely to kind of pass the。

 the hidden test as well and rera them。 And then finally。

Submit them to the competition to be truly evaluated。

So this is the solve rate compared to the sampling budget and I don't know if I mentioned this there were two kind of iterations of Alvo code when was in 2022。

 the last one， late 2023， and you can see this kind of sampling budget per problem and there's no sign of slowing down either you have a million problems and then the solve rate kind of keep a million samples and the solve rate keeps increasing So this is the solve rate on recent context So getting about 40% when you have these million samples。

Which may not sound like much， but this is actually。

87th percentile for all kind of human competitors in these competitions。 So This is actually very。

 very top level for competitive programming， which is quite an a exciting milestone。😊，And actually。

 just last night， Open AI drops the01 model and they have this as kind of one of the benchmarks they've used and this the graph on the right is showing kind of G 40 and how01 model compares to that by using again a lot of this inference time compute to get a correct solution。

And。So I think I had one more。And yeah， so you can see the sample budget here and how things scale as you have a higher sampling budget。

 they scale better。And so this is a really great tool。 But obviously。

 this is a super expensive thing to do。 And in both of these cases。

 this is a super expensive thing for to do for any kind of。😊。

Everyday use case or something when you're not trying to， you know， win this one competition。

 And so I think a lot of the challenges is gonna be to figure out how we can actually do this in a more efficient。

 cheap way and kind of be able to scale up our inference time compute without。Just breaking the bank。

嗯。And now I'm gonna get into a bit of further like optimization behind human data。

 Weve got a bit of a flavor of it with the alpha code。

 with the way that we're selecting and kind of optimizing at test time。

 but we're still using in that sense， like all basically human data。

 and I think we can do really amazing things when we go beyond that。😊。

So looking at optimization beyond human data， I have a couple of kind of case study examples here。

 So this first one is called Al Devev from 2023。Also from some of my colleagues discovering faster sorting algorithms so basically you can use reinforcement learning to optimize for not only correctness but also program latency and starting from in this case they kind of set up this game where the actions are generating lines of assembly code and the states are kind the program this thus far and then also the current state of the CPU to see that what's going on and their reward is this cul of correctness and low latency and what they discovered is that they can actually find a faster sorting algorithm than humans had found to do this thing is now integrated into standard sorting library for C++ and this is kind of I think the first time this library had been touched in this sorting library this function have been touched like 10 years so is quite an exciting thing that there are gl。

AsIm moving beyond what we can do as humans。Another example of this is this paper called FunSe。

 which stands for kind of function search， which this is taking a completely frozen model。

 so not doing any training in contrast to the last ones're doing RL and the goal is to find better solutions for in kind of case study on these capsat and binpacking problems which are very hard mathematics problems but evolving the solution generating program using few shot prompting of a pretrained code LLM。

 so basically starting with kind of a specification they take a prompt and they record any previously successful solution and the thing about these this class of problems is that there's an evaluation that is a sliding scale and basically you can get more and more points and they were able to create new solutions to these problems。

By simply prompting with a few shot like increasing you know this here's one solution that's okay。

 here's another solution that's even better。 Now you know what can you do and basically using the LLM as a source of diversity kind of a diverse solution generating thing。

 and then because we have this evaluation function that we can just run and check and get verified we can use that to actually create new solutions So the kind of interesting component there to me。

 at least is this this executable verification function that we can then use to create better and better solutions。

And there's other work on execution based reinforcement learning。

 so there's a paper called PPO codeder， which trains an RL agent to generate code with a of rewards and that includes compiler feedbacks like if you have test cases do they pass is there error signal and as well as some combination of syntactic and semantic matching？

To the correct solution。 So this actually in practice looks like getting the abstract syntax tree or data flow graph。

 So I think earlier I mentioned these multiple representation levels that we can have of these programs and if we can match those things more than we can we talked about this in terms of evaluation。

 but a lot of the times what we find is that a lot of things that we do in evaluation are also equally as valid due in training so we can use the compiler of feedback and the test case generation as a signal that we can then optimize to create correct and correct code as per the test cases and also as per closeness to some reference solution。

 as well as the KL penalty。 So they actually found that the compiler feedback is the weakest of these rewards in terms of their ablation。

 it didn't help as much as the other rewards。 but it does still make an impact。

 And I think this line of work super exciting for seeing how things can progress as we go forward。😊。

うち？嗯。Now。We'll get into repository level coding。 So everything that I've kind of talked about and then case stay on up to this point is very self-contained。

 welldefined problems。 But a lot of the times that's not how actually， probably most of the time。

 That's not how we actually write code。 we usually go into a code base that's existing。

 and sometimes maybe not you know， the cleanest or the most well documented。

 And then we need to make changes to this code in order to achieve our aims and then leverage other you know。

 libraries and leverage other pieces of code。 so that we can achieve our aims。

 So now we're going into this kind of like repository level coding。So in 2023。

 this benchmark called Swbench was created and Sbech basically sources task instances from real worlds repositories from Python from GitHub and they basically take GiHub issues and pull request and they create this kind of data set out of this where basically this kind of evaluation data set where the goal is to basically go from issue to pull request so that the repository is passing whatever the failed tests are or whatever the issue was or whatever the new tests are。

 so the kind of。The evaluation metric here is this executable correctness on all the test cases in the repository。

This is a very hard problem。And this is a very hard problem for a lot of reasons。

 So this is one requires ultralong context to be able to fit these repositories in memory so that you can usefully address the problem。

 And especially because a lot of the times bug finding is very like needle in the haystack kind of issue。

 You have all this code the problem is in one file that you need to you need to first locate and then address And that requires So that requires multiple steps of reasoning to be able to find。

 okay， what's the problem。 Where is it what would solve it and that's not something that's usually doable and kind of a single shot thing。

 So a lot of the times requires more agentic type of models that can interact for multiple steps with some sort of environment。

This also requires generating data in a patch format and this is a different format than a lot of other data is in。

 so like even just generating this kind of di for the models can be quite challenging So it just less obvious than maybe a contiguous format。

 and there's less data because each of these data points is very complex。

 So all of this together means that this is very hard problem I think when they created this benchmark in 2023 the highest performing model。

 which was called I is getting like less than 2% on this benchmark。

 now we've know as a community made a lot of progress。

 and now how about 22% on this is the leaderboard as of yesterday on the sweep benchmark and so you can go at any time check how models are。

One benchmark and so there's been kind of a lot of rapid progress made for these models on Sbench despite all these challenges so working on hard problems is usually once you specify the problem。

 again going back to evaluation， it kind of rallies a lot of people around trying to solve it。😊，Okay。

 so we've gotten through quite a few case studies。 So now I really briefly want to talk about what's next。

 So we are。Looking back at kind of what I've just presented。

 we've had a lot of rapid improvement in the last， you know， couple of years。

 Cogeneration has absolutely taken off in a lot of ways we could have only dreamed of， you know。

 five years ago。And there's amazing capabilities that lie inside of these models。

 but lowering the cost and the inference time Comp and sampling is going to be key to scaling impact。

 I think this is true of the alpha quo system。 and this is also true of the one model。 I think。😊。

Generally， that's how progress gets made a lot of the times is you do something you no matter what it takes to no matter how expensive it is and then try to consolidate that knowledge and improve thats there's also room for improvement like even though we made drastic progress on Sub bench it's still very very low compared to a lot of software engineers and on these natural。

 more real- world software engineering tasks。 there's a lot of room to go。And there's more room。

 I would say， to fully leverage these special properties of code that we're talking about and putting them in every kind of stage of this pipeline and optimizing them to their full potential。

 these kind of code execution or multiple layers of representation that we have for codes。And。

I talked about this a little bit during evaluation。

 but especially as we add you know code execution to more and more parts of the pipeline。

 One thing that we should really keep in mind is the safety of executing that code。

 So having proper protocols for executing that code in isolated sandboxes as well as being mindful that the code that the model generates is not always right and could be potentially be harmful。

 especially when you're doing things like displaying that code to users So yeah always kind of keeping that in mind。

And so we're back where we've started and I think cogeneration will kind of help us continue to make progress in machine learning and I hope it serve as a useful lens to understand some of the more some of the lessons from this week I really appreciate your attention I think we have about 10 minutes now for our questions。



![](img/da6ba9f8d804a927e35dfbc8d49ef072_2.png)