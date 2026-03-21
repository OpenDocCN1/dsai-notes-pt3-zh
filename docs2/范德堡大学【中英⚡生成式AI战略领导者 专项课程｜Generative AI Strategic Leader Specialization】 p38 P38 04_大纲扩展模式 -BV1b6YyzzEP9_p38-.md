# 范德堡大学【中英⚡生成式AI战略领导者 专项课程｜Generative AI Strategic Leader Specialization】 p38 P38 04_大纲扩展模式 -BV1b6YyzzEP9_p38-

There's a limit to how big we can go with the large language models。

 they fundamentally have a limit to the size of the input we can give them。

 so how big of a prompt we can give them or how long our conversation can be and they can still remember it。

And there's just a limitation on how much output they can generate at once Now it's inevitable that these language models are going to keep getting bigger and bigger and we're going to be able to give them more and more input and get more and more output from them。

 but more than likely everybodys going to face some limitation on how big we can go。

Now the way that we work around that is we're typically generating pieces like we generate a piece of the solution。

 then we take it， so you can imagine if you're trying to generate a book。

 you can't just tell ChatGBT at this point， go and generate a book for me， it's not going to do it。

 It's going to tell you， well， I have to stop my endpoint at some point。And similarly。

 you can't just give it 50，000 pages at this point and dump it into chatGBT and ask it to give you an answer or 100。

000 pages or a million pages。There's always going to be a limit probably on the amount of information。

 so we need a way to work with it in smaller pieces。

 but still be able to put all the pieces back together。

So one of the ways that we can do that is by building an outline of what we're trying to put together and we can build the outline out and we can build it to the level of granularity that we want and then we can start filling in the pieces once we've gotten enough detail into our outline and then we can go and generate individual pieces and we can know where they all fit together so this is an effective way of using it to generate the pieces now this is basically putting a plan together this same approach works for all kinds of things it could be software anywhere where we can go and sort of have this outline like structure and then when if we generate something that fits sort of the outline or the plan at that point。

😊，Then we can go and work with it。 Now we're going to look at a specific pattern that can help us generate the outlines and work with them。

 This is called the outline expansion pattern。And so the idea is we want to make it really easy to generate outlines and continue to expand them down to the level of granularity that we need in order to build the individual pieces。

 then be able to put them together。Now， one of the reasons that outlines are a really helpful tool when we're building bigger bodies of work with a tool like Cha and GT is that。

An outline， we can always take parts of the outline and copy and paste or reintroduce them into the prompt to give the large language model context about what we want So with chat GT for example。

 we can generate an outline and then we can copy and paste a portion of the outline into our prompt and say within this context。

 Here's where you are in the outline Now fill in the content for this and don't repeat anything that would have come before in the outline and in fact you can refer to the other parts of the outline wherever you're going to talk about a topic that was discussed previously or maybe we want to have forward references。

 where we can provide at the high-level outline and say you know wherever you are going to need to talk about a topic that's later that's going to be discussed later。

 you can provide a forward reference to where it is in the outline you can do similar types of things with software or other sort of whatever the bigger thing as that you're building Now this works well when we have a structure that's andemenable to sort of this outline。

Based plan now sometimes we have plans or structures or designs where everything crosses over and you can't easily do this。

It doesn't work to express it as an outline and express the plan and in those cases it just doesn't work。

 but many problems we can sort of build out in this sort of outline like fashion。

 and then we can use cutting and pasting from the outline to provide the appropriate context so building outlines can be a really powerful thing for us。

So， we're going look at。And build with the outline expansion pattern， so here's what we say。

We're going to say act as an outline expander and notice I'm starting to introduce multiple patterns here。

 I'm basically introducing in the persona pattern。Generate a bullet point outline based on the input that I give you and then ask me for the bullet point you should expand on so we're telling it you're going to generate the outline and then you're going to expand on anything that I ask you to expand on。

Create a new outline for the bullet point that I select at the end。

 ask me for what bullet point to expand next， so notice I'm using the tail generation pattern as well。

 and then I'm using the ask for input pattern so I'm putting a lot of things together into this prompt。

