# Wk01 - Stanford CS146S - Introduction to Coding LLMs and AI Development -fdquDw1IfmM-

We've all interacted with them。 La language models。 I mean。

 whether it's asking chat G for a recipe or having an AI summarize a huge document。 You hit send。

 And almost instantly， you get something back that feels intelligent。

 But what's actually happening in that black box after you hit send。 It maybe be more importantly。

 what happened for months or even years before you ever type that first prompt。 Exactly。

 That's the core question we're diving into today day。

This deep dive is really about pulling back the curtain on this incredible multistage engineering pipeline that transforms raw。

 messy internet data into the AI assistant you use So we're talking about the fundamental stages of training Y we're tracking the three big ones pre-training supervised fine tuning and reinforcement learning and then we'll get into the advanced prompting techniques you actually need to command these things Our sources today come from some pretty deep technical papers and engineering lectures that you know they really reveal the stunning scale and the clever tricks behind all of this So our mission for you the learner is to really get the true architecture of these systems We're going to trace the models' evolution from what trillions of pieces of text it consumes all the way up to the methods that make it seem like it can reason So let's start at the very beginning before an LLM is a helpful assistant It starts as what we call a base model and what is that functionally functionally it is a massive highly sophisticated text completion machine。

The goal of this first stage pretraining is just knowledge acquisition on a scale that is genuinely hard to wrap your head around The first step being data gathering。

 which I know from the sources is just biblical and scope It really is it begins with this intense data scraping mostly from the deep archives of the internet the biggest source often common crawl that's the nonprofit that's been indexing the web for years 2007 over 2。

7 billion pages and then that raw internet data is combined with high quality curated documents the Wikipedia academic journals。

 public code from Github you said the data is raw which I mean that must be incredibly messy I know they don't just dump the entire internet into the model Oh they absolutely can't the filtering process is ruthless they remove everything spam malware known racist content adult material even just repetitive text but even after all that cull the data sets are still astronomical completely a representative high quality public data set。

Like fine web it still clocks in at about 44 terabtes of text data Wait44 just text that's dizz it is and that text needs to be processed。

 it gets converted into sequences of tokens which are basically small chunks of text a word or even part of a word exactly and that fine web data set alone translates to approximately 15 trillion token15000 billion pieces of training data that the model has to absorb So we have the trillions of tokens what's the core mechanical operation here what are those billions of in GP actually doing the mechanism is conceptually surprisingly simple L are autogress models All that means is that they are predicting the probability of the next token in a sequence based entirely on the text that came before if I say the cat on the model predicts or something like that precisely it calculates the most probable completion and modern models can handle a stunning amount of to make that prediction。

To window， It working memory has gotten huge。 It's grown exponentially。

 an older model like G2 could only handle maybe1 thousand tokens of context。

 Modern ones can look back at hundreds of thousands， sometimes even a million tokens。

 and this prediction is all mathematical。 It runs that context through a neural network with billions or even trillions of adjustable parameters。

 Think of them like knobs on a giant mixing board。1。6 billion for G2 maybe a reported $1。

8 trillion for G4。 and training is just the process of nudging those knobs over and over。

 So the model's prediction of the next token matches what was actually in the training data。

 millionsions of times per second。 and this optimization requires an almost unbelievable amount of specialized computational power。

 This is the gold rush you mentioned It is。 Comp are rushing to rent these massive machines like an apex H100 GPU node。

 which can cost about $3 per GPU per hour。The sheer expense is why training of big foundational model costs tens of millions of dollars。

 That cost analysis really dictates the whole structure of the industry， doesn't it。

 Only a few players can even afford to create these base models It does because every single one of those expensive machines is just trying to predict the next token faster and more accurately。

 So the goal of pretraining is to create a massive lossy compression of the internet。

 That's a powerful way to think about it。 A probabilistic zip file of human knowledge。

 but if it's compressed what information gets lost。 Well， it loses nuance。

 it loses the ability to reason or to understand what is truthful versus what is just common on the internet。

 it learns the syntax of knowledge， but not really the deep structure of logic。

 which leads us perfectly into the next stage。 That base model that expensive autocomplete is not what we use when we talk to Chet GBT。

 exactly the output of pretraining is just the base model to turn it into a helpful conversational assistant We have to enter the posttrain。

And this starts with supervised fine tuning or SFFT is the first step in shaping the model's personality and it's computationally way cheaper。

 We're talking hours instead of months and you swap out the data we swap the raw internet text for a smaller highly curated data hundreds of thousands of examples of high quality dialogues is where human labelers come in they're basically defining the AIs persona humans are hired given these really strict detail instructions and they're tasked with writing the ideal assistant response for all kinds of prompts they're literally teaching the LLM to adopt that helpful truthful and harmless persona by example So when I talk to an AI I'm not talking to some new form of intelligence I'm interacting with a neural network that is simulating the average highly skilled human labeler who followed those instructions perfectly That's the simplest way to put it。

 you're talking to the most expensive， highly optimized simulation of human customer service ever built so once。

If the muddle has the right persona。 We need to teach it how to actually solve problems。

 and that moves us to the third most advanced stage， reinforcement learning or Rl。

