# 吴恩达《Transformer中的注意力机制：概念与PyTorch代码实现》中英字幕（deepseek-R1纠错+翻译 - P6：6.the-matrix-math-for-calculating-masked-self-attention.zh_en - GPT中英字幕课程资源 - BV1AYKpeGEUf

![](img/f744bdceb8a1fd2f40c17e434cdcb4a0_0.png)

In this lesson， you will go through the matrix math required to calculate massed self attention one step at a time。

 like before you'll learn both the how and the why the equation works。 Let's have some fun。Earlier。

 we went through the matrixtri math equation for self attention。



![](img/f744bdceb8a1fd2f40c17e434cdcb4a0_2.png)

And now we're going to go through the matrix math for masked self attention。



![](img/f744bdceb8a1fd2f40c17e434cdcb4a0_4.png)

The good news is that the only difference between the equation for self attention。

And the equation for masked self attention。Is that we add a new matrix M for mask to the scaled similarities。



![](img/f744bdceb8a1fd2f40c17e434cdcb4a0_6.png)

And that means that just like we did earlier， we start by calculating the query。

 key and value matrices。

![](img/f744bdceb8a1fd2f40c17e434cdcb4a0_8.png)

Thus， given the prompt， write a poem。

![](img/f744bdceb8a1fd2f40c17e434cdcb4a0_10.png)

The transformer creates word embeddings。Then it adds positional encoding。

To give us these encoded values。

![](img/f744bdceb8a1fd2f40c17e434cdcb4a0_12.png)

Now we calculate the query， key and value matrices just like before。



![](img/f744bdceb8a1fd2f40c17e434cdcb4a0_14.png)

Now we calculate masked self attention。

![](img/f744bdceb8a1fd2f40c17e434cdcb4a0_16.png)

And just like we did earlier， we'll calculate the similarities between the queries and the keys。



![](img/f744bdceb8a1fd2f40c17e434cdcb4a0_18.png)

Then we scale the similarities。

![](img/f744bdceb8a1fd2f40c17e434cdcb4a0_20.png)

Now we add a masking matrix M to the scaled similarities。



![](img/f744bdceb8a1fd2f40c17e434cdcb4a0_22.png)

The purpose of the mask is to prevent any tokens from including anything that comes after them when calculating attention。

In this example， where the prompt is write a poem。We want the first token， right。

 to only include itself and mask out a poem from its attention calculations。

And we want the second token， A to include itself and write and maskask out poem。

And we want the third token poem to include everything。



![](img/f744bdceb8a1fd2f40c17e434cdcb4a0_24.png)

The masking is done using a matrix that looks like this。

Which adds zeros to values we want to include in the attention calculations。

And negative infinity to any value we need to mask out。



![](img/f744bdceb8a1fd2f40c17e434cdcb4a0_26.png)

Adding0 to something doesn't change it。So these scaled similarities go unchanged。

But adding negative infinity turns these scaled similarities into negative infinity。



![](img/f744bdceb8a1fd2f40c17e434cdcb4a0_28.png)

What that means is that when we apply the soft max function to each row。



![](img/f744bdceb8a1fd2f40c17e434cdcb4a0_30.png)

The first token， right， has 100% similarity to itself。And 0% similarity to anything that came after。

Likewise， the second token A has 0% similarity to the token that came after it poem。

And the last token poem has similarities with everything。



![](img/f744bdceb8a1fd2f40c17e434cdcb4a0_32.png)

And thus， when we finally multiply the percentages by the value matrix。



![](img/f744bdceb8a1fd2f40c17e434cdcb4a0_34.png)

The masked self attention value for the first token right does not include anything that came after it。

Likewise， the masked self attention value for the second token， A only includes right and A。

And the masked self attention value for the last token poem includes everything。



![](img/f744bdceb8a1fd2f40c17e434cdcb4a0_36.png)

And that is how we calculate masked self attention， bam。



![](img/f744bdceb8a1fd2f40c17e434cdcb4a0_38.png)