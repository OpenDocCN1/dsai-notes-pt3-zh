# 斯坦福大学《深度学习自然语言处理｜Stanford CS224N NLP with Deep Learning 2024》中英字幕（deepseek-R1 - P16：-16-Lecture 15 - After DPO by Nathan Lambert.zh_en - GPT中英字幕课程资源 - BV1U5RNYgEfp

![](img/6b9bbcc5d4d2e23b44f1c4d24dbd64a6_0.png)

![](img/6b9bbcc5d4d2e23b44f1c4d24dbd64a6_1.png)

Okay， well， welcome back to CS S 224 N。 welcome back from me to CS S 224 N too。

 since I was traveling for a couple of weeks。 I everything went smoothly in the meantime。

 So today I'm delighted to introduce our first invited speaker， Nathan Labert。

 So Nathan did his PhD at UC Berkeley。 So you're allowed to boo and his for that。

 But since then he worked first for a couple of years at Huging F and now he's working at AI too。

 the Aen Institute the Aen Institute for Art In in Seattle。

 So Nathan comes from a background in reinforcement learning。

 like quite a few of the people who are now applying reinforcement learning to La models。

 He had an earlier background applying reinforcement learning to robots。 but it turns out。😊。

sMore fun to do it with language models。 No， it's not。 Okay， But anyway， I mean。

 he's been very influential in both developing ideas as to how to do posttrain with RHF and other ideas that come since then。

 including DO that he'll definitely mention in today's talk。

 And so he's one of the sort best experts on the posttrain phase of language model development。

 which has just proven as time has passed by the more and more of the action and the large language model companies is happening not in the the initial pretraining language model training phase。

 when this subsequent posttrain phase。 And Nathan will have a lot to say about that today。

 Thanks a lot for coming to do this。😊，Yeah， thanks for the wonderful intro。

 You can see my talk is life after DPO， which is a little bit of an unclear title。

 So I apologize about this， but it's trying to capture like。😊。

What is the moment that we're at in alignment and alignment research。 And really， DPO is the paper。

 the story of last year， which is this paper that came out。 And I'll get to the math。

 And now a lot more people are interested in able to do alignment。 And it's building on from there。

 So it's like， what what are we gonna be interested in after DPO。

 And a tidbit talking with Chris that isn't explicitly in my slides is like what we're trying to close and。

😊，The labs， like Me and people with the amount of data that they're using for this kind of post training。

Fine tuning English， all these words all defined is so big that like the amount of data points that meta bought in Lama2 from one of these providers is much more data than all of the data that's been collected on chatbot arena from Lms。

 So chatbot arena has like 800000 data points that have been collected in Me2s papers says they bought about 1。

5 million comparisons。 And these are years outdated than chatbot arena's data that's as of a few weeks ago。

 So you can only imagine what open AI Anthropic， etca are buying at the scale。

 And this is the kind of reality that we need to adapt to is like what is different Like we don't have that type of resource doing research。

 And what are we gonna do。 So this lecture is some history on things that lead up to DPO that I saw that I think are important to remember。

 and then。Really， what kind of goes0 to 100 and talk about recent research that we're doing to try to answer this question and define what is happening。

So I'll start with a heavily abbreviated history of language models。 I won't go through all of this。

 There's a bunch of this in the class already。 This is late in the lecture。 I like to talk。

 start with Claude Channon。 and then you skip a whole bunch of stuff where this autoregressive loss function。

😊，Shows a lot of promise。 and this was not fast。 You can see how many years that it took to build language modeling as a field here and deep learning is brewing in the background of one of many things that went into this and then you have these years with like 2017。

 the transformer paper that you hear about 2018 with G1 Elmo and Bert kind of these foundational topics in language processing and how embeddings are created。

 and then with G2 and scaling laws become this kind of key idea that people are looking at and tracking and how these models are improving。

 And then in 2020 is when people really started to wake up to how useful these large scale trained language models were。

 at this time I wasn't even a language modeling person。 But for a lot of people in AI。

 this is when the kind of gravity of the situation was starting to suck people in and there's a lot of cadence to these things in 2021。

 we had the stochastic parrots paper， which before ChattBT is raising the warnings of what are。😊。

What are we actually putting into these models and what are they learning。

 Like are they actually learning something meaningful from language or are they repeating the language that we have。

 And this is a kind of philosophical debate depending on where you land on what language is。

 what these language models are doing today， but it's important that it came out before TTT。

 and it's like these foundations of debates of what language models are doing。

In0 end of 2022 is when Chat GBT actually came out。

 which was supposed to be this kind of quiet launch of like a demo from Open AI。

 and it has since captured the attention of the world that we have seen。😊，And the simple question is。

 can chat GT exist without RLHF， I think it's important to acknowledge that so much of this is from pretraining。

 but at every point of the line and chat GT and then a lot of these popular models since then。

 RLHF in these human related or other fine tuning technologies seem to be necessary。

 but not sufficient。 Like you need the pretraining。

 But you also need this kind of RLHF for this posttrain to really shift the needle on what the most important models are at that certain moment。

Some examples you can list so many of them where RLHF is relied upon。

 I like to look at these plots from the anthropic constitutional AI paper。

 where they kind of show this iterative improvement of their different RHF methods。

 It kind of shows how you have these multiple model versions that are evolving over time as you add more fine tuning data This is a dense paper。

 but one of the most representative figures and kind of what RHF can do。

 there's a lot of information in here。 they don't need to follow right now。

 And then like metatas Lama 2 paper is pretty funny where they have this quote is like reinforcement learning known for its instability seemed as somewhat shadowy field for those in the NLP research community。

 However， reinforcement learning proved highly effective。

 particularly given its costs and time effectiveness。

 So this this't from the technical report directly which I find really entertaining this is back in the day when we were like。

 oh we don't know if RHF is really going take off。 This is July of 2023 is like in this building period。

 and it's just directly from the report。 and that's aged really well where people are still using this today。

😊，But there's just a lot of interesting hints and kind of history of culture of R LHF in the releases of these models where the people of these companies like to talk about it and give us kind of these cultural details to what's going on。

😊，So I'm going kind of go through some definitions and。

I don't spend too much time on say doing RHF 101 in exactly what is happening with these kind of mathematical terms。

 but it's important to get on the same page of what some of these things do and don't mean。

 there's a lot of definitions I think some of the interesting ones that if they don't make sense right now to come back to is like what's the difference between instruction fine tuning and supervised fine tuning I think like instruction fine tuning is what's become really popular where it's like you're training a model to follow instructions and I have another slide on this after and supervised fine tuning is like this domain specific thing。

 And we want to do both of them。 I think instruction fine tuning is more linked to RLHF。

 it's about making these models really useful and really engaging and kind of easy to work with And then there's other things like alignment which is like super vague but it's in the word it's aligned It's training a model to be mirrored to what a user wants and there's a lot of things that you can align to RHF is a mouthful which is one specific tool for doing alignment where you have this kind of human feedback data。

