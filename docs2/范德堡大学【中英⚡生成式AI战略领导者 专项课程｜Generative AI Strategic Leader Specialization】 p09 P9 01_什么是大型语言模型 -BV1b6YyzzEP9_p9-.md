# 范德堡大学【中英⚡生成式AI战略领导者 专项课程｜Generative AI Strategic Leader Specialization】 p09 P9 01_什么是大型语言模型 -BV1b6YyzzEP9_p9-

![](img/036178dcdb11f2a03961ffe0ea1a484b_0.png)

So what are large language models exactly and what do they do， How do they work Now。

 I'm not going to go into the full details of this， but I want to give you just enough。



![](img/036178dcdb11f2a03961ffe0ea1a484b_2.png)

![](img/036178dcdb11f2a03961ffe0ea1a484b_3.png)

About how they work that will help you in thinking through designing prompts。

 So there's a couple things to know about them that will be useful when you're designing prompts now。



![](img/036178dcdb11f2a03961ffe0ea1a484b_5.png)

![](img/036178dcdb11f2a03961ffe0ea1a484b_6.png)

The fundamental thing that you want to know about these large language models is basically what they're doing is they're taking your input and they're trying to generate the next word and then they'll take that word that they generate。

 and they'll add it to you what you originally gave it and they'll try to generate the next word。

 This is a way to think of it。 Now there's a lot more detail than this。

 but think of it basically is it's trying to generate word by word， the response to your input。

 whatever your prompt is， there's going to try to generate word by word。

 the next word that's going to be in the output until it gets to a point that it thinks it's generated enough and then the last word is basically going to be the equivalent of stop。

 but it's going to be it's not going to be something you're going to see。



![](img/036178dcdb11f2a03961ffe0ea1a484b_8.png)

![](img/036178dcdb11f2a03961ffe0ea1a484b_9.png)

![](img/036178dcdb11f2a03961ffe0ea1a484b_10.png)

![](img/036178dcdb11f2a03961ffe0ea1a484b_11.png)

![](img/036178dcdb11f2a03961ffe0ea1a484b_12.png)

![](img/036178dcdb11f2a03961ffe0ea1a484b_13.png)

![](img/036178dcdb11f2a03961ffe0ea1a484b_14.png)

![](img/036178dcdb11f2a03961ffe0ea1a484b_15.png)

So what it's doing is basically producing words or tokens， basically to respond to your prompt。



![](img/036178dcdb11f2a03961ffe0ea1a484b_17.png)

![](img/036178dcdb11f2a03961ffe0ea1a484b_18.png)

And so what we're trying to do with large language models is we're trying to produce prompts that then cause it word by word to produce an output。

 now I want to show you a little bit about this and kind of give you some intuition of it。

 So if I go and I write， Mary had a little and we stop right there and if you're familiar with the nursery rhyme。

 Mary had a little lamb， it fleece was white as snow， I'm giving it a prompt。

 and if I say Mary had a little， it's going and then completing it。

 it it starts from my last statement， Mary had a little and it's giving predicting the next word which is lamb it's fleece was white as snow and everywhere that Mary went the lamb was sure to go it followed her to school one day which was against the rule。

 It made the children laugh and play to see a lamb at school and so the teacher turned it out。

 but still it lingered near and it goes on and on。

![](img/036178dcdb11f2a03961ffe0ea1a484b_20.png)

![](img/036178dcdb11f2a03961ffe0ea1a484b_21.png)

![](img/036178dcdb11f2a03961ffe0ea1a484b_22.png)

![](img/036178dcdb11f2a03961ffe0ea1a484b_23.png)

![](img/036178dcdb11f2a03961ffe0ea1a484b_24.png)

![](img/036178dcdb11f2a03961ffe0ea1a484b_25.png)

![](img/036178dcdb11f2a03961ffe0ea1a484b_26.png)

Until it stops。Now， you notice what it's doing is it's my prompt。

Triggered it to produce the next word， which was Mary had a little was my prompt。

 so the next word was lambmb。If I go and I say roses are red。What does chatt G do。

 It says violets are blue， sugar is sweet， and so are you。

 And it says this is a classic point that' is often used to express affection or admiration for someone。

 But the key thing to note is it's doing a next word prediction。

 I said roses are red and it's picking up where I stopped and predicting the next word。

 which is violets。😊，It's then adding that in and it's saying roses are red violets and it's predicting R。

 it's then going back， adding that in and it says roses are red violets R and it's predicting blue。

 and it's doing this over and over。And so。It does really sophisticated sort of incredible things。

 but underneath the hood， when it was trained and created。

 basically what was done was a large portion of the text and other things on the internet were taken。

