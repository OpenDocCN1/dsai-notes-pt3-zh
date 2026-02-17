# 吴恩达《Transformer中的注意力机制：概念与PyTorch代码实现》中英字幕（deepseek-R1纠错+翻译 - P3：3.the-matrix-math-for-calculating-self-attention.zh_en - GPT中英字幕课程资源 - BV1AYKpeGEUf

![](img/73b33da29d8c198be87fb6949cab4436_0.png)

In this lesson， you'll go to the matrix math required to calculate self attention one step at a time。

 You'll learn both the how and why the equation works the way it does。 All right， let's go。

At first glance， the equation for calculating self attention can be a little intimidating。

 but don't worry， we're going to break it down into small， easy to understand pieces。

 We'll start with these variables。 Q stands for query。K stands for key， and V stands for value。

The terms query， key and value come from database terminology。

 So let's talk about databases for a little bit。

![](img/73b33da29d8c198be87fb6949cab4436_2.png)

Imagine we had a database of guests at a hotel that paired each guest's last name with their room number。

😊。

![](img/73b33da29d8c198be87fb6949cab4436_4.png)

Now， imagine Stat sququach is working at the desk one night。

 and I check in until sququatch my last name， Starmer。



![](img/73b33da29d8c198be87fb6949cab4436_6.png)

However， instead of correctly spelling my last name Starmer。

 sququatch types a stammer into the computer。

![](img/73b33da29d8c198be87fb6949cab4436_8.png)

Now the computer has to figure out what last name in the database is closest to whatever squatch typed in。

In database terminology， what sququaash typed in， the search term is called a query。

And the actual names in the database that we are searching are the keys。

So the computer compares the query to all of the keys in the database。And ranks each one。

And in this case， the query， stammer。Is closest to the key for Stmer。

 And so the computer returns my room number 5，3，7。

![](img/73b33da29d8c198be87fb6949cab4436_10.png)

And in database terminology， we'd call the room number the value。

To summarize the database terminology。The query is the thing we are using to search the database。

And the computer calculates similarities between the query and all of the keys in the database。

And the values are what the database returns as the results of the search。



![](img/73b33da29d8c198be87fb6949cab4436_12.png)

Bam。Going back to the equation for self attention。We now have a better idea of what the Q。

 K and V variables refer to。Now let's talk about how we determine the queries， keys。

 and values in the context of a transformer。First， let's remember that self attention calculates similarities between each word and itself and all of the other words。



![](img/73b33da29d8c198be87fb6949cab4436_14.png)

And self attention calculates these similarities for every word in the sentence。

And that means we need to calculate a query and a key for each word。

And just like we saw in the database example， each key needs to return a value。



![](img/73b33da29d8c198be87fb6949cab4436_16.png)

So in order to keep our examples small enough that we can easily calculate things by hand。

 let's use the prompt。 write， a poem。

![](img/73b33da29d8c198be87fb6949cab4436_18.png)

And just like we saw in a previous lesson， the first thing a transformer does is convert each word in the prompt into word embeddings。



![](img/73b33da29d8c198be87fb6949cab4436_20.png)

And then the transformer adds positional encoding to the word embeddings。

To get these numbers or encodings that represent each word in the prompt。Note in this simple example。

 we're just going to use two numbers to represent each word in the prompt。 However。

 it's much more common to use 512 or more numbers to represent each word。Anyway。

 in order to create the queries for each word， we stack the encodings in a matrix。



![](img/73b33da29d8c198be87fb6949cab4436_22.png)

And multiply that matrix by a2 by two matrix of query weights。

To calculate two query numbers per word。Note， we multiplied the encoded values by a two by two matrix。

Because we started with two encoded values per word。

And a two by two matrix allows us to end up with two query numbers per word。



![](img/73b33da29d8c198be87fb6949cab4436_24.png)

If instead， we had started with 512 word embeddings per word， and thus 512 encoded values per word。

Then a common thing to do would be to use a 512 by 512 matrix to create 512 query numbers per word。

That being said， the only rule that you really have to follow is that the matrix math has to be possible。

Also， I want to point out that I've labeled the query weights matrix with the transpose symbol。

 This is because pi torch prints out the weights in a way that requires them to be transposed before we can get the math to work out correctly。

 Small bam。

![](img/73b33da29d8c198be87fb6949cab4436_26.png)

Now we create the keys by multiplying the encoded values by a2 by two matrix of key weights。



![](img/73b33da29d8c198be87fb6949cab4436_28.png)

And we create the values by multiplying the encoded values by a two by two matrix of value weights。



![](img/73b33da29d8c198be87fb6949cab4436_30.png)

Now that we have the query， key and values for each token。



![](img/73b33da29d8c198be87fb6949cab4436_32.png)

We can use them to calculate self attention。

![](img/73b33da29d8c198be87fb6949cab4436_34.png)