Which is like feedback is a really loaded word there where there can be like preferences and learning to rank is related to actually putting feedback on preferences。

 There's a lot of little things。 I tried to make preference fine tuning a phrase at one point。

 but didn't really double down on it， I think it's a little bit clearer than RLHF。

 especially in the context of DPO， but there's just these lot of spheres that are overlapping in this kind of posttrain or fine tuning space of models these days。

Instruction tuning， instruction fine tuning is the kind of still the foundation of a lot of this。

 this is where things called system prompts are added。

 where we're like making the model ready for a specific style of input Open AI is still kind of innovating on this。

 They have this model spec document they released a few weeks ago where they said they're going to have like a second levell system prompt here。

 which this just adds some structure to how the models can take in data so that you can do a lot more of this fine tuning down the line and how user data actually gets passed to the model or how the developer passes information that the user doesn't see。

😊，So what this can often look like is like stack overflow Reddit data where you have a question at the top and then an answer。

 And this is still， I think a lot of what is happening behind the scenes。

 There's a lot of data sets of stack overflow out there。 Reddit has these data partnerships。

 and this still uses the autoregressive loss function that we started with。

 We haven't branched out into kind of different loss functions yet， but still super important。

 a lot of academic research shows that this is like all you need in some ways which I think is a much more mixed bag。

 buts it's the simple method and it's the right place to start。😊。

And where we kind of go is then we go to this RHF objective， which。

This looks really familiar to people that are trained in reinforcement learning。

 I think this is a little different from the NLP loss function on the left side is like the standard reinforcement learning objective。

 which is you're learning a policy pie to maximize some reward， which is a function of something。

 depending how you side of the problem。 And then on the right side is going to be this kind of KL constraint It's a distance so that the policy doesn't change too much。

 It's related to this whole idea of over optimizeim that don't go into too much of this talk。

 But the key idea is that we want to optimize a reward， but not over optimizeimize it。😊。

And the primary questions when doing RLHF is like， how do we implement a reward function。

 like what is our reward actually going to be and then how do we optimize it？

 You see this abstracted later as like we train a specific reward model。

 and then we have specific policy updates。 and DPO direct preference optimization handles this a little bit differently。

So to get before we get there， it's like the actual preference model that people use for RLHF is what I find this interesting。

 like it's from this Bradley Terry model， which is from economics in like the 1950s。

 which is essentially a probability distribution over a pairwise choice。

And what ends up happening for various technical reasons is that if we chain a preference model。

 it needs to output a scalar value。 And by some coincidence， I think is still very convenient。

 They just take the output of this learned probability distribution as a reward。 They say that， okay。

 a reward is gonna to be proportional to this probability。 and it's gonna to work。

 And it ends up doing so。 But that's like even a big leap to accept that。

 like we have this pairwise preference probability that's saying the probability that one answer is chosen over another。

 And then you have to kind of this mental crazy step of saying we just pass in one number or one piece of text。

 and we're getting the probability that that one piece of check is chosen over any arbitrary other one。

 So there's a lot of like assumptions like make there's like kind of deep。😊，Concepts in here。

 but what we're getting is a model that's giving us a score out。And the kind of question is， if we。

 why do we have to do this And like， what if we can just take our original objective and use gradient ascent on this equation。

 ascent， because it's a maximum。 And this is really what DPO does。

 I'm blurring through a ton of math。 It's a great paper to learn a lot of this math of language modeling where you've learned how these。

😊，Probabilities of different pieces of text are handled by the model and how it ends up being a lot of these like log probability ratios and seeing how the prompt and the completion are handled differently。

 It's worth digging into and understanding the derivation。 But the core idea is， like。

 why can't we just do gradient descent or gradient asscent to solve RHF optimization and。😊。

This is like it becomes incredibly simple。 So if you look at the code on the right as a reference code from the original implementation。

 it's extremely simple to implement and it has this characteristic where if you work with something like transformers before。

 it's pretty easy to write a loss function that uses DPO rather than building an entire infrastructure stack to start with when you do something like PPO and this full RHF stuff that OpenaiI does。

 you normally need a homeless entire new infrastructure stack。

 but you can get started with DPO in a much much simpler way。

 and there's some kind of characteristics that I'll get to later。

 which is DPO still has a reward model， which is really important to the math actually checking out where you're using your original language model as a different type of reward model。

 but that quickly takes us down a whole bunch of deris that is probably at least not the lecture that I think is as fun to give。

😊，And the key thing is， which is why this lecture is called what it is。

 is that the first two points mean we'll see more DPO models than anything else。

 like DPO is where everyone will start with if they want to do alignment research and it's for a good reason like it is the right place to start if you're thinking about doing this。

 it scales more easily on compute， it's easier to debug。 it's even easier to learn。

 So like it's not really worth second guessing that And it is a good place to start。

But it also leads into these ridiculous conversations online where everyone is trying to figure out like。

 is DPO better than other RL methods， PPO， which is this older， popular DRL algorithm。

 which John Schulman wrote， reinforce， which is a slightly different parameterization of policy gradient。

 they're very similar。DPO ends up being much simple。 like it's just simpler to work with。

 So there's this meme where it's like if you you just do gradient ascent， it'll work。 In reality。

 they're pretty， they're different loss functions and they're doing very different things。

 But you can get similar results with both of them， which is why if something is much easier to do。

 you should just start with it。 And I come back to this much later in the talk。

 which is like what is fundamentally different about these RL algorithms and how your data is processed and where the signals actually come from。

 But for now， it's like we don't need to say one versus the other。

 we can do both and they are different。So that's kind of a quick one on one of what the core ideas are。

 I'm going to kind of take a path to where。How we actually got to training models with DPO because I think this slide was from a different talk where this subsection is reduced from。

 but DPO really came out months before we started getting popular models trained with it。

 so it's like how did we actually get to the point where the community was training models with DPO which is much more recently than the paper was actually released？

And this comes all the way back to these first instruction tune models that you saw。 So the alpaca。

 the Viuna koala Dolly of the world， all in April of 2023。

 And these are all built on kind of similar things and slight iterations。

 So they're kind of figuring out how to use synthetic data， building off those first llma release。

 There's some other things that I'll talk about。 but this is where we started。

 They're all using instruction tuning。 Most of them use synthetic data and。😊。