And it was taught basically over and over again。 it was given a series of words and it tried to predict the next word。

 except that it was given you know a paragraph of text from the internet。

 and they would show it part of the text， you know part of the sentence。

 and they would ask it to try to predict the next word in the sentence and when it got it wrong。

 they would go and tweak the models is what they call these things。

 large language models and their large because they were trained on so much data and they have so many different parameters to them。

There are these large language models。And what they're doing is they're basically。

 they've learned patterns from our language， our human language that was out there on the internet。

 and they've basically learned the idea of given what came before in the text。

Try to predict the next word。And then if I take that word and I add it back in。

 try to predict the next word。 And so they trained these models to get really good at looking at the context of the information。

 Now， if you think about it， you know， it has a lot of context。

 It's tapping into a pattern that it's seen。 I said Mary had a little and it says lamb。 you know。

 it could have been Mary had a little bit of peanut butter on her shirt， you know。

 but it's learned context， right， and that's part of what makes it work。 it could be roses are red。

 you know， daffodils are yellow， but it's learned this context， right，😊。

And so that's a part of the piece of this is it pays attention to words。

And uses that knowledge of the context， it's paying attention to different words that have come before that are in the current sentence。

 it's paying attention to their relationships， and it's using that knowledge。

 that contextual knowledge to try to predict the next word。

 and then it's taking the word that it produced， putting it back into the output and trying to produce the next word。

 the next word。And this is the basis of things。 Now。

 this will be helpful to know when we start thinking about the patterns of our prompts。

 when we think about conversations， when we think about what we can do to tap into this。

 this fundamental concept of predicting the next word now。

One of the things to know with these models is they are rapidly rapidly evolving。

 We're seeing a lot in the news about chatt GT， but there's lots of competing models that are coming out。

 and probably by the time you're watching this video。

 there'll be even more that I'm not going to mention or talk about because they they didn't exist today when I started talking about it。

 So chat GT is certainly out there， there's a new version。 G4， They're models like know Lama。

 there are variations on Lama like alpaca， there's all kinds of different models that are coming out。

 and they're rapid rapidly evolving。 So more than likely the discipline of prompt engineering and what you're learning。

 some parts of this are going to be hopefully timeless。

 but some parts of it will probably evolve and adapt。😊。

As the different capabilities of these models evolve， now。

 one of the things you'll want to do is always have that openness to experimentation。

 to creativity and doing trying things out。 Remember， with these tools， we can rapidly prototype。

 we can rapidly explore things and try things out。 And so we want to always tap into that now。😊。

One thing to note is that a lot of times these tools reproduce output that is not the same every time now it's possible that we could get the same output every time in certain cases like roses or red。

And now we get something different。And then if we went in and we did it again。

We get something different Now notice that initially we got something that was what we kind of expected。

 but each time we're getting some variation on this。

And this is something else that's useful to know is these models aren't designed to do exactly the same thing every time。

There is inherent randomness or variation in what they produce。

 and so this is something you need to know about when you're using the models。

It's really powerful and useful if you use them the right way。

 if you aren't using the models the right way or you're trying to fit them in for a task that they're not good for。

 you're going to have to do a lot of work to deal with this fundamental aspect of it。

But it's also an asset that makes you want to think about this as。You know。

 you should never expect these outputs to be perfect necessarily on the first try。 You know。

 it's a tool that can help you get an output that you want。

 but it's not necessarily perfect on the first try。 There may be errors。

 There may be variation and you need to build that into the processes and the other things that you build around the tool。

 So if you're going to use it in your business， know that it may not give you exactly the same output every time。

 Now， there's ways to try to help limit what it does and try to guarantee that。

 but it's not guaranteed to do that。 And so you want to know that you want to know there's some randomness。

 There's some variation， which can be great when we're writing you know， pros with this。

 because we don't get exactly the same text every time。 or else we would all have you know。

 exactly the same outputs。 and we wouldn't be able to explore and try things。

 So knowing that isn't helpful you know thing to realize。

 Now it' changed on a vast amount of data that came from the Internet， knowing that。

Its knowledge is based on the time that training data was collected， so in the case of Chat and GPT。

 it's cut off around 21-21， newer ones have more up to dateate knowledge base。

 but they're always going to be behind in what they were trained on。

 so they were taught to predict the next word and they learned from that idea predicting the next word。

And they learn to predict the next word in the context of a lot of different domains。

 be it speech language pathology or programming， or be it about creating recipes， whatever it is。

 but their knowledge that they were trained on and the patterns that they learned cut off at some date and so when we want to introduce and reason or work with new knowledge we're always going to have to provide that as part of our prompt。

 as part of our input into the conversation is that。😊。

Whatever additional information they need in order to reason。

 they're not necessarily continually updating they can't retrain these things necessarily you know all the time now it may change at some point the technologies may change。

 but right now today know that when you need new additional information that wasn't publicly available on the internet you're probably going to need to provide it in the prompt Now those are some of the key things that you'll need to know as we go forward in this course in order to help you write more effective prompts。

