# Langchain初学者入门2025 p23 P23_#23_RAGs_工作流程_第2部分 -BV1jgeWzYEey_p23-

Now let's look at the second part of the workflow it starts with the user asking a question about the book let's say the book is lot of the rings right so let's say the question is what is the name of Frodo sword right so now what we do is we also convert this question that prompt into an embedding as well okay now the next thing is we have a retriever component right here that takes this embedding which we know is the mathematical representation of the prompt and then asks the vector store hey give me the top five relevant chunks for this particular question。

😊。

![](img/aaab87f7963965f99ee1a87932c9f8c1_1.png)

![](img/aaab87f7963965f99ee1a87932c9f8c1_2.png)

![](img/aaab87f7963965f99ee1a87932c9f8c1_3.png)

![](img/aaab87f7963965f99ee1a87932c9f8c1_4.png)

![](img/aaab87f7963965f99ee1a87932c9f8c1_5.png)

![](img/aaab87f7963965f99ee1a87932c9f8c1_6.png)

OkayAnd the vector store vector stores basically have very low latency meaning they are very fast because they are working with numbers right so this vector store with its extremely low latency and high speed gives back the top five chunks with the highest relevant scores right so at this point we have two things we have the user's question right here in English as well as the passages from the book in the form of smaller chunks that answers the user's question chunks that are relevant to the user's question al right so now we have the top five chunks right now what we are going to be doing is we are going to send both the question in plain text as well as the chunk in plain text to the LLM right so now the LLM has all the relevant passages and also the user's question so the LLM is now able to sort of reason and give a very informed answer and finally the LLM is going to respond back to the user right here I hope you now have。

😊。

![](img/aaab87f7963965f99ee1a87932c9f8c1_8.png)

![](img/aaab87f7963965f99ee1a87932c9f8c1_9.png)

![](img/aaab87f7963965f99ee1a87932c9f8c1_10.png)

![](img/aaab87f7963965f99ee1a87932c9f8c1_11.png)

![](img/aaab87f7963965f99ee1a87932c9f8c1_12.png)

![](img/aaab87f7963965f99ee1a87932c9f8c1_13.png)

![](img/aaab87f7963965f99ee1a87932c9f8c1_14.png)

![](img/aaab87f7963965f99ee1a87932c9f8c1_15.png)

![](img/aaab87f7963965f99ee1a87932c9f8c1_16.png)

![](img/aaab87f7963965f99ee1a87932c9f8c1_17.png)

![](img/aaab87f7963965f99ee1a87932c9f8c1_18.png)

![](img/aaab87f7963965f99ee1a87932c9f8c1_19.png)

A full picture of rags and how they work now rags are pretty great when it comes to you know giving our private data to the LLm basically giving it this additional data and we can sort of chat with our data right so that is one use case。

😊。

![](img/aaab87f7963965f99ee1a87932c9f8c1_21.png)

![](img/aaab87f7963965f99ee1a87932c9f8c1_22.png)

![](img/aaab87f7963965f99ee1a87932c9f8c1_23.png)

We can also there is another way of looking at drags okay we can also think of rags as giving long term memory to LLMs right so Ill give you a very simple example so I'll give you one final example to better understand this let's say there is a customer support bo。

😊。

![](img/aaab87f7963965f99ee1a87932c9f8c1_25.png)

![](img/aaab87f7963965f99ee1a87932c9f8c1_26.png)

![](img/aaab87f7963965f99ee1a87932c9f8c1_27.png)

Okay so all the past conversations with a specific user can be stored in a vector database so that in the future if there is a specific question from history rags can go and retrieve that particular relevant chunk and give more accurate answers so in the next few sections we are going to be looking at how to code all of this with the same example that we saw right now and you'll see it is actually much more simpler than it looks so I'll see you in the next section。

😊。

![](img/aaab87f7963965f99ee1a87932c9f8c1_29.png)

![](img/aaab87f7963965f99ee1a87932c9f8c1_30.png)

![](img/aaab87f7963965f99ee1a87932c9f8c1_31.png)