What Viuna actually did was they used this thing called share GT。

 which was the first time that people working in kind of academic alignment space had access to data that was from humans。

 It ended up being a bit of a legal gray area because it was logging data that people used in a Google Chrome extension called share GT to like make it so chat GT had to share button。

 But this data is really important to things like Vikua and a lot of the other models that came down the line and is still used in models today as like one subset of the training data。

 So just having access to these human prompts， was unlocked a lot of potential back in the day and is still something that we're seeing。

 thankfully now we're starting to get data sets like this that were collected in more permissive ways like this kind of LMs data has prompts that are collected with consent and wild chatt。

 which was a project from AI too， which essentially gave people free access to chat GT and exchange for their data。

😊，The thing that came after Sha GPT was the realization that we need more human data and this open As project is one that we honestly need more of。

 it shows how hard it is to create human data that we haven't seen more things like this。

This was run by a few people in a discord community working extremely long hours to generate prompts responses and preference pairs to kind of common requests whole language models。

 And this was from April of 2023。 And we haven't seen anything like it。

 Cha or LM says data is similar， but there's not the same level of controls and voting and ranking that they went into this open assistant data。

 And again， is a data that we're still training models with and many people still train models with they come up time and time again。

 So it's just like these one or two influential data sets from over a year ago are still what are used to trade models。

 So you'll get the theme as I keep going。😊，There was actually RHF models trained in April of 2023 as well。

 This was from Car AI that was doing a lot of work in the space。

 They've kind of taken They've followed back a bit in recent times。

 But there were people that were doing the similar methods to what I'm gonna talk about at the end of the talk。

 That kind of knowledge and infrastructure was not translated into things that were easy to use。

 So there's also this vein of。😊，Even if things are open。

 it doesn't mean that it's gonna immediately catch on and be useful。 You have to have the resources。

 the data and your code base set up in a way that people can build on it。

 which is what DPO did really well。 This like R Jeff model from Carper was successful。

 It was better than the Vikua model， but no one really built on it right away。

 which I always find confusing。😊，Then kind of later in the year。

 another key thing for this open alignment was the Lama2 backlash。

 whether the Lama2 was asked to kill a Linux process， it would refuse。

 And this kind of bred a whole series of models which are kind of are still referred to as uncensored。

 which I don't think is the best name， because I don't think there was ever actually any censoring to the model it wasn't intentional censorship。

 But the goal is to make models that don't refuse any request。

 which is useful as a research artifact， which is like what do you get out of a model if it answers every question。

 Like what are the limits in that regard。There are other ways to use that， which are up to you。

 But like what ended up happening is a lot of these like shared GT data sets because they're from chat GT。

 There's data that says， oh， as a language model， I shouldn't answer that。

 So people start filtering all of that out。 And you still see a lot of people releasing these like uncensored models today It a popular area of development。

I think that we should understand what people need when doing research and researching a model that doesn't refuse is reasonable。

 but if you're to deploy a model for free use to users。

 you should consider whether or not everything should be answered。 So it's like as a researcher。

 how your artifacts are used kind of depend on the work that you're actually going to be doing。

Then in the alignment space， there's this long series。 I'm almost done with the and lens。

 but there's this long series of models that are really interesting to people like me that never really broke through the narrative where they're saying there's things like we used RHF where the first model to beat G4 on Apaca Val in these other Val tools。

 They're scaling things up。 But they don't always have papers that don't always have code bases。

 And it's like things are happening around。s just like it's not just like the hugging base of the world。

 there's a lot of different organizations in the US and elsewhere that were're aligning models and getting similar numbers or beating these kind of mainstream tech companies in these places that you look for models to these。

 So these are all in the summer of 2023。😊，And this is kind of all these I bring these up because this comes before like the first big splash of DPO。

 So this Zephyr model was really the first model that I remember making a splash with DO。

 And this is when it took until this time which was in September after the may release of the paper for people to really be like oh DO is a real deal。

 like it took four months And now like the paper has best paper everyone uses theres tons of derivations。

 but in industry and people trying to train models， there was a lot of skepticism until this moment。

 So this is like a classic academic story of needing to wait a bit until until your work is vindicated in some ways。

 But the two crucial things here was new data， the ultra feedbackedback data set。

 which is a data set of synthetically generated text labeled by G4 So it's again it's kind of new ways of making data where it's a preference data set we didn't make it it was made by open BMB I think they're based in China。

😊，I should know more。 And then we also just had to do a lot of experiments to make it work。

 There's a weird， really low learning rate that was needed to make this kind of chat model work with DPO。

 which is like 5 v-7。 If youre really plugged into AI。

 you'll know that like 3 e-4 is like the lore of the best learning rate。

 So many orders of magnitude lower。 So that's kind of what it took to get this to work。

 we probably could have done a month earlier。 if we just did more hyperbrameter But like this is the random happensstance of the stories that people now like backcast as like this is the super important bottle。

 it's somewhat random。 And then at the same time I was switching jobs to the Allen Institute and they were already working on this project。

 which is trying to do a systematic study of instruction tuning data along with some of this preference tuning recipes that were coming out because once this Zephybra model came out。

 there's always skeptic like doing it at 7 B is' easy like that's a small model。

 So it's like always an actually scale to the real deal bigger models to be what。😊。

ChadTBT does So it is like， okay， we have some more compute and we tried it on this 70 billion parameter scale and we showed similar gains all we did was use the same ultra feedback recipe。

 the low learning rate and it largely worked。 So this is within two months。

 and then this is when since then is when there's tons of new DPO models。

 anyone all these startups that are releasing their own models of releasing instruct version that is a DPO thing and that kind of continued for six months。

 I think just today I'm starting to see less DPO models which is interesting and then keep track keeping track of them for another evaluation project and it has finally kind of slowed down a little bit。

 I don't know if that's alignment at large， but there is so many I should add a slide that's like a list of the ridiculous amount of DPO models after then after these two this is really when the floodgates kind of started and when like okay DPO really works。

😊，So this is kind of why I say what comes next。 It's like we could retrain models on dataset sets that we have。

 We don't have that many dataset sets， but it kind of feels like we're fishing in the dark。

 like Zephyr was built on the success of needing the low learning rate。

 This twolu2 model is actually trained on TPUs because we have the Google Tensor research cloud So we have bigger TPUus to train these models。

 And it's like how do we do this more systematically。

 And that's where most of what I talk about today on the technical matter is the recent research that we've been doing to just kind of make sense of this and answer the fundamental questions of like what do we need to change about DPO is PPO better and so on。

