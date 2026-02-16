# 杜克大学《大型语言模型实践（生成式AI简介、Azure的LLMs（1、2课，共6课）｜Large Language Model Operations》 - P124：47_03_02_功能概述.zh_en - GPT中英字幕课程资源 - BV1Ef421m7zD

![](img/41872ecdb1f5379b5e52780043b266c9_0.png)

Let's have a quick overview of functions and how do they work and let's start here by looking at the user input so the user input would be anything that a user will ask a question to a large language model or anything that is essentially a prompt so we start here by gathering this prompt right and then the next logical step in in this whole processes go to the chat application so the prompt goes all the way to the chat application the chat application will just start processing this could be semantic kernel。

 it could be anything could be a framework or it could be just using simple libraries that allows us to interact with the LLM。



![](img/41872ecdb1f5379b5e52780043b266c9_2.png)

So then the chat application will grab that prompt that we defined or capture first with the input and then it will go all the way to the LLM right so say for example what's the weather in January in Boston for example。

 so then that prompt goes to the LLM and the LLM is like well you know usually it will be something related to that now what we can do here is that when the LLM response we can we can have this function。



![](img/41872ecdb1f5379b5e52780043b266c9_4.png)

where the LLM will go and process that input and be able to extract certain things in that we can actually pass into the prompt so instead of having these one two and then step three number here with the LLM and then going back to the chat and back to the user what we're going to have is a function and the function is going to act as an intermediary step。

 so what we're going to have here， I'm going to remove these arrows right there。



![](img/41872ecdb1f5379b5e52780043b266c9_6.png)

![](img/41872ecdb1f5379b5e52780043b266c9_7.png)

It's not going to be a workflow like that at all we going to have here is the OM is going to respond to the chat。



![](img/41872ecdb1f5379b5e52780043b266c9_9.png)

And it's going to say， hey I receive this message and the chat we applying some logic and some interaction with the LLM can say hey does this look like something that we can actually use and pass to our function of our function right here。

 step number four could be a function that does something in the cloud for example has like a weather API a weather API is a perfect example of these so theLM says like it seems like I'm getting asked about the weather so I think the function related to the weather might be a good thing to interact with so then the chat will just go and send some information to the function。

 the function will get that information will do some processing and then it will return that information to the chat so say for example it captures accurate weather stats for Boston in January and then with that information with that added context then that goes back。



![](img/41872ecdb1f5379b5e52780043b266c9_11.png)

![](img/41872ecdb1f5379b5e52780043b266c9_12.png)

![](img/41872ecdb1f5379b5e52780043b266c9_13.png)

![](img/41872ecdb1f5379b5e52780043b266c9_14.png)

![](img/41872ecdb1f5379b5e52780043b266c9_15.png)

![](img/41872ecdb1f5379b5e52780043b266c9_16.png)

![](img/41872ecdb1f5379b5e52780043b266c9_17.png)

![](img/41872ecdb1f5379b5e52780043b266c9_18.png)

![](img/41872ecdb1f5379b5e52780043b266c9_19.png)

![](img/41872ecdb1f5379b5e52780043b266c9_20.png)

Back to the LM。Back to the ELM， then back to the chat and then back to the user。

So instead of going from input to chat to LLM to chat to input。

 we're doing a potential intermediate step， which is input， chat， LLM， chat， then function。



![](img/41872ecdb1f5379b5e52780043b266c9_22.png)

![](img/41872ecdb1f5379b5e52780043b266c9_23.png)

![](img/41872ecdb1f5379b5e52780043b266c9_24.png)

Then chat， LLM chat and then input so it is a little bit complicated or it seems a little bit complicated。

 but the only or the important thing is that we are adding superpowers almost like a plug to the LLM。

 the LM is just a probability machine， we're adding some grounding and some context some extra data that we can fetch using an extra function and we'll see how we can put all that together。



![](img/41872ecdb1f5379b5e52780043b266c9_26.png)

![](img/41872ecdb1f5379b5e52780043b266c9_27.png)

![](img/41872ecdb1f5379b5e52780043b266c9_28.png)

![](img/41872ecdb1f5379b5e52780043b266c9_29.png)

![](img/41872ecdb1f5379b5e52780043b266c9_30.png)

![](img/41872ecdb1f5379b5e52780043b266c9_31.png)