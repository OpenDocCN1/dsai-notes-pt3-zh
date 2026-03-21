# 范德堡大学【中英⚡生成式AI战略领导者 专项课程｜Generative AI Strategic Leader Specialization】 p27 P27 04_撰写有效的少样本示例 -BV1b6YyzzEP9_p27-

Let's look at some examples of where we're making mistakes in our few shot examples of things that we can do wrong in the formatting of our prompts and what we can kind of think about and learn from these examples。

Here's some few shot examples。 And the idea behind this is we put together not very good prompt to analyze how hard things are。

 like， is it soft or hard， That's really what we're trying to get at with this prompt and some few shot examples。

 Now this is a good prompt。 This is a bad prompt and we'll see why。

So what we've got is we have input is the prefix， we then got brick， we've got output as a prefix。

 and then hard。We've got input as a prefix and then pillow， output， soft。

 and then we've got input car。Now notice what we've got here。

 one we don't have a lot of examples here。But2， we kind of we've kind of switched gears。 like。

 you know， we started talking about input and output and the hardness of things。

 using things that are really obvious， probably the like a brick as hard。 A pillow as soft。 Is a car。

 I guess a car as hard。 But it's not as clear what we're getting at。

 We also might just be trying to describe some fundamental sort of intrinsic capability or you know。

 properties of this thing。 It may not be about hard or soft， because it could be other things。

 It could just be an attribute to describe the thing itself。

 because pillows are generally thought of as soft and bricks are normally thought of as hard。

 Those are kind of fundamental descriptors sometimes that you use for them。😊。

And what we see is that when we prompt chatGBT in this example。

 what we get is it says fast or maybe transportation， and so this kind of shows us a couple things。

 this is a prompt that's not very well designed and because of that。

 what we see is that chatGBT isn't quite sure what the next output should be from the pattern。Now。

 there's a couple mistakes in here。 One is we've got input and output。

 input and output are really generic prefixes。 They don't really give the language model much information about what the task is that it's trying to do。

 All we know is we're taking in something that we're getting out something。

 but it's not really telling us you know， what it is that we're describing like maybe we should go and say。

 you know， input， brick， surface feeling， you know， hard input， pillow， you know， surface feeling。

 you know， soft or maybe it's something about like if you hit it， what will it feel like。

 you know there's all kinds of things we could do to give it more sort of context。

 around what we're trying to get at。We could also give it more examples。

 but what we've got here overall in this prompt is we've got a lack of information。

 it's not detailed enough and we're not giving enough information about what the task is that's being solved and the result of that is is that the language model isn't really sure what the solution is。

Now， one way we could solve this。As we can go and before we give our examples。

 we could give a little bit more context so we can provide some instructions so we could say your output can only be soft or hard。

 Now， one thing to notice is I'm putting these things in quotation marks to try to indicate to the language model that these are the two values。

 I don't want it to get confused and think I'm talking about soft or hard and some other context。

 but I'm putting these things in quotation marks trying to giving them some emphasis that either it's soft or hard。

 and this may not always work because we still have a prompt that's really generic that's really doesn't have a lot of context and a lot of meat to it。

 It's still very you vague。 we've got input brick， we're still dealing with it。

 Now luckily in this case。Adding this little bit of additional context and specifying to the large language model that we only want Soft hard as an output helps it figure out that it should think about if I pushed on this car。

 how would it feel like it would feel hard know and that's kind of the task that's being solved and so it comes back with the right thing。

 but that's a first thing to think about when you're writing few shot examples。

Are your examples detailed enough， Are your prefixes that you're using for these things meaningful？

 Do they give additional context that the large language model can use to figure out what the next thing in the sequence is。

 Another way to think about it is if you gave this to 10 different human beings。

 would you have a chance， So a few of them might be confused about what you're trying to ask for it。

 And if the answer is yes， then you probably need to think about how to refine your prompt。 Like。

 if it's not fully clear what you're trying to do in the examples of what the process behind the examples is illustrating。

 then you' probably not detailed enough。 Now， one way you can solve that is by adding some more instruction like we have here at the top of this prompt。