😊，So this is kind of the reality that I go back and forth in between which is we don't really have the human data to do ourLHF like industry but it is getting much easier to do alignment research so you can kind of choose your narrative。

 I think sometimes because I'm so close to industry and hear about people have I'm like too often on this side but there is a lot of opportunity to do things it feels crowded but being crowded at this point when there's so much investment is just because you're in the right area and most people in this room aren't trying to be professors so if you get scooped it's okay。

It I find it very fun。 so like how do we actually understand what we're doing with alignment and can we improve on these models Like we have to loop to。

 It has a number because we want to keep releasing more models。

 So it's like how do we get better evaluating what we're doing to try to understand this process and then how do we train better models。

 So these are the sort of things that I'm up to I have a few examples of things I've been working on。

 I built an evaluation tool for reward models， I'll talk more about reward models to start here and we need better evaluation because when your training models。

 you need to be able to do kind of what I call like local evaluation。

 You need to be able to get a number that tells you if your training technique is improving the end result。

 You can't wait until chatbot arena evaluates your model because that takes you about a month to get your numbers back。

 you need to be able to run something at your desk that gives you signal on if you're actually doing a good job。

 and we're still pretty behind on those evaluation tools and they're more coming， which is promising。

😊，And then given DPOs simplicity， can we actually improve on that and can we catch on some of the industry rumors that。

They've let it drift aside。So reward benchnch is this project that I started because there are no evaluation tools for reward models。

 My motivation was mostly for transparency， given how much industry says reward models or what you need to focus on。

 they're really important for getting good models out the door。

 And it's like what does that mean Like what is like what does it mean for a reward model to be good。

 If we look at this kind of feedback diagram， which is the one kind of homage to the RL background。

 just feedback loops is like a reward model is in this case。

 the agent is your actual language model pi is the policy， the training data is prompts that you get。

 So in this kind of。😊，Our LHF framework， you have this feedback loop where the policy generates something A。

 which is the action， which is the completion， it goes to the reward model which then scores it。

 but you kind of on the side are looking at all these evaluation tools and it's like none of these evaluation tools are giving us internal insight into what's happening in this feedback loop。

 it seems kind of external to what we're doing when we're training these models。

So we really wanted to zoom in on this reward model and reward models are trained in another kind of weird way。

 The many quirks of RHF。 So in order to train a reward model。

 you need to collect this pairwise preference data。

 If you're kind of using chat2BT lot you'll sometimes see it give you two answers and ask you which one is better。

 This data is literally what is used to train a reward model。 it's of prompt and then two completion。

 a chosen completion and a rejected completion。 but in order to train these models。

 you have to pass both of them in at the same time。

 So you pass both of them in at the same time and it gives you two scalar values。

 use a language model that outputs a scalar just by some modifications of the last layers rather than outputting text。

 and then this loss function I'll show you on the next slide is essentially why you need you need to do this batch mode idea。

 which is you pass multiple things at once and you get multiple numbers out。

 So this loss function is essentially here this R is the output directly from the reward。😊。

For the rejected completion and the chosen completion。

 So you're trying to separate the distance between them and then automatic differentiation kind of updates the parameters so that this distance is bigger。

 So you can't just kind of do supervised learning directly on one thing to say for the reward model。

 There are alignment methods researching that Now， But it's really built on this idea of separating two things and creating a margin in the preferences to kind of learn the decision boundary。

 There's a lot of really specific details in industries such as these models are only trained for one epoch。

 They get really low accuracy scores when you compare them to other kind of trained to set things in machine learning。

And there's some additional tweaks that people do， you can do ensembles。

 Lama2 did this weird margin loss， but none of it really is transformative in how these models are trained。

 They're in this weird place where you can only get about 70% agreement with your annotators。

It's it's kind of the sort of thing of is the noise part of the signal or is it a bug。

 So like in preferences， it could make sense that it's a signal because not everyone's preferences here are the same。

 So not getting full of agreement be like this system might be working。

 We don't want ChaTPT to be fully narrow minded all the time。

And this kind of reads the thing of like how do we actually evaluate these reward models that I was talking about。

 I hear all the time that reward models are crucial to ourLHF。

 but how do we know exactly what types of the final policy they're improving。

 should we include safety in these reward models， how does scaling laws impact reward models and it's kind of basic machine learning questions its like can we evaluate these。

 what should we think about？So what we did is we collected a bunch of prompts and then we manually created chosen and rejected answers for each prompt。

 and then we can see whether or not the reward model agrees with our human created data call that like a win or loss and accuracy point of view。

 it's really direct， we're just doing inference on existing models and we're going to see whether or not they agree with human data。

And this is a slide if you want to go into the academic side of things。

 this was built on a lot of existing evaluation tools that were out there。

 you'll see some common names， Alpaca Val empty Ben or things that you've heard about excess test was on the slide when I mentioned Lama2 being overly safe and there's some other things that are really good but you might not have heard about like this LOM bar data set from Princeton is a bunch of trick questions that I'll have an example on later and some kind of normal names from Anthropic and openAI in here as well so there's a lot of different things that we're testing with this data and then we're trying to get the full picture of like what is going on with these models。

We released this in March of 24 and you can see a key in the bottom where these kind of red circles with the arrow in them are DPO models which you can use as a reward model and then this kind of these dice which look like gray squares when you zoom out are what I described in this kind of classifier type of training and you can see that there's reasonable scores the benchmark is saturated bunch of open models。

 some names that you've seen before like the twolu models and the Zebra models are on here kind of normal stuff where like this is why we expected it's not too saturated but if you look here let's show you where this model is moved in a few months。

 So today we have a lot more models and there's a lot more information here So I get to tell you about more interesting things which is like how open AIs and cohers models do on this which is like I mentioned wanting to do this for Trans but we also add new types so this is where the fifth model ended up so in two months the model that was fifth on a leaderboard is now 31st so we're trying。

We're getting the saturation from people doing research in the area to actually have places that compare their models。

And but we also have models from some closed labs and I'll kind of get into the details here。

 so like some of these are labeled as are different types of models with his LLM as a judge。

LLM as a judge is the idea of if you can ask a language model which answer is better。

 this is kind of how things like Alpaca of Al and MT Ben are built。

 but you can also use that as a reward model。 I told you that I have prompts and then chosen and rejected。

 I could just ask chat G which one is better and see what it does。

 And this is what we added it in as a baseline and this ends up being really interesting because G4 and G40 are not actually as good in this closed domain as a reward model that coher is training So we don't have full information because we don't have opening eyes reward models but we can use their models that compare So we have a lot of different information going into one system about how language models in different parts of the alignment process choose different categories。

