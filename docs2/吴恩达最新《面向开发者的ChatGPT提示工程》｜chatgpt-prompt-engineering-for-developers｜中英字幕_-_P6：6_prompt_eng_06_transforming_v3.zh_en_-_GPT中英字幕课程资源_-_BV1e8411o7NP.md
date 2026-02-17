# 吴恩达最新《面向开发者的ChatGPT提示工程》｜chatgpt-prompt-engineering-for-developers｜中英字幕 - P6：6_prompt_eng_06_transforming_v3.zh_en - GPT中英字幕课程资源 - BV1e8411o7NP

![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_0.png)

Large language models are very good at transforming its input to a different format。

 such as inputting a piece of text in one language and transforming it or translating it to a different language or helping with spelling and grammar correction。

 So taking us input a piece of text that may not be fully grammatical and helping you to fix that up a bit or even transforming formats such as inputting HTML and outputting Jason。

 So there's a bunch of applications that I used to write somewhat painfully with a bunch of regular expressions that would definitely be much more simply implementing now with a large language model in a few prompts。

Yeah， I use Chad GT to proofread pretty much everything I write these days。

 so I'm excited to show you some more examples in the notebook now。😊。



![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_2.png)

So first， we'll import open AI and also。Use the same get completion helper function that we've been using throughout the videos。

 And the first thing we'll do is a translation task。

 So large language models are trained on a lot of text from kind of many sources。

 a lot of which is the internet。 and this is kind of， of course， in many different languages。

 So this kind of imbued the model with the ability to do translation。

 and these models know kind of hundreds of languages to varying degrees of proficiency。

And so we'll go through some examples of how to use this capability。So。

 let's start off with something simple。So in this first example。

 the prompt is translate the following English text to Spanish。Hi， I would like to order a blender。

And the response is ola， Migutaia， or dinner， unna liquid。Kuadorra。

 and I'm very sorry to all of you Spanish speakers。 I never learn Spanish， unfortunately。

 as you can definitely tell。Okay， let's try another example。😊。



![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_4.png)

So。In this example， the prompt is， tell me what language this is。And then this is in French。

 Comb Cule Laererre。And so let's run this。😊。

![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_6.png)

And the model has identified that this is French。The model can also do multiple translations at once。



![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_8.png)

So in this example， let's say translate the following text to French and Spanish。And you know what。

 let's add another and English。Pirate。And the text is， I want to order a basketball。



![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_10.png)

So here we have French， Spanish。An English pirate。

![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_12.png)

So in some languages， the translation can change depending on the speaker's relationship to the listener and you can also explain this to the language model and so it will be able to kind of translate accordingly So in this example we say translate the following text to Spanish in both the formal and informal forms would you like to order a pillow and also notice here we're using a different delimiter than these baics it doesn't really matter as long as it's kind of a clear separation。

So here we have the formal and informal。So formal is when you're speaking to someone who's maybe senior to you or you're in a professional situation。

 That's when you use a formal tone。 and then informal is when you're speaking to maybe a group of friends。

 I don't actually speak Spanish， but my dad does。 and he says that this is correct。

So for the next example。We're going to pretend that we're in charge of a multinational ecommerce-commerce company。

 And so the user messages are going to be in all different languages。

 And so users are going to be telling us about their I T issues in a wide variety of languages。

So we need a universal translator。So first， we'll just paste in a list of user messages in a variety of different languages。

And now， we will loop through。Each of these user messages。 So for issue in user messages。

And then I'm going to copy over this slightly longer code block。

And so the first thing we'll do is ask the model to tell us what language the issue is in。

 so here's the prompt， then we'll print out the original messages language and the issue。

 and then we'll ask the model to translate it into English and Korean。So that's from this。



![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_14.png)

So the original message in French。

![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_16.png)

So we have a variety of languages and then the model translates them into English and then Korean。😊。



![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_18.png)

And you can kind of see here。 So the model says this is French。

 So that's because the response from this prompt is going to be this is French。

 You could try editing this prompt to say something like， tell me what language this is。

 Respon with only one。

![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_20.png)

![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_21.png)

