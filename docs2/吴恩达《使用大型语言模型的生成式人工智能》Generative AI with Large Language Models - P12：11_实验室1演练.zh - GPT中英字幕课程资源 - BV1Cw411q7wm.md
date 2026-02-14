# 吴恩达《使用大型语言模型的生成式人工智能》Generative AI with Large Language Models - P12：11_实验室1演练.zh - GPT中英字幕课程资源 - BV1Cw411q7wm

So this is lab one。And like I said， we are going to grab a data set of these conversations that are happening between people what we plan to do is to summarize these dialogues and so think of a support dialogue between you and your customers maybe the end of the month you want to summarize all of the issues that your customer support team has dealt with that month some other things to note now I'm zoomed in a little bit much here but you could see that we have eight CPUs we have 32 gigs of RAM we're using Python3。



![](img/e7932f5ef0eac2c4ad991634ab7c4295_1.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_2.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_3.png)

And these are some of the Pip installs。 So if I do a shift enter here。



![](img/e7932f5ef0eac2c4ad991634ab7c4295_5.png)

This is going to start doing。

![](img/e7932f5ef0eac2c4ad991634ab7c4295_7.png)

The Python library installs and we see that we're going to be using Pytorch we are installing a library called Torch data which helps with the data loading and some other aspects for Pytorch specific to data sets and so here we see transformers this is a library from huggingface a really cool company who has built a whole lot of open source tooling for large language models they also have built this library。

 this Python library called data sets that can load in many of the common public data sets that people use to either train models finet models or just experiment with and so if you click shift enter there。

 this will run for a bit now keep in mind this does take a few minutes to load this whole notebook will depend on these libraries so make sure that these do install just ignore these errors these weren。



![](img/e7932f5ef0eac2c4ad991634ab7c4295_9.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_10.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_11.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_12.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_13.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_14.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_15.png)

We always try to do things to mitigate these errors and warnings they always show up things will still work so just trust me these libraries and these notebooks do run we've pinned all of the Python library versions so that as new versions come out it will not potentially break these notebooks so just keep that in mind this does say to restart the kernel I don't think you have to do that let's just keep on going so now we're going to actually do the like imports here so this is going to import functions called load data set this is going to import some of the models and tokens that are needed to accomplish our lab here。



![](img/e7932f5ef0eac2c4ad991634ab7c4295_17.png)

We're going to use this data set called dialogueo sum and this is a public dataset set that transformers and specifically the datas library does expose and does give us access to so all we do is call load dataset that was imported up above and we pull in this dataset now from here on out we're going to explore some of the data we're going to actually try to summarize with just the flan T5 base model okay so before we get there though let me load the data。



![](img/e7932f5ef0eac2c4ad991634ab7c4295_19.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_20.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_21.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_22.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_23.png)

Let's take a look at some of the examples at this data set。

 so here's a sample dialogue between person one and person2。So person one says what time is it Tom。

 So it looks like person two's name is Tom actually just a minute。

 it's 10 to 9 by my watch and on and on。 And so here's the baseline human summary。

 This is what a human has labeled。This conversation to be a summary of that conversation。



![](img/e7932f5ef0eac2c4ad991634ab7c4295_25.png)

And now we will try to improve upon that summary by using our model right so again no model has even been loaded yet。

 this is purely just the actual data so here's the conversation and then you know think of this like this is the training sample and then this is what a human has labeled it and then we will compare the human summary which is what we're considering to be the baseline we will compare that to what the model predicts is the summary right the model will actually generate a summary。



![](img/e7932f5ef0eac2c4ad991634ab7c4295_27.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_28.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_29.png)

Here's a second example you could see it's got some familiar terms here that like a lot of us are familiar with CDdRM painting program for your software Now here's where we're actually going to load the model so fllan T5 we spoke about in the videos this is a very nice general purpose model that can do a whole lot of tasks and today will be focused on F T5's ability to summarize conversations after loading the model we have to load the tokenizer now these are all coming from the Hugingface transformformers library and so just to give you an example before transformers came along we had to write a lot of this code ourselves and depending on the type of model there's now many。

 many different language models and some of them do things very differently than some of the other models and so there was a lot of sort of bespoke like ad hoc libraries out there that were're all trying to do similar things and then Hugingface came along and really has a very well optimize。



![](img/e7932f5ef0eac2c4ad991634ab7c4295_31.png)

Like implementation of all of these Now here's the tokenizer。

 This is what's going to be used to convert the raw text from our conversation into our vector space that can then be processed by our flt5 model And so just give you an idea let's just take a sample sentence here what time is it Tom the first sentence from our conversation up above we see the encoded sentence is actually these numbers here and then if you go to decode it。

 we see that this decos right back to the original So the tokenizer's job is to convert raw text into numbers those numbers point to a set of vectors or the embeddings as they're often called that are then used in mathematical operations like our deep learning back propagation our linear algebra。

 all that fun stuff Allright now let's run this cell here and continue to explore okay now。



![](img/e7932f5ef0eac2c4ad991634ab7c4295_33.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_34.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_35.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_36.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_37.png)

We've loaded our model and we've loaded our tokenizer。

 we can run through some of these conversations through the F T5 model and see what does this model actually generate as a summary for these conversations？



![](img/e7932f5ef0eac2c4ad991634ab7c4295_39.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_40.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_41.png)

And so here again we have the conversation here again is the baseline summary and then we see without any prompt engineering at all just taking the actual conversation passing it to our fllan T5 model it doesn't do a very good job summarizing we see it's 10 to9 that's not very helpful there's some more details in this conversation that are not coming out at this point same with the conversation about our CDRM baseline summary as person one teaches person2 how to upgrade the software and hardware in person2 system the model generated person one is thinking about upgrading their computer So again lots of details in this original conversation that do not come through the summary so let's see how we can improve on this In the lesson you learned how to use instructions to tell your model what you're trying to do with the data that you're passing it and so here's an example and this is called in context learning and specifically。