So kind of。And kind of go back and you can see like this cohere is across two different months。

 theirs has improved a lot， and then these kind of earlier DPO models that we saw higher up on the leaderboard have been shifting down by more people training reward models to begin with。

And the specific category that I'll focus most on is this kind of chat hard thing。

 If you think about evaluation a lot， it's actually surprisingly common as a topic covered and kind of tech coverage is how evaluation is saturating。

 This is the one feature of our benchmark that hasn't fully saturated。

 And it's really important to kind of having some sort of longevity to the benchmark。

 And I'll talk more about this kind of as we go from here。 So I mentioned this data set and。😊。

It's interesting to understand if you could actually do this problem。

 So what we have is a prompt a chosen and a rejected and the prompt is given an example of a metaphor that uses the following object stars。

 And then the chosen and rejected are two similar metaphors。

 But one of the like you could you can see if you read these what the differences are。

I'm just pausing for the people that are still that are paying attention to reading these。

 but essentially what happens is that the chosen one is about the sky and the rejected is about the moon or yeah so the twinkling diamonds in the sky。

 see you even messed up reading the slide， but ask for stars and it's about this kind of metaphor of stars where they're rejected is about the moon。

 which is also in the sky at night and this data set is a whole bunch of things like this where what they do to create this is they either manually or by chat UptT ask or ask to rephrase a prompt and then you create a new generation from it So you can kind of get these rejected generations that are just off topic and it makes sense for something that would be really hard for language models because they have this association between the stars and the moon but we want our language models to be able to answer questions like this。

 and this is the type of thing where our reward model benchmark。

 which is something that is training language models has the best correlation as something that is hard So this is promising this is the sort of thing that if you're in。

😊，Research is really interesting， So it's really in the weeds。

 but it shows that we still have things to learn about these models。

 and there are things that we can't do yet。😊，But another interesting pattern in safety。

 I mentioned this kind of uncensored models and in safety， we see all the patterns we would expect。

 the breakdown at the top of this table refusals is things that we want the language model or refuse and then this excess test data can be split into something that we want models to refuse and we want models to respond and you can kind of see that there's multiple categories of either GPO models or reward models where the model that handles safety really well。

 refuses things like asking for advice on causing harm and response to something that is borderline。

 but there's actually a lot of models out there that just refuse everything。

 so that'll tank your score on things that response to everything which is kind of the safe bit We were seeing a lot of like tech companies release models like this it just feels like it doesn't feel right when you talk to them but there's also the models that just respond to everything。

 It's like not my job to gate whether or not I should it's not like not the language models。

Job to gate the question is the philosophy there， which is something that we hear a lot about in the discourse of alignment。

 but to see it in these reward models and DPO models when directly probing them at the without asking them to generate text is nice to be able to confirm a lot of suspicions that we have。

So this is back to some of the DPO math， which is。Again， good to know。

 So if you are go into the DPO paper， you'll see equation 3 here。

 which is the reward that is defined in order to make the math actually work。

 and this is very different than just outputting a scalar。

 It ends up being a ratio of the probability of the policy relative to the original policy during training。

 which is called the reference model and this。Isn't it's like it's a very complicated mathematical representation。

 So if you actually take a piece of text and pass it through a DPO model。

 the reward will be something like -200 or something because it's a bunch of log probabilities。

 Probabilities are between 0 to1。 You take the log。 you get negative numbers。

 and you sum all of these up。 So you get a big negative number。

 And that intuitively is like the score of that these models are providing。

 which is very different than the other type of reward models that I talked about training earlier。😊。

And if you have two prompts with a chosen and a rejected equation4 is the math that you actually need to do to decide whether or not one of the answers was better。

 You're kind of comparing these ratios of probabilities from two different models with respect to this reference model which is the starting point of training and the question is when people release a DPO model。

 they normally release model and they don't release all the intermediate checkpoints So this reference model would be an intermediate checkpoint and the training process So the question is like can you do this。

 can you use it as a reward model if you don't have access to all the information and the short answer is no。

 which is all the scores on our benchmark plummet across all the DPO models that we have which makes sense because this extra model is a regular regularizer in the probabilities or it's in the actual reward equation if you go back a few slides like it's in the equation So if what we do is we get rid of this and we stop normalizing equation4 and we just see if it works。

And it doesn't。 but this is。Important because DPO is training a reward model。

 But if we don't always have access to it， we we just can't learn from it。

 We can't use that in another system as clearly。 So it's just a lot to ask for when getting people to release models。

And this is an interesting slide showing coher' kind of progress on reward models in just a few months。

 they released something that was clearly state of the art on our benchmark， a alignment lab。

 this kind of RLHF flow work release something in May and then just a few days later coher sent another number of those like here's our new model。

 it's still better than everyone else。 So it's nice to kind of have this academic industry。😊。

Intersection， but it's very rare and takes a lot of work in terms of networking and building relationships。

 But we're trying to do it， at least in these small niches where the companies are willing to share。

Reward benchnch2 is going to need to just mostly make everything harder and make everything more human and kind of the last point is what I'm going transition into next is like everything I've told you about is about part of this RHF pipeline。

 but I haven't told you how it is impacting the final model that you use at the end of the day。

 which is very rightful criticism which is like if you're evaluating part of the alignment pipeline。

 you should be telling me whether or not the final model is actually useful。

 So this is kind of where I talk about our journey into trying to train PPO model。

 So we're trying to fine tune in a good model。 We spent a lot of time on DPO with this2lu2 work and we wanted to know if we could do better by switching to PPO。

 So this is a lot of its not yet published work， but it's gonna to be out soon。

 So the numbers aren't entirely final， but we're just trying to disentangle what the difference between DPO and PPO is。

At a very empirical level。 So we're trying to answer if it's better or not。

 So what we're going to do is kind of walk through a series of design decisions and see how it affects the suite of evaluations。

 We're starting with this Lama 2，13 B model that has already been instruction tuned。

 The difference between the blue and the red is the gains from instruction tuning for these kind of reasoning coding chat task。

 Instruct tuning does the biggest delta that you'll see among all of these slides。

 Instruct tuning kind of puts the model on the map as being useful。😊。

And it is easy to see gains at the beginning， and then it's harder and harder for us to really keep improving these models。