We start by multiplying the query matrix Q。By the transpose of the key matrix K， Josh。

 why do we need to transpose K when we do this multiplication。



![](img/73b33da29d8c198be87fb6949cab4436_36.png)

![](img/73b33da29d8c198be87fb6949cab4436_37.png)

Well， in this specific case， the obvious thing is that the multiplication wouldn't work if we didn't transpose K。

Then the two numbers in the first row of Q could multiply the top two numbers in the first column in K。

 But then the bottom number would be left out of the fun。So in this case。

 multiplying by K without transposing it is a bad idea for technical reasons。



![](img/73b33da29d8c198be87fb6949cab4436_39.png)

However， there's actually a much more important reason to transpose K and to understand it。

 let's go through the multiplication one step at a time。



![](img/73b33da29d8c198be87fb6949cab4436_41.png)

We start with the first row and Q， the query for the word right and the first column in K transposed。

 the key for the word right。The matrix's multiplication gives us the sum of these products。

 which is negative 0。09。This process of multiplying pairs of corresponding numbers together and adding them up。

 like we did here， is called calculating a dot product。So a negative 0。

09 is the dot product of the query and the key for the word right dot products can be used as an unsscaleed measure of similarity between two things。

 And this metric is closely related to something called the cosine similarity。

The big difference is that the cosine similarity scales the dot product to be between negative1 and one。

 In contrast， the dot product similarity isn't scaled。So that makes negative 0。09。

 an unscaleed similarity between the query and the key for the word right。Likewise。

 the unscaleed dot product similarity between the query for right and the key for A is 0。06。

And the unscaleed dot product similarity between the query for write and the key for poem is negative 0。

61。

![](img/73b33da29d8c198be87fb6949cab4436_43.png)

Likewise， we calculate the unscaleed dot product similarities between the query for a and all of the keys。

And the unscaleed dot product similarities between the query for poem and all of the keys。Thus。

 by multiplying Q by the transpose of K， we end up with the unscaleed dot product similarities between all possible combinations of queries and keys for each word。



![](img/73b33da29d8c198be87fb6949cab4436_45.png)

Double bam。

![](img/73b33da29d8c198be87fb6949cab4436_47.png)

Now， the next thing we do is scale the dot product similarities by the square root of D sub K。

D sub K is the dimension of the key matrix。And in this case。

 dimension refers to the number of values we have for each token， which is2。

So we scale each dot product similarity by the square root of two。

 and that gives us a matrix of scaled dot product similarities。 Note。

 scaling by just the square root of the number of values per token doesn't scale the dot product similarities in any kind of systematic way。



![](img/73b33da29d8c198be87fb6949cab4436_49.png)

That said， even with this limited scaling， the original authors of the transformer said it improved performance。



![](img/73b33da29d8c198be87fb6949cab4436_51.png)

Small bam。The next thing we do is take the softm of each row in the matrix of scaled dot product similarities。



![](img/73b33da29d8c198be87fb6949cab4436_53.png)

![](img/73b33da29d8c198be87fb6949cab4436_54.png)

And taking the soft max of each row gives us these new rows。😊，Note。

 the soft max function makes it so that the sum of each row is one。



![](img/73b33da29d8c198be87fb6949cab4436_56.png)

So we can think of these values as a summary of the relationships among the tokens。For example。

 the word right is 36% similar to itself。40% similar to a。And 24 per cent， similar to poem。



![](img/73b33da29d8c198be87fb6949cab4436_58.png)

Bam。Now let's put these new rows back together to form a matrix。

And the last thing we do to calculate self attention is multiply the percentages by the values in matrixtri v。

To understand exactly why we do this multiplication， let's go through it step by step。

When we multiply the first row percentages by the first column in V。

We calculate 36% of the first value for the word， right。And add it to 40% of the first value for a。

And then add 24% of the first value for poem。And that gives us 1。0。

 the first self attention score for the word right。In other words。

 the percentages that come out of the soft max function。

Tell us how much influence each word should have on the final encoding for any given word。



![](img/73b33da29d8c198be87fb6949cab4436_60.png)

Likewise， we scale the second column of values to get the second self attention score for the word right。



![](img/73b33da29d8c198be87fb6949cab4436_62.png)

Then we scale the values by the percentages for a to get the self attention scores for a。

 and then scale the values by the percentages for poem to get the self attention scores for poem。

And at long last， we have calculated the self attention scores for each input token。



![](img/73b33da29d8c198be87fb6949cab4436_64.png)

Bam。In summary， the equation for self attention may look intimidating。

 but all it does is calculate the scaled dot product similarities among all of the words。

Convert those scaled similarities into percentages with the softm function。

And then use those percentages to scale the values to become the self attention scores for each word。



![](img/73b33da29d8c198be87fb6949cab4436_66.png)

Triple bam。