How is this different from SFT SFT taught it what to say？RL teaches it how to think。With Rl。

 the model can practice problem solving in verifiable domains like math and code where we know for a fact what the correct final answer is。

 So you give it the problem in the answer， but it has to figure out how to get there。

 It has to discover the sequence of tokens that reliably leads to that result。

 and this is where it gets truly fascinating。 because this is where we see the model's cognitive strategies emerge。

 It learns to think by creating a kind of internal monologue。 That's right。

 because the model has finite computation per token。

 it learns it has to distribute its reasoning across multiple tokens。

 We call this chain of thought or coach a day。 if you just ask it to spit out the answer to a hard math problem in one go。

 it fails。 It will consistently fail at the mental arithmetic。 Yeah。

 you have to train it to spread out the calculation step by step。

 That's the key takeaway for the user right there。 The model needs tokens to think if you don't let it think step by step。

 you're asking it to do calculus without any scratch paper。 precisely。

 Now this pure Rl process works great when the。Answer is objectively verifiable math， code， chess。

 But what about things that are subjective like writing a joke or a persuasive essay For those domains。

 companies use an adaptation called reinforcement learning from human feedback or RLHF This is where they train a second AI a reward model to act like a human judge correct a human ranks different AI outputs and the reward model learns to replicate those rankings it becomes a proxy for human taste。

 but the sources point out a major drawback here reinforcement learning is extremely good at finding ways to game any simulation。

 The LLM can learn to generate content that just tricks the reward model into giving a high score。

 prioritizing optimization over genuine quality So RLHF is powerful。

 but it's a shortli process The model will eventually learn to exploit the reward system Exactly human oversight remains mandatory。

Okay， so once you have this highly trained model knowledge personality and some reason ability。

 the final stage is all about prompt engineering right the art of command。

 it's basically programming the model through conversation a foundational technique here is in context learning K shot prompting Yep you just give the model a few examples。

 maybe one，3 or five right inside the prompt itself So if I need it to translate sentences into Korean using a very specific honorific style you just give a one or two examples of that exact style and the model instantly adapts。

 it learns the pattern in context but for more complex logical tasks。

 we have to go back to chain of thought we have to and even a simple instruction like let's think step by step which is called zeroshot C Cot。

It dramatically improves accuracy。 You're unlocking the model's ability to reason out loud。

 but the model's knowledge is frozen in time。 right。

 It doesn't know what happened yesterday or what's in my company's private database。

 And that is why external tools are so critical for real world tasks。

Particularly retrieval augmented generation or ag。 Ag is our crucial defense against hallucinations。

 It's like giving the AI a smart Google search function。 That's a great way to frame it。

 The L M realizes it needs current information。 So it generates special tokens that invoke a tool like a web search。

 And the results of that search get fed back into the AI's working memory。

 Ined directly into its context window right before it generates the final answer。

 It forces the model to use current facts instead of just its old training memory。

 We can refine this even more with self correctionction techniques。 for sure， Take self consistency。

 Instead of asking the model a question once。 You ask it five times。

 You force it to find five different reasoning paths and then you take the majority answer。

 That cuts down on random errors。 And then there's reflection。 which is great for coding。

 It's fantastic。 You feed an error message back into the prompt and asks the model to critique and revise its own code。

😊，You're teaching it to learn from its mistakes in real time These techniques are what separate simple chatting from high leverage professional use absolutelyly。

 which brings us to the core shift happening for professionals the discussion is always about replacement。

But the material highlights a different idea。 The mantra is you won't be replaced by AI。

 You'll be replaced by a competent engineer who knows how to use AI。

 The LL M isn't replacing the engineer。 It's augmenting them。

 Turn a regular engineer into a hyper efficient one。

We see this with internal use at places like Open AI with their codex models。 Okay。

 let's take a concrete example。 code understanding。 An engineer pasts the stack trace from an error。

 Normally， that's an hour of digging。 right， Instead， they prompt the model。 Given this stack trace。

 Lo the author logic in this repo and trace the data flow。 That saves 45 minutes， just like that。

 Reffactoring is another huge one。 Up a legacy API call across dozens of files。

 That's a tedious three hour manual job。 with an LL M。

 you prompted to apply this change consistently across all 40 files。 and it takes 90 seconds。

 That's real leverage。 or performance optimization。Instead of hunting for a bottleneck for an hour。

 you have the model， analyze the code， flag the slow database calls。

 and draft to fix 30 minutes of work becomes five minutes of prompting。And finally， Q A and testing。

 you can point the model at low coverage code overnight and wake up to runnable unit tests that cover edge cases a human might have missed。

 But to get this kind of precision， you can't just type a casual request。 There are best practices。

 Yes， versus role prompting。You have to aggressively define the persona。

 You are a helpful assistant that loves programming at the level of a senior software developer and structured prompts using tags like error or log when you paste in complex data so the model can parse it efficiently。

 and the most advanced technique is persistent context。

 Engines will keep a file like agents test M D with all the business logic and naming conventions。

 The AI can't possibly know。 and they paste that context into every session。 Y。

 It keeps the model informed and dramatically improves accuracy across all your prompts。

 So we've charted this whole path today。 from trillions of raw internet tokens through human labeled conversations that give the AI its personality right up to the advanced reasoning that requires chain of thought。

 The core takeaway for you。 the learner is that Lms are powerful that they have these cognitive deficits。

 We call it the Swiss cheese model of capability。 The holes don't line up exactly。

 it can solve an Oibia level math problem， but then。😊，Failed to compare two simple numbers like 9。

1 and 9。9。 You have to treat them as stochastic tools。

 Always check their work and use these techniques to compensate for their limitations。 Okay。

 let's unpack this for one final thought， something for you to really mallll over after this deep dive。

 When L O Ms are trained with pure reinforcement learning on problems where the answer is verifiable。

 The model isn't constrained by human logic。 We saw this years ago with Alphago discovering move 37。

 this brilliant， totally unforeseen strategy。 A move， no human would have considered。 right。

 So if these thinking models continue to evolve in open domain problem solving。

 discovering new superior cognitive strategies， maybe even a new internal language for thought that's more efficient than English。

 What will it mean for us when the optimal way to solve a complex business problem is something no human could have conceived。

 That raises a really important question of the future of human AI collaboration。