So what we start with is we add this enthropic helpful harmless RLHF data with DPO and you can see that there is a small bump across all the metrics that we did。

 this data set is known as being particularly noisy among researchers in the area but it is kind of the starting point when you're doing research on alignment it's been around for a few years it's big it's both turn but it's known to be noisy and it' still gives improvement and then what you do is if we switch to this data that was used for both Zephyr and 2lu2 officially this ultra feedback data we get an even bigger bump so this is just kind of showing the difference that changing only the data can give you in a DPO recipe it's normally increases of kind of like zero to2% and in the research sphere trying to ship a model that's a big deal。

So this is kind of where we tread it into new territory。

Grad students worked really hard and implemented PPO and Js， in addition to what they already had。

 And we are like， okay， what happens when we add PPO and reliably across multiple experiments。

's this is one example with 13 billion parameters。 PO just happens to do a little bit better。

 like 1% better。 And we try to change a lot of things。

 and the changing things is where things are get a bit messier。

 So we've heard from industry that using a bigger reward model can be really helpful to getting a better policy model。

Essential， these bigger reward models will be better at nuance。

 they should give label better scores which are used as rewards。

 They should just kind of make this process a little bit more stable if we have the compute for it。

We see that it does improve some things， but it doesn't actually make the model overall much better。

 it's kind of flatlined with like pretty similar data and then just making the reward model bigger。

 which is a little bit surprising to us。And we all this is like this is the most。

 this is the most realistic few slides of the talk。

 but it's like we did this thing where we took the。

 we even were trying to see if our reward model training was bad as we scaled it up。

 So we used reward benchch on the right， which I had told you about earlier。

 which it's not clearly correlated， whether or not these 2，13 B models or 70 B or better。

 And we also did this best of n sampling idea， which is if you generate a bunch of completions from the language model。

 You can rank them by your reward model and then reevaluate on the top rank completions。😊。

That shows that our reward models are better at the bigger scale。

 but we couldn't get this to really click into like a downstream model in a PPO notion of the world。

We even tried adding more prompts to RLHF， we' added more code and reasoning prompts because that's something that Open AI talks about a lot and we want to improve our models on。

 it doesn't really shift the needle on this kind of cohesive average over many tasks in the paper what you'll see when it's out is it shows that we added prompts really similar to two math and code evaluations and those specific evaluations got a bit better but adding the full noise into the fact that some other evaluations might go down makes it this just like this process is really hard to disentangle and this is why it's like we're getting the  zero to2% improvement out of PPO but DO doesn't have this sort of mess。

So what we ended up getting to is there's always one more thing for us to obblate when you're trading these models with PPO。

 the sort of things like different regularization， we're learning a value function in R。

 different warm up different size parameters like there's so many knobs to turn in PPO and it was reliably getting us a pretty good model。

 but it's like we're staring into the bestss trying to improve this right now in the next few months and the bottleneck in terms of the actual technical side is that PPO generates new responses from the model as it trains to kind of refresh the data and that is by far and away。

 the biggest bottleneck when you're actually training these models is it's just way slower than DO。😊。

So all these resources for PPO things are somewhat available to academics。

 the Google Tensil Research cloud， I think is pretty available to grad students I work with seems to sign up。

 the codeb is open。 So if you're interested in grad student and are trying to do PPO alignment and have access to TPUs please get in touch it's it's a very fun can of forms but kind of as a summary like this is the。

😊，Many different DPO data sets that we tried。 This is almost all of the。

Well received data sets that are out there in the open。

 And they all look at like the factuality column like some of these things just don't matter at all when you're aligning these models。

 So like， we need to get new data sets that are really adding different capabilities to these models and。

Something that matches these kind of ultra feedback numbers at the bottom， and。

I don I don't like I'm surprised whenever I look at this。

 but this is where we are at and we need to try to keep building data sets and keep adding freshness to this system。

 Ultra feedback at this point is maybe six months old or so。 I don't know the exact age。

 but in terms of people training models that that feels old to people to things that are happening。

And these are the actual sort of numbers that you get when you compare DPO versus PPO。

 this is all with this 13 billion parameter。 Again。 we change the data set。

And every one of these PPO comes out a little bit better on average。

 And this is a few grad students and people like me。

 this is not a big team in industry doing this like we're scraping by and。

I don't know if it's worth the effort。 If I， Id see why Open AI uses this because we are able to get a bit more signal out of it。

 but it's a ton of effort to get a bit better signal out and。😊。

I'll kind of transition into a bit more of a like open ended discussion of this。

 And then we'll have questions， but it's like。What about PP PO is actually special。

 like this generation and this online nature。 And like。

 can we just change DPO to be like this or like， where are the new things going to go？

 And I had the pleasure of advising one project that was related to this。 But this is much。

 much more general。😊，So it's like what is special about online data。

 there's multiple ways that you can get new data into your RLHF。Process。

 and then there's also this related question in reinforcement learning literature。

 which is like on versus off policy， which is a technical distinction that often gets looped in with these discussions of DPO versus PPO。

 They're actually related， but the reinforcement learning discussions have a very。😊。

Much more like definitional flavor to them。 while in this alignment space。

 we're more focused on if we need to get fresh data in and how we need to label our data for language models。

 So I'd make this distinction between these two things。

 which is freshly generated data from the policy。 If you zoom into a data like culture feedback。

 it has generations from all sorts of models from alpaca Viuna G3。5 G 4 Lama。

 like there's generations from all sorts of models in this data set we are using。

 So when we train these Zephyr， these twolu models。

 we're incorporating information from a lot of different models down into our one policy。

 whereas what PO is doing is only generating data from your existing model and kind of changing this distribution over time。

 So like that is a very different idea of where the signal is coming from from the models。

 And then the second thing is whether or not you're refreshing the data of labels over time。

 If I have human labelers comparing chosen and rejected， that's one data point。 but it can also。😊。

Later on， take this reward model that I trained and generate a chosen and rejected and change the label。

 So these kind of two things of like what the actual text is and when the chosen slash rejected label was given are what people mean when they're talking about like is something special about online in RLHF。

 And it's much clear it's clear to see that PPO does it very differently than DPO。

 but we're not restricted to this。In the last few weeks， I have the dates all in here， so April。

 April and May of 2024， there started to be a lot of papers on this about DPO， PPO， online offline。

And they。Really kind of say similar things， which is that online is important。

And these papers on this slide， they。Show these kind of more theoretical en closed form experiments on link。

What is special about online data and what performance drops if you use this kind of offline data？