![](img/e7932f5ef0eac2c4ad991634ab7c4295_43.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_44.png)

zeroro shot inference with an instruction And so here's the instruction which is summarized the following conversation。

 Here is the actual conversation。 and then we are telling the model where it should print the summary。

 which is going to be after this word summary Okay now this seems very。

 very simple and let's see how it does。 let's see if things do get better。 So not much better here。

 Okay， so the baseline is still person one is in a hurry。 Tom tells person2 there's plenty of time。

 and then the zero shot in context learning with a prompt。 it just says the train is about to leave。

 So again， not the greatest and then here is the zero shot for the computer sample it's still thinking that person one is trying to upgrade So not much better。

 So let's keep going here。 there is a different prompt that we can use here。

 which is where we just say dialogue colon Okay now these are really up to you。

 This is the prompt engineering。

![](img/e7932f5ef0eac2c4ad991634ab7c4295_46.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_47.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_48.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_49.png)

side of these large language models where we're trying to find the best prompt。 and in this case。

 just zero shot inference。 So no fine tuning of the model， no nothing。

 All we're doing is just finding different instructions to pass and seeing if the model does any better with slightly different phrases So let's see how this does So really this is sort of the inverse of before where here we're just saying here's the dialogue and then afterward we're saying what was going on up in that dialogue。

 And let's see if this does anything better。 So Tom is late for the train。

 So it's picking that up but still not great。 here we see person one。

 you could add a painting program， person2， that would be a bonus。 So a little bit better。

 it's not exactly right， but it's getting better。 It's at least picking up some of the nuance Now。

 as part of in context learning you learn there's something called one shot and then few shots。

 So let's get a sample of that here， let's get hands on with one。



![](img/e7932f5ef0eac2c4ad991634ab7c4295_51.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_52.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_53.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_54.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_55.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_56.png)

St and then few shot so earlier we were doing zero shot that means we're not giving it any samples of prompt and then completion All we're doing is just giving it a prompt。

 we are asking the model to do something and seeing what the model generates with one shot and then few shot we will actually give it samples that are correct so or that use the human baseline and that then puts the model into you know gives the model a little bit more information to work on okay so let's see how one shot works here and so all we're doing is just taking a full example including the summary from the human baseline then giving it a second example but without the actual summary and that's the dialogue that we want the model to summarize so let's see how this look So one shot means I'm giving it one complete example including the correct answer as dictated by the human here the human baseline then we give it a second example and ask the model。



![](img/e7932f5ef0eac2c4ad991634ab7c4295_58.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_59.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_60.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_61.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_62.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_63.png)

It's going on， so let's see how we do here。So here we're just gonna do the upgrade software。

 person one wants to upgrade person2 wants to add painting program。 person one wants to add a Cd roM。

 So I think it's a little better。 and let's keep going there's something called few shot inference as well Now some of you might be asking。

 well， this seems like cheating because we're actually giving it one answer and then asking it and it's not really cheating。

 it's more of you' helping the model you know help itself。 Now in future lessons and in future labs。

 we will actually finet the model where we can go back to the zero shot inference which is what you would normally think of as a good language model but here we're just building up some of the intuition here and so keep in mind this is a very。

 very inexpensive way to try out these models and to even figure out which model should you fine tune So we chose plan T5 because it works across a large number of tap。



![](img/e7932f5ef0eac2c4ad991634ab7c4295_65.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_66.png)

But if you have no idea how a model is， if you just get it off of some model hub somewhere。

 these are the first step， so prompt engineering zero shot， One shot。

 U shot is almost always the first step when you're trying to learn the language model that you've been handed。



![](img/e7932f5ef0eac2c4ad991634ab7c4295_68.png)

And data also very dataset specific as well and task specific。

 So few shot means we're giving three full examples。

 including the human baseline summary123 and then a fourth but without the human summary yes even though we have it we're just exploring our model right now。

 and we're saying tell us what that fourth dialogue is that summary and just ignore some of these errors。

 some of these sequences are a bit larger than the 512 context length of the model typically you would probably want to filter out any of these inputs that are larger than 512 but here it still does a pretty good job So here we see a case where the few shot didn't do much better than the one shot。

 And so this is something that you want to pay attention to because in practice people often try to just keep adding more and more shots。

 five shots six shot typically。

![](img/e7932f5ef0eac2c4ad991634ab7c4295_70.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_71.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_72.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_73.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_74.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_75.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_76.png)

In my experience above five or six shots， so full prompt and then completions。

 you really don't gain much after that either the model can do it or it can't do it and you know going above five or six here we see for this particular sample that really one shot was good enough Now the last part of this lab is going to be fun this is where you can actually play with some of these configuration parameters that you learned during the lessons。



![](img/e7932f5ef0eac2c4ad991634ab7c4295_78.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_79.png)

Things like the sampling temperature you can play with these try out and gain your intuition on how these things can impact what's actually generated by the model in some cases for example by raising the temperature up above you know towards one or even closer to two you will get very。

 very creative type of responses if you lower it down I believe 0。

1 is the minimum for the huggingface implementation anyway of this generation config class here that's used when you actually generate I can pass generation config right here if you go down to 0。

1 that will actually make the response more conservative and will oftentimes give you the same response over and over if you go higher I believe actually 2。

0 is the highest if you try 2。0 that will start to give you some you very wild responses it's kind of fun you should try it。



![](img/e7932f5ef0eac2c4ad991634ab7c4295_81.png)

![](img/e7932f5ef0eac2c4ad991634ab7c4295_82.png)