And I say， ask me for what to outline。And so what we see is it says， sure。

 I'd be happy to help you with that so I say， let's write an outline for writing effective prompts for chat GT。

And so what we see is that chat GBT generates this outline and it's an interesting outline introduction to chat GBT。

 understanding the importance of prompts， tips for writing effective prompts， yada， yada yada。

 so a lot of good things there。And then I decide， okay。

 let's go and expand on three from the outline。 So if we look back here。

 three with tips for writing effective prompts。 I thought let's go ahead and expand the outline there。

And explore this a little more。And so then it picks up from three。

 and it expands on tips for writing expected prompts and gives us a new outline。

So we built in using this pattern， we can rapidly fill in and outline。And。

Probably there are going to be tools to support us in this very soon or plugins to support us in this very soon to where we don't have to remember all the pieces they outlined。

With this I would probably just manually have a document where as it was generating the pieces I would go and look and say okay here's the three。

 I'll paste 3N and its expansion now and you can easily fit the parts together。

 This is one of the nice things about the outline approach is that it's really obvious how all the pieces fit together I know that  three。

1 goes underneath three so it's sort of self describing in terms of the assembly so if I generated a piece of an outline here I've expanded three I know exactly where that goes。

 how it fits together in the overall whole。Then I go and say well。

 you know this idea of experimenting with different prompt styles that looks interesting。

 so maybe I should go and expand that further in the outline and so I basically say 3。

2 and now it goes and expands the outline around 3。

2 so you see how we've got a simple pattern and we now can go in rapidly create an outline and keep expanding it to the level of detail and because of it's using this outline structure it's really easy to fit all of the individual pieces back together。

😊，And as long as we have limitations on how much input， how big of a prompt we can give。

 and how much output we can get at once。We're always going to be looking for ways to generate things and pieces and know how they fit together。

 so we want the pieces to be really obvious on how to assemble them and we always want to make sure that we have a clear structure or sort of guidelines for each individual piece so that we can assemble them so you can imagine if this part of the outline depends on knowledge of what was covered in a different part of the outline。

Then we would need to make sure that that was introduced into the prompt。So we just said 3。2。

 but if we had an idea that maybe the conversation had gotten so long that what was in item one had been forgotten。

We might want to go and just cut and paste the outline underneath one back into the prompt and then say expand 3。

2 because we know 3。2 was just previously generated。

 but that would help give it the knowledge of what had come before and make sure that what it put into32 was consistent with what had been done earlier in the overall structure Similarlyly if it need to make sure that 3。

2 was cohesive what's what's going to come later， we would want to put in those pieces。

 So one of the things we have to think about is even if this outline style when we do this。

 it will work but we always have to think about， you know does it still have the context to make sure the individual pieces are cohesive。

 even if they fit into the outline at this point， we want to make sure it doesn't do something that you know breaks something somewhere else。

 And this is a problem a fundamental challenge that we're always working with in prompt engineering when we're building from pieces。

 how do we be able build the pieces so that they're standalone self-contained。

 but can be assembled into the overall whole。And so we see this again， we just expand 3。

5 which was setting the tone in style， and we get this very rapid expansion and creation of a sophisticated outline now that we can use to write text for a bigger project to be able to try to write software there's all kinds of sort of analogies or analogs to the outline the sort of the master structure where we start with a certain level of detail then we pick some piece of it and we expand the level of detail and then we may pick a piece of that and we may expand the detail and then we may move back up to another bullet point in the outline and expand the level of detail and so we can be moving up and down in the outline。

 we can be going up to the top level where we can be going down to the really detailed things and we can expand wherever we want。

😊，And sort of keep a map of the overall picture that we can use to build individual pieces and make sure that we can assemble them。

 but also as we build pieces that we can make sure that chatGPT has the relevant information this sections of the outline。

 for example， that in the prompt that it needs in order to reason about or generate whatever it's going to produce next。