It's good to dig into these， but this is what Id say it's like nice to do research now because if you have an idea。

 A lot of times people have like three papers that confirm the notion that you have。

 it's a lot easier to be confident in things if three independent institutions。

 say something similar。 At the same time， there's a lot of methods coming out where people are trying to modify DO to actually use this kind of online notion。

 I think self-rewarding language models for Me was the first really popular one where they just had they asked the DPO model。

 hey， which of these answers is better in between each iteration。

 So they did this like Lm as a judge to relabel their own data and then they did multiple iterations of DO and the model had really strong stores there's now ideas like not using all of your data at once。

 So you can kind do batches of DPO and update your data。😊。

The paper that I was on with this discriminatory guided DPO。

 which I'll talk about in a second is using reward models plus this DPO training objective。

 There's just a lot of things that we can change。 And I think the community again is in this expansion phase where I even get messages from people are like oh my paper was really similar to this other paper that we did it first they didn't cite us and I'm like this is kind of the point but it's hard。

 It's like it's gonna to be like this for a little bit longer and then hopefully in the end of the year in a few years we're going to be like okay。

 this is clearly what we need to do on the methods side of thing So this is one example D2PO discriminatory guided DPO which as an advisor to which is an undergrad researcher and the idea is comparing these three different thing So a is a standard DPO you have a data set。

 you apply the loss function on it B is what we call some sort of online preference optimization which is where you can repeatedly label your data。

The reward model， it is kind of like the self-re paper that I mentioned。

 which is you can reshuffle your preference data based on a reward model and that kind of adds some notion of onlineness to your data And then the third thing is like what if we're relabeling data and we're retraining our reward model over time So we're just really trying to keep our kind of what our policy is doing related to our reward model and keep everything really updated in real time so that it's all it's all lined up and this is wondering how much of a gain do you have by retraining the reward model over time and a DPO framework。

And part of why I like this paper is there's。Things like closed form tasks。

 So the biggest question that I get for alignment is like how do we actually evaluate it。

 Like what tasks is it good for There's a whole philosophical discussion where I think information transformation is a valuable task writers tell the same stories in different ways。

 but the best told story is the one that resonates with people that has value and but at the other time where academics and we need to be able to measure things So this paper has things like your reward is counting the number of nouns in a sentence and then you're using these alignment methods to increase the number of nouns in the output and sentences from the model so you can measure that a lot better because we have classifiers which know our nouns and you can see on this left figure is that just by retraining this reward model a few times and it converges better than if youre just to relabel your preference data It's a mouthful but it's just like keeping your model your training process a little bit more online can improve performance and on the right is a more standard open-ended evaluation task。

😊，where we're asking a language model like chatTBT which answers better and that has all sorts of problems but we can show similar results I think the big takeaway is really like these few slides。

 which is the literature is moving we have studies that show that online is better and people are coming up with really cool。

 clever ways to actually use online data So combined with new data sets。

 this is kind of the like DPO of this year is like online methods and how they work。😊。

So this kind of goes back to what industry is doing and I showed this figure earlier on the left with Claude where you can see the little points along the lines and these are these different iterations。

 we don't know exactly what they're doing。 but it seems a little bit different where the dots on these figures are new data sets from humans rather than this kind of redo a reward model relabel your data。

 This is what happens when you have access to different types of scale。

 The Lama2 paper makes this much clearer， they say they work with an annotator。

 they get batches of data when they're generating this new batch of data。

 the previous models checkpoint was used for generations they do this many times and you can kind of see that they're collecting new human data。

 new human data， new human data and each time they generate human data it is trained for a new model they're doing a lot of training updates and they're kind of building on each other and this kind of leads into the last section that I'll talk about in the conclusions is like what did metata do with Lama3 this is one of the most funny。

Blog post sentences。 it's like the ridiculous things that they give us and then we parse the tea leaves。

 They say in the blog post is that our approach to post training is a combination of supervised fine tuning。

 rejection sampling。 proximal policy optimization PPO and direct preference optimization So it's like the people ask me like what the heck did they do And I mean I kind of agree but it really goes back to this slide in my mind。

 which is that they're getting new data and then they're training a new model over time。

 So what I think is happening at each one of these points。

 they tried a few methods and they chose the training method that worked best。

's it's practical meta is a really practical organization， especially in the Geni org right now。

 and that just makes sense it's like at different points in the model。

 your model has different capabilities and it's ready to be trained in different ways。

 rejection sampling which I didn't cover here is the simplest training method you take a reward model。

 you rank some supervised fine tuning outputs and then you use this。😊。

Autoregressive loss function again and then from there DO is much simpler to PPO。

 but it might not give you the highest end performance and then as your model really starts kicking into gear or you have more time to train this model once all of your data is collected and you're not on a weekly time crunch you can experiment with all the little knobs of PPO and you can really try to get the best model out at the end of the day。

It's just， hopefully they release a technical report that confirms some of my hypotheses。

 But I think this is normally what people are interested in when somebody from industry comes up to give a lecture and it's。

 it's。I wish we had more details on what industry was doing。

But in terms of current directions that I'm most interested in R LHF， I talked about data a lot。

 We are very bottlenecked on data， even as academics with very limited compute。

 we literally try every data set that is available。

 Like that's not like we don't have a lot of compute， but we need to keep innovating there。

 We're gonna see。😊，More DPO methods， it's here to say there's a ton I didn't cover here。

 things like removing the reference model， changing the loss function slightly。

 not using pairwise preferences， but singlewise preferences。It's a lot going on there。

 we should use more model sizes and  seven and 13 billion parameters。Or in Lama's case。

 like seven and 70 billion parameters。Particularly scaling down is very useful is a place where academia can still play。

 There's kind of less of a weird marketing dynamic where all the companies are racing to go bigger for certain strategic reasons。

 but this is something that's accessible to many people aligning small models。

 It's hard to get signal out of them because the models show more or less random scores on many benchmarks that people care about or really low scores。

 So even just kind of breaking through in that domain would be really impactful work to kind of get more people working on alignment。

😊，And then kind of evaluations I covered at length。

 which is we need to keep getting more specific on things we care about。

 And personalization is something in alignment that。I didn't cover in this talk。

 but it's something that is good to compete with this kind of big tech。

 which is like how do we train models that are good for you as an individual rather than one big model for one big technology organization。

So these slides will get to you， but these are the types of places that I follow and I'm trying to see open models or open data sets that are reputable and easy to keep track of so you don't have to try to follow everyone and I write about this a lot without doing too much self-promotion。

 but I have like I end like 10 minutes early for questions that I'm happy to take in a Q&A format and then if you don't have to stay in wait if you don't want to。

Okay， thank you， Nathan， questions。 anyone got questions。😊，就是。good reward bottle。

 which is a large assumption， I agree， but what is the key challenge to doing online detail in sense you can do N rollouts and then just like rank them using our reward model。

