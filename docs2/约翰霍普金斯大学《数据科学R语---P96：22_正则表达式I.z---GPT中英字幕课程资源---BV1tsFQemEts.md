# 约翰霍普金斯大学《数据科学R语言基础｜Data Science： Foundations using R》中英字幕（deepseek - P96：22_正则表达式I.zh_en - GPT中英字幕课程资源 - BV1tsFQemEts

This lecture is about regular expressions。 We've already seen how the text functions， sub。

 G sub and Gr can be used to manipulate strings and identify patterns that might be of interest。

In this lecture， we'll talk about regular expressions which extends the idea of searching for a specific bit of text to searching for a bit of text that might fit a more broad pattern。



![](img/9288477895a64811ad2f16cb98858303_1.png)

Regular expressions can be thought of as a combination of literals and metacharacters。



![](img/9288477895a64811ad2f16cb98858303_3.png)

So to draw an analogy to natural language， think of literal text forming the words of the language and the metacharacts defining its grammar。

Regular expressions have a rich set of meta charactersact that allow us to search through strings to identify specific patterns of interest that might be very hard to identify with literals。



![](img/9288477895a64811ad2f16cb98858303_5.png)

So here's an example of what I mean by literals， so literals consist of words that match exactly。

 so for example， the literal nuclear would match all of these lines because nuclear appears here in this line。

 nuclear appears here in this line， here in this line here in this line and here in this line。

 so that's the exact letters match in all of those different lines。



![](img/9288477895a64811ad2f16cb98858303_7.png)

![](img/9288477895a64811ad2f16cb98858303_8.png)

![](img/9288477895a64811ad2f16cb98858303_9.png)

The literal Obama would match all of these lines because it appears here。 it appears here。

 it appears here， it appears here， and it appears here。

 So you can find it in each of these different lines。

 and you can actually match exactly what you've observed。



![](img/9288477895a64811ad2f16cb98858303_11.png)

![](img/9288477895a64811ad2f16cb98858303_12.png)

Regular expressions consist in the simplest form of only literals。

 a match occurs only if the exact sequence of literals occurs anywhere in the text being tested。

But what if we only want the word Obama or sentences that end in the word Clinton or Clinton or some other much smaller phrase like Clintoninto？



![](img/9288477895a64811ad2f16cb98858303_14.png)

We need a way to express white spray and word boundaries， sets of literals。

 the beginning and end of a line， or maybe alternatives， things like war or peace。

 and so what we're going to use here are metacharacters in order to specify these more general search terms that we'd like to be able to identify。



![](img/9288477895a64811ad2f16cb98858303_16.png)

![](img/9288477895a64811ad2f16cb98858303_17.png)

So some metacharacters represent the start of the line， so for example。

 if you have a carrot followed by I think it will match the start of a line followed by I think so that will match all of these lines。

 I think we all rule for participating and so forth。

 but it wouldn't match necessarily if the I think came somewhere in the middle of the line。



![](img/9288477895a64811ad2f16cb98858303_19.png)

Dollar sign represents the end of the line， so for example。

 if you have the phrase morning dollar sign， then that will match all of the lines here because morning is the last word in the line。



![](img/9288477895a64811ad2f16cb98858303_21.png)

However， if mourning was a word that appeared only in the middle of the text， it wouldn't match。



![](img/9288477895a64811ad2f16cb98858303_23.png)

We can also consider lists or sets of characters that will be accepted at any given point in the match。

 So， for example， you might have either a lowercase or a capital B。

 either a lowercase or a capital U， either a lowercase or uppercase S and either a lowercase or capital H。

 so that will match all versions of the word bush， regardless of which letters are capitalized。

 So for example， this version has a capital B， this version has all lowercase values。

 this version also has all lowercase values here we have another uppercase value and another uppercase value。

 So it will match any of those because it will match both lowercase and uppercase at every possible letter。



![](img/9288477895a64811ad2f16cb98858303_25.png)

![](img/9288477895a64811ad2f16cb98858303_26.png)

![](img/9288477895a64811ad2f16cb98858303_27.png)

The next things that you can do is you can start combining these together so for example you can say I want to look at the beginning of the line to see either a capital I or a lowercase I so that will either match lines like this whereas the lower case I or a capital I to begin the line followed by am so what it does is it allows the beginning the start of the line。

 either one of the lowercase or capital I and then the literal M。



![](img/9288477895a64811ad2f16cb98858303_29.png)

![](img/9288477895a64811ad2f16cb98858303_30.png)

The other thing that you can do is you can specify actually range of characters or range of letters。



![](img/9288477895a64811ad2f16cb98858303_32.png)

So if you put in square brackets A dash Z， that will match any letter from A to Z that's lowercase。

If you do A dash C lowercase or A dash C uppercase， it will actually look for any of the letters。

 whether they're uppercase or lowercase。So for example， if you make this search right here。

 it's going to start at the beginning of the line and it's going to look for a number between0 and9 followed by any letter。

 so it will match any of these lines because each of the lines starts with a number at the beginning of the line and is followed by a letter as the next letter in the line。



![](img/9288477895a64811ad2f16cb98858303_34.png)

![](img/9288477895a64811ad2f16cb98858303_35.png)

Used in the beginning of a character class， the carrot is also a metachar and indicates that it will it should match any of the characters。

 not in the indicated class。 So for example， here， we're looking at the end of the line with the dollar sign。

 And we're looking for any line that ends in anything other than a period or a question mark。

 because this means either a period or a question mark。

 And this carrot means that it's not either of those two characters。

 So itll match all of these lines because most of them don't have any punctuation and some have exclamation points at the end。



![](img/9288477895a64811ad2f16cb98858303_37.png)

![](img/9288477895a64811ad2f16cb98858303_38.png)