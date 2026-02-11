# Edureka《通过LLMs学习生成式AI（基础、应用开发、流行工具，第2、3、4课／共4课）｜Learn Generative AI with LLMs》中英 - P54：17_Transformer的工作原理.zh_en - GPT中英字幕课程资源 - BV1ym421V7gx

![](img/a537d07002765d56367d530fa3008c42_0.png)

So let's now explore the progression from our previous discussion。

 so now let's understand how do transformers work step bystead the first step is encoded decoder architecture so imagine two characters in a story picture a storyteller it is nothing but an encoder and the character it is nothing but a decoder means the two characters here are storyteller and storyteller as encoder and the character as decoder so a storyteller analyzes the story using the input sequence and generates generates a vector a summary of the story meaning means here the character which is nothing but a decoder uses the summary to create a translated version of the story that is nothing but a output sentence means the most language models or the elements adopt an encoded decoder architecture where the encoder cross。

😊。

![](img/a537d07002765d56367d530fa3008c42_2.png)

![](img/a537d07002765d56367d530fa3008c42_3.png)

![](img/a537d07002765d56367d530fa3008c42_4.png)

![](img/a537d07002765d56367d530fa3008c42_5.png)

![](img/a537d07002765d56367d530fa3008c42_6.png)

![](img/a537d07002765d56367d530fa3008c42_7.png)

![](img/a537d07002765d56367d530fa3008c42_8.png)

![](img/a537d07002765d56367d530fa3008c42_9.png)

![](img/a537d07002765d56367d530fa3008c42_10.png)

![](img/a537d07002765d56367d530fa3008c42_11.png)

![](img/a537d07002765d56367d530fa3008c42_12.png)

![](img/a537d07002765d56367d530fa3008c42_13.png)

is the input with self attention to create a meaningful vector and the decoder uses this information to generate an output such as translated sentence So that's about encoded decoder architecture then the second step is self attention So analyzing the relationships into a sentences means think of each word in a sentence as a character in a mystery novel selfat works like the detective or the current word analyzing the relationship with other characters or other words each word assign course to other others based on the relevance and the detective combines information from the most relevant characters enhancing its understanding means self attention is at the core of the encoder where each word is analyzed assign course based on the relevant to others and combined with information from the most relevant words this mechanism。

😊。

![](img/a537d07002765d56367d530fa3008c42_15.png)

![](img/a537d07002765d56367d530fa3008c42_16.png)

![](img/a537d07002765d56367d530fa3008c42_17.png)

![](img/a537d07002765d56367d530fa3008c42_18.png)

![](img/a537d07002765d56367d530fa3008c42_19.png)

![](img/a537d07002765d56367d530fa3008c42_20.png)

![](img/a537d07002765d56367d530fa3008c42_21.png)

![](img/a537d07002765d56367d530fa3008c42_22.png)

![](img/a537d07002765d56367d530fa3008c42_23.png)

![](img/a537d07002765d56367d530fa3008c42_24.png)

![](img/a537d07002765d56367d530fa3008c42_25.png)

![](img/a537d07002765d56367d530fa3008c42_26.png)

helpslps capture the complex relationships in the sentences That is about the self attentionten。

 Then the next step is multi head attention。 So， for example。

 envision multiple detectives such as attention heads working on different aspects of the mystery like analyzing the grammar semantics or the sentiment。

 Each detective provides a unique perspective， correctly contributing to a comprehensive understanding means multi head attention involves parallel attention heads capturing various input aspects simultaneously This enables the model to consider the different faces of the input。

 En its ability to understand and process the complex information。

 Then the next step means the residual connection and layer normalization。 What exactly happens here。

 So consider these as stabilizes in the story。😊。

![](img/a537d07002765d56367d530fa3008c42_28.png)

![](img/a537d07002765d56367d530fa3008c42_29.png)

![](img/a537d07002765d56367d530fa3008c42_30.png)

![](img/a537d07002765d56367d530fa3008c42_31.png)

![](img/a537d07002765d56367d530fa3008c42_32.png)

![](img/a537d07002765d56367d530fa3008c42_33.png)

![](img/a537d07002765d56367d530fa3008c42_34.png)

![](img/a537d07002765d56367d530fa3008c42_35.png)

![](img/a537d07002765d56367d530fa3008c42_36.png)

![](img/a537d07002765d56367d530fa3008c42_37.png)

So residual connections and layer normalizations are the techniques that ensures a stable and smooth plot development the help in stabilizing training and facilitating the learning of long strange dependencies in the text means these techniques are essential stable training and improving the model's ability to learn complex patterns and depends within the input data means transformers work by employing the encoder decoder architecture。

 using the selfatten to analyze the relationships with the sentence。

 incorporating multi head attention for a comprehensive understanding and employing stabilizing techniques like residual connections and layer normalization to facilitate the effective training and learning Now the summary in this lesson we delvet into transformers key components of many language models or the last。

😊。

![](img/a537d07002765d56367d530fa3008c42_39.png)

![](img/a537d07002765d56367d530fa3008c42_40.png)

![](img/a537d07002765d56367d530fa3008c42_41.png)

![](img/a537d07002765d56367d530fa3008c42_42.png)

![](img/a537d07002765d56367d530fa3008c42_43.png)

![](img/a537d07002765d56367d530fa3008c42_44.png)

![](img/a537d07002765d56367d530fa3008c42_45.png)

![](img/a537d07002765d56367d530fa3008c42_46.png)

![](img/a537d07002765d56367d530fa3008c42_47.png)

![](img/a537d07002765d56367d530fa3008c42_48.png)

![](img/a537d07002765d56367d530fa3008c42_49.png)

![](img/a537d07002765d56367d530fa3008c42_50.png)

W models these models use an encoded decoder architecture featuring self attention mechanism that analyze each words relevance and enhances understanding additionally multi head attention residual connections and layer normalization contribute to stable training and the ability to capture diverse aspects of the input data so making transformers powerful tool for text generation so that is a summary Thank you。

😊。

![](img/a537d07002765d56367d530fa3008c42_52.png)

![](img/a537d07002765d56367d530fa3008c42_53.png)

![](img/a537d07002765d56367d530fa3008c42_54.png)

![](img/a537d07002765d56367d530fa3008c42_55.png)

![](img/a537d07002765d56367d530fa3008c42_56.png)