Go， and you can。So what is that part？啥子。Yeah， I'm gonna repeat the questions so that people can hear them and it gets recorded。

 The idea is， if you have a good reward model， what is stopping you from doing online DPO and kind of just improving the policy from there。

 I think there's kind of multiple angles to this that。

They're both technical and like the kind of industrywide。

 but the technical thing is I think the prompt matching ends up being really important。

 so prompt matching， so what your reward model can learn is specific to the prompts。

 that are the technical detail where the prompts used for your policy often are exactly the same as your reward model and PPO which is really strange because we talk about generalization and machine learning but we're kind of like softball ourselves at the PPO stage which is we're only grading PPO answers。

 which our reward model is trained to answer。😊，Which is kind of strange。

 so people think that some of that might break down and we see some of that when trying to train PPO models with off the shelf reward models。

 which is kind of a long answer。And then。But I think that' it's like mostly distribution matching。

 if I had to guess， but if we had truly a good model。

 it should work for some things and that could be one of the reasons why there aren't that many in the open because it would kind of help people catch up an alignment is like a reward model if it is as important as people say it is。

 it might be easy。哦。other questions， yeah。Or least don't have this all。Okay wasster。

Mar there at this art。you still have these night grades。

He doesn't more complicated that if everyones。感多。もそめ。said a story。

 example like measured by the that's a lot。お。Yeah， I think this is a whole conversation so if I don't cover it if you want more after I answer I you can come up。

 but the question is like is there more than pairwise preferences that can be used in ourLHF and there's a lot of different lines of work that are studying this one is methods like there's a method out of Stanford that's KtoO liketky I always mess it up these names are so hard to pronounce but it's idea of using one sided preference data so a lot of customer apps have like did you get good support from this agent yes or no and like you could use data like that is it just is a different loss function for using single singlesided preferences or just yes or no there are other things like learning to rank from multiple answers So this is something slightly insinuated but like binary preferences is kind of there's a lot of literature on learning preferences and one of the models that got reduced down is a starling model and they use。

AKwise preference。 So they have like five or nine answers to every prompt and then they collect answers。

 and then they have a different loss function。 And this is one of the models that's kind of like broken through in the open alignment space。

 It's one of the few that I left in and skipped in my slide deck。 But so that's kind of interesting。

 And then there's other research that's like fine grainined preferences。 So for every。😊。

Completion to a prompt。 you get labels likeciness， helpfulness， honesty。

 So there's a few things on that regards。 there's like a steer LM paper from NviIDdia。

 And then there's work from UW that does like learning from fine game grain preferences。

 So that one is probably like the one that's most emerging most in the academic sense。

 but there's so much to learn here。 There's like like literally all the field of social choice needs to get condensed into these things。

嗯嗯。Any other questions？Okay，我个是此假季。不は。Yes， so the question is how can we broadly is like how can we exceed human performance with fine tuning or any training for that regards。

 and I think this is where some older ideas in CSs will come back like I think one of the foundational ideas in CSs is search which is really also motivated as like exploration in RL and therefore we need to have some sort of language models that can search and generate new data is talking with somebody before the grad student and I think that it's like search will be a large part of synthetic data。

 but then the human aspect will be what gets it across the line if it can't solve a certain area and this is like the Qstar riverors are ridiculous。

 but that seems to be the best argument for the sort of thing that open AI is trying with。

It was like how to get that barrier broken with AI。Thank you so much for coming in。

 you mentioned data sets for a big limitation and I was curious how one goes about creating a data set。

Yeah， this is another thing that's hard。 as I think community efforts are what people have tried to do。

 I mentioned open assistant， but most people that do a community effort are like I never want to do this again。

 So while I still think it's worth doing things once that are highly impactful even if you might not want to do it again other avenues for building these in a sustainable manner are very important。

 I think that there's some ways that this is being done like chatbot arena returns some of the prompts in the labels to users。

 there's specific concerns I have with that data around being too noisy but that is the sort of thing that can happen if AI too has a demo for their models it's going to be about science and like generating information rather than being a chat G competitor。

 It's like a nonprofit。 It can't do a product competitor but that's the sort of data that we would want to release and something that I might just have to do。

 but I'm interested in like academic workshops and competitions as。

groundund where you could have communities meet every three， six。

 eight months and have work that's focused on the area and or like focused time to have people contribute to it。

 but it's a good question it's not it's probably why there aren't very many。Yeah， there's。

How do you feel you reward models are submit to reward hacking as well？

so we get yeah close first and then we'll come to you the various places you've done research at over the years do you have any sense。

😊，How they compare in terms of。Specifically alignment。Research， I mean， obviously。

We't doing a lot of research specifically at those。I think generally。

 that represents different culture and investments of the company。

 Like I wasn't doing language models until the time at Huging phase。

 So I can really only speak to these kind of two open companies And from like hugging phases perspective is to show that more people can do this。

 Like we're not trying to compete with chat to PT， but we're trying to foster an ecosystem of doing this And AI too is similar。

 but more about like what is happening， Like how do we learn about this， How do we do science。

 How do we study the science of this and communicate that clearly。

 And I'm sure if you do the exercise， You can map this to every companies。

 Like what is their important thing， like they have different goals and their products in their corporate structure and things like that。

I will talk more when not recorded。Okay， up the back。TheI reward also subject to reward hacking。

 like there is a good result on the outcome， but actual。In reality， the outcome was not。て。Yeah。

 so this is like when talking about reward models， this is probably the most established line of work。

 The question is like are reward model subject to reward hacking and reward hacking is a classic problem in R。

 I should bring back from my RL slides where you have the boat swimming going in circles and then be like this happens to your language model and what happens。

 But it is。 And there's a lot of research to mitigate it， but it's a fundamental problem。

 which is you have a very powerful optimizer and you have an incomplete representation of your reward andll always find where your representation of reward is wrong。

 So it's like we will always be doing the best we can， but I think saying it's perfect。

 It's like not possible in the math。😊，I mean， I can also say。

 like the ways that it fails are pretty funny because like if you train these models。

 you'll end up with a model that just says JavaScriptscript to like every answer to like infinity。

 it's like sometimes it's really easy to see when that is happening。

 which is good or like you could change your loss function so that it will always exploit and like it's a good way to kind of make sure that things are working。

 which is。😊，You should be able to easily exploit if you turn the brakes off。うね。

Any last public question？If not， thank you for Nathan for giving this call。😊。

👏And if there's anything you'd like to ask off the record， he'll be here for a bit longer。😊。



![](img/6b9bbcc5d4d2e23b44f1c4d24dbd64a6_3.png)