With only one word or don't use a sentence， that kind of thing if you wanted this to just speak one word。

 or you could ask for it in a JSO format or something like that。

 which would probably encourage it to not use a whole sentence。



![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_23.png)

![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_24.png)

And so amazing， you've just built a universal translator and also feel free to pause the video and add kind of any other languages you want to try here。

 maybe languages you speak yourself and see how the model does。😊。



![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_26.png)

![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_27.png)

![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_28.png)

So the next thing we're going to dive into is tone transformation writing can vary based on an intended audience。

 you know the way that I would write an email to a colleague or a professor is obviously going to be quite different to the way I text my younger brother and so ChaTBT can actually also help produce different tones。

So let's look at some examples。 So in this first example。

The prompt is translate the following from slang to a business letter， Du， this is Joe。

 check out this spec on the standing lamp。So。Let's execute this。And as you can see。

 we have a much more formal business letter。With a proposal for a standing lamp specification。

The next thing that we're going to do is to convert between different formats。

 chart GBT is very good at translating between different formats such as JSON to HTML， you know XM。

 all kinds of things， markdown。And so in the prompt we'll describe both the input and the output formats。

 so here is an example， so we have this JO that contains a list of restaurant employees with their name and email。

And then in the prompt， we're going to ask the model to translate this from JSON to HTML。

 so the prompt is translate the following Python dictionary from JSON to an HTML table with column headers and titles。

And。Then will。Get the response。From the model and print it。

So here we have some HTML displaying all of the employee names and emails。

And so now let's see if we can actually view this H T M L。So。

We're going to use this display function from this Python library， display HTML response。

And here you can see that this is a properly formatted HTML table。

The next transformation task we're going to do is spell check and grammar tracking and this is a really kind of popular use for chat GBT。

 I highly recommend doing this， I do this all the time and it' is especially useful when you're working in a non-native language and so here are some examples of some common grammar and spelling problems and how the language model can help address these。

So I'm going to paste in a list of sentences that have some grammatical or spelling errors。

And then we're going to loop through each of these sentences。And。Ask the model to proofread this。

Proof free and correct。And then we'll use delimiters。

And then we will get the response and print it as usual。



![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_30.png)

And so the model is able to correct all of these grammatical errors。

 we could use some of the techniques that we've discussed before， so。



![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_32.png)

![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_33.png)

We could to improve the prompt。 we could say proofread correct the following text。



![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_35.png)

And rewrite。And rewrite the whole。And rewrite it。Corrected。Vashion， if you。Don't find。Any errors。

Just say。No errors found。Let's try this。So this way， we were able to。 oh。

 they're still using quotes here。

![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_37.png)

But you can imagine you'd be able to find a way with a little bit of iterative prompt development to kind of find a prompt that works more reliably every single time。



![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_39.png)

AndSo now we'll do another example， it's always useful to check your text before you post it in a public forum and so we'll go through an example of checking a review。

😊，And so here is a review about a stuffed panda， and so we're going to ask the model to proofread and correct the review。

😊，Great， so we have this corrected version。 and one cool thing we can do is find the kind of differences between our original review and the models output。

 So we're going to use this red lines Python package to do this。

 And we're going to get the diff between the original。😊。



![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_41.png)

![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_42.png)

![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_43.png)

![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_44.png)

Text of our review and the model output， and then display this。



![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_46.png)

And so here you can see the diff between the original review and the model output and the kind of things that have been corrected。

 So the prompt that we use was proofread and correct this review。

 But you can also make kind of more dramatic changes， changes to tone and that kind of thing。

 So let's try。

![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_48.png)

![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_49.png)

![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_50.png)

One more thing。 So in this prompt we're going to ask the model to proofread and correct this same review but also make it more compelling and ensure that it follows APA style and targets and advanced reader and we're also going to ask for the output in markdown format and so we're using the same text from the original review up here。



![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_52.png)

So let's execute this。

![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_54.png)

And here we have a expanded APA style review of the soft panda。



![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_56.png)

![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_57.png)

So this is it for the transforming video next up we have expanding where we'll take a shorter prompt and kind of generate a longer more free form response from a language model。

😊。

![](img/6792a7b5e0d0cf628d9bb69dcb94b26e_59.png)