Now let's look at another example。I've got object plane speed fast， object worm， speed slow。

 and then I go through a series of examples and notice I'm giving a little bit more context here。

 you know， my speed prefix is a little better right because speed seems something that's quantifiable right。

 like a plane is fast you know， a worm is slow， like that should be more context。

 and so we then go prompted with object ball speed and this is another important thing to realize is it says variable。

😊，And so one of the things we have to think about is we're trying to get the large language model to produce an output or to classify or to fit into some boxes。

 We need to make sure that it gets enough information in the input to be able to accurately put things into the boxes so we need to make sure that whatever information we're giving it about what it's going to do always has you know enough context that it can make a decision about the label Now in this case。

 a ball could be fast， it could be slow， if I shoot a ball out of a cannon。

 it might be going really fast， you know if I shoot a ball， if I put it on the top of a rocket。

 it might be going really fast， you know there's all kinds of different things that could make a ball go faster or slower so。

We have to make sure that we provide enough context now in general。

 the thing to think about is am I giving enough information now I'm going to go back and I'm going to change my prop down。

 I'm going to say object ball kicked by a baby and then we get immediately it says slow。

So when you're building up the few shot examples， you want to make sure one。

 your prefixors are pretty descriptive。Two， do the examples that you're giving really give enough information to derive what the underlying process is that is going on in order to go from you know the starting input to the final output。

 can you really do you really have enough information there to see what's underneath the hood and one way to think about that is if you asked a bunch of humans would they all know exactly what you wanted it to do without any ambiguity。

2， you want to make sure that you have enough description before the examples。

 if needed to provide additional context。 Sometimes examples you're just not going to be able to get there with examples and you may need to provide some additional rules or other information at the start of your prompt to help it along And so really a lot of times what you're thinking about is you have a limited amount of space in your prompt and you have to think about is this something that I can better describe and an example or is it something that I can better describe in know some instructions at the top and what better means is。

 will I get a more accurate output and will it take less space or maybe less words to describe it if I can get it done very clearly in an example then maybe that's the right way to go that example doesn't take a lot of space On the other hand。

 if it's a really simple rule and I can describe it。

 I may be able to get a better response by putting that rule up into the description。

And then finally， we have to make sure that we provide enough information。 So in this example。

 ball kicked by baby， if we're trying to bucket things or we're trying to get a particular output。

 we may have to make sure that when we give input， that there's sufficient richness and detail in that input to follow the rules or prior examples that we've given。

 Now， this is particularly important if our prior examples were pretty clear cut。

 it's probably something better。 Now， one could argue that you know， our prior examples。

 if we go back and look at this， our we said plain playing was fast well。You know。

 a plane might not be fast right， a plane might be slow。

 It might be sitting parked on the tarmac of an airport and so we also want to make sure that our examples are rich enough and detailed enough Now sometimes we can get away with simple things like playing fast worm slow in order to teach it but sometimes we're gonna have to go into more detail。

 we're gonna to provide more context so make sure and think about do you have enough real information is there is it going to depend on the situation those things like that provide details now one way to do it would be to say just make some assumptions you know but one of the things that can happen sometimes when you do that is you may get more verbose output than you really want。

 it may not fit into that bucket but when you're writing these prompts think meaningfully about like what is a meaningful prefix what information or instruction so I need to have at the top and can you know important information be better convey as an instruction。

At the top or as an example。Do my examples cover the space enough。

 do I have enough good examples with rich detail for it to learn from and derive what the underlying process is。

 and then when I go and I give it the new input， do I make sure I have enough relevant context and information with the new input in order to apply the process that I taught it because we may teach it the process really well。

 but then give it a new input that just fundamentally is missing information in order to apply that process。

