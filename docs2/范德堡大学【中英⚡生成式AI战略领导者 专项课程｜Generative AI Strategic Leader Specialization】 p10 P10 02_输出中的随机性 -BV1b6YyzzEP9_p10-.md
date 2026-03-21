# 范德堡大学【中英⚡生成式AI战略领导者 专项课程｜Generative AI Strategic Leader Specialization】 p10 P10 02_输出中的随机性 -BV1b6YyzzEP9_p10-

Large language models are unlikely， at least in the near term。

 to give you an exact and repeatable answer every single time。

 There's always going to be the possibility they do something a little bit unexpected。

 and this is by design and can be a really good thing Now a lot of what we're going to be doing in prompt engineering is trying to deal with the fact that large language of models have some unpredictability to them。

 and we want to sort of constrain that unpredictability。

 we want to mold it and shape it and work with it in a way that that's helpful to us。

 Now when I mean by this is that there's always some randomness。

 you know ability to generate new and different ideas each time you put a prompt in and this can be really good sometimes like if we're writing fiction and we want a lot of different ideas。

 a lot of different storylines， a lot of different characters and each time we ask for new data or ask for a new output。

 we get something completely new and unique then it's really good。😊，On the other hand。

 if we're trying to have the large language model do some type of reasoning on a system。

 we may not want it to have a lot of variation。And what it gives us out。 For example。

 if we want a yes or a no answer， we don't want it to say yes， sometimes no， sometimes。

 and then suddenly decide to say， well， maybe not， because here are these other things that I'd like to tell you about why it's hard to determine and goes on on this tirade for a paragraph or two about why it can't exactly given the an give us the exact answer。

 Sometimes we just want a yes or a no without any explanation。And we can't always get that easily。

 so a lot of the prompt engineering techniques are going to be dealing with this。

Now I'm going to just show you a quick sample of the randomness。

 the fact that the same input is not necessarily going to give us exactly the same output every time。

 and I want you to remember this when we go through this course because I'm going to show you a lot of different techniques to try to get the large language model to do certain things and sometimes they're going to work really well and sometimes they won't work。

 but what these techniques will typically give you is they will give you something that's more reliable that works most of the time or a lot of the time but isn't guaranteed to work every single time Now this is an important point。

😊，We're always going to have some randomness here。 We're always going to have some unknown。

 And we have to accept that and deal with that。 So I asked Cha GT。 I said。

 how many birds are outside my house。 And it says as an AI language model。

 I don't have the capability to perceive the physical world and it goes on， And then it says。

 if you're interested in finding out how many birds are outside of your house。

 You can go outside and observe the area yourself。 You might also consider set up a bird feeder。

 Okay， well， that was an interesting。 when， let's see if we ask it again what it says。😊。

So now we're going to go and get a different answer out of it and says well。

 I can't see what's going outside your house。 I don't have access to cameras。

 I only do text processing。And then it says， you know。

 you could go outside and observe the area yourself where you could set up a camera or monitoring device to record。

 get the number of birds， you know availability of ch， shelter and presence。

 and so now we've gotten something different and you know what we don't have anymore is this advice to set up a bird feeder。

If we went and ran this again， we're probably also going to get yet another example。

 it's probably going to have some similar characteristics， it's still going and saying， hey。

 I don't have the ability to do that， it's running some of its things that you know it's sort of standard text that it tells you。



![](img/77a52de8e235f6e63ff3e79e4e59cb3e_1.png)

But then it's saying， hey， if you're interested in how you could try observing the area or to capture images of the area。

 you can then count the number of vers you see。 Additionally。

 you could consider setting up bird feeders or bird baths。

 so we're getting a similar output each time， but it's not exactly the same output。

And so this is a fairly constrained set of outputs for this question， you know。

 we're still getting some similar types of things each time。

 but we're not getting exactly the same thing。And that's always going to be an issue for us。

 So know that when you're developing prompts， a lot of what you're dealing with is the fact that there is variation。

 Now， if I wanted it to give me an exact number。And I was using a prompt like this。

 this is obviously not going to work like we're not going to get an exact number of birds outside of my house with this prompt now we might need to be able to go back and give it additional information that could help it decide。

