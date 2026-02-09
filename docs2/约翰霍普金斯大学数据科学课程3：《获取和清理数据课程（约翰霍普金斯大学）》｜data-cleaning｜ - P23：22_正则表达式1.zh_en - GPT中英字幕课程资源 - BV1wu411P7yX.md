# 约翰霍普金斯大学数据科学课程3：《获取和清理数据课程（约翰霍普金斯大学）》｜data-cleaning｜ - P23：22_正则表达式1.zh_en - GPT中英字幕课程资源 - BV1wu411P7yX

![](img/528bd216656f638c92a88350dd8a8cba_0.png)

This lecture is about regular expressions。 We've already seen how the text functions， sub。

 G sub and Gr can be used to manipulate strings and identify patterns that might be of interest。



![](img/528bd216656f638c92a88350dd8a8cba_2.png)

![](img/528bd216656f638c92a88350dd8a8cba_3.png)

In this lecture， we'll talk about regular expressions which it extends the idea of searching for a specific bit of text to searching for a bit of text that might fit a more broad pattern。



![](img/528bd216656f638c92a88350dd8a8cba_5.png)

![](img/528bd216656f638c92a88350dd8a8cba_6.png)

Regular expressions can be thought of as a combination of literals and meta charactersacters。



![](img/528bd216656f638c92a88350dd8a8cba_8.png)

So to draw an analogy to natural language， think of literal text forming the words of the language and the metacharacts defining its grammar。



![](img/528bd216656f638c92a88350dd8a8cba_10.png)

Regular expressions have a rich set of meta characters that allow us to search through strings to identify specific patterns of interest that might be very hard to identify with literals。



![](img/528bd216656f638c92a88350dd8a8cba_12.png)

![](img/528bd216656f638c92a88350dd8a8cba_13.png)

So here's an example of what I mean by literals， so literals consist of words that match exactly。

 so for example， the literal nuclear would match all of these lines because nuclear appears here in this line。

 nuclear appears here in this line， here in this line here in this line and here in this line。

 so that's the exact letters match in all of those different lines。



![](img/528bd216656f638c92a88350dd8a8cba_15.png)

![](img/528bd216656f638c92a88350dd8a8cba_16.png)

![](img/528bd216656f638c92a88350dd8a8cba_17.png)

![](img/528bd216656f638c92a88350dd8a8cba_18.png)

![](img/528bd216656f638c92a88350dd8a8cba_19.png)

![](img/528bd216656f638c92a88350dd8a8cba_20.png)

The literal Obama would match all of these lines because it appears here。 it appears here。

 it appears here， it appears here， and it appears here。

 So you can find it in each of these different lines。

 and you can actually match exactly what you've observed。



![](img/528bd216656f638c92a88350dd8a8cba_22.png)

![](img/528bd216656f638c92a88350dd8a8cba_23.png)

![](img/528bd216656f638c92a88350dd8a8cba_24.png)

Regular expressions consist in the simplest form of only literals。

 a match occurs only if the exact sequence of literals occurs anywhere in the text being tested。



![](img/528bd216656f638c92a88350dd8a8cba_26.png)

![](img/528bd216656f638c92a88350dd8a8cba_27.png)

But what if we only want the word Obama or sentences that end in the word Clinton or Clinton or some other much smaller phrase like Clintoninto？



![](img/528bd216656f638c92a88350dd8a8cba_29.png)

![](img/528bd216656f638c92a88350dd8a8cba_30.png)

We need a way to express white sprays and word boundaries， sets of literals。

 the beginning and end of a line， or maybe alternatives， things like war or peace。

 and so what we're going to use here are metacharacters in order to specify these more general search terms that we'd like to be able to identify。



![](img/528bd216656f638c92a88350dd8a8cba_32.png)

![](img/528bd216656f638c92a88350dd8a8cba_33.png)

![](img/528bd216656f638c92a88350dd8a8cba_34.png)

![](img/528bd216656f638c92a88350dd8a8cba_35.png)

So some metacharacters represent the start of the line， so for example。

 if you have a carrot followed by I think it will match the start of a line followed by I think so that will match all of these lines。

 I think we all rule for participating and so forth。

 but it wouldn't match necessarily if the I think came somewhere in the middle of the line。



![](img/528bd216656f638c92a88350dd8a8cba_37.png)

![](img/528bd216656f638c92a88350dd8a8cba_38.png)

![](img/528bd216656f638c92a88350dd8a8cba_39.png)

![](img/528bd216656f638c92a88350dd8a8cba_40.png)

Dollar sign represents the end of the line， so for example。

 if you have the phrase morning dollar sign， then that will match all of the lines here because morning is the last word in the line。



![](img/528bd216656f638c92a88350dd8a8cba_42.png)

![](img/528bd216656f638c92a88350dd8a8cba_43.png)

![](img/528bd216656f638c92a88350dd8a8cba_44.png)

However， if mourning was a word that appeared only in the middle of the text， it wouldn't match。



![](img/528bd216656f638c92a88350dd8a8cba_46.png)

We can also consider lists or sets of characters that will be accepted at any given point in the match。

 so， for example， you might have either a lowercase or a capital B。

 either a lowercase or a capital U， either a lowercase or uppercase S and either a lowercase or capital S H So that will match all versions of the word bush regardless of which letters are capitalized。

 So for example， this version has a capital B this version has all lowercase values。

 this version also has all lowercase values here we have another uppercase value and another uppercase value So it will match any of those because it will match both lowercase and uppercase at every possible letter。



![](img/528bd216656f638c92a88350dd8a8cba_48.png)

![](img/528bd216656f638c92a88350dd8a8cba_49.png)

![](img/528bd216656f638c92a88350dd8a8cba_50.png)

![](img/528bd216656f638c92a88350dd8a8cba_51.png)

![](img/528bd216656f638c92a88350dd8a8cba_52.png)

![](img/528bd216656f638c92a88350dd8a8cba_53.png)

![](img/528bd216656f638c92a88350dd8a8cba_54.png)

![](img/528bd216656f638c92a88350dd8a8cba_55.png)

![](img/528bd216656f638c92a88350dd8a8cba_56.png)

The next things that you can do is you can start combining these together so for example。

 you can say I want to look at the beginning of the line to see either a capital I or a lowercase I so that will either match lines like this whereas the lower case I or a capital I to begin the line followed by am so what it does is it allows the beginning the start of the line。

 either one of the lowercase or capital I and then the literal M。



![](img/528bd216656f638c92a88350dd8a8cba_58.png)

![](img/528bd216656f638c92a88350dd8a8cba_59.png)

![](img/528bd216656f638c92a88350dd8a8cba_60.png)

![](img/528bd216656f638c92a88350dd8a8cba_61.png)

![](img/528bd216656f638c92a88350dd8a8cba_62.png)

![](img/528bd216656f638c92a88350dd8a8cba_63.png)

The other thing that you can do is you can specify actually range of characters or range of letters。



![](img/528bd216656f638c92a88350dd8a8cba_65.png)

So if you put in square brackets A dash Z， that will match any letter from A to Z that's lowercase。



![](img/528bd216656f638c92a88350dd8a8cba_67.png)

If you do A dash C lowercase or A dash C uppercase， it will actually look for any of the letters。

 whether they're uppercase or lowercase。

![](img/528bd216656f638c92a88350dd8a8cba_69.png)

![](img/528bd216656f638c92a88350dd8a8cba_70.png)

So for example， if you make this search right here。

 it's going to start at the beginning of the line and it's going to look for a number between 0 and9 followed by any letter。

 so it will match any of these lines because each of the lines starts with a number at the beginning of the line and is followed by a letter as the next letter in the line。



![](img/528bd216656f638c92a88350dd8a8cba_72.png)

![](img/528bd216656f638c92a88350dd8a8cba_73.png)

![](img/528bd216656f638c92a88350dd8a8cba_74.png)

![](img/528bd216656f638c92a88350dd8a8cba_75.png)

Used in the beginning of a character class， the carrot is also a meta character and indicates that it will it should match any of the characters。

 not in the indicated class。 So， for example， here。

 we're looking at the end of the line with the dollar sign。

 and we're looking for any line that ends in anything other than a period or a question mark because this means either a period or a question mark。

 And this carrot means that it's not either of those two characters。

 So it'll match all of these lines because most of them don't have any punctuation and some have exclamation points at the end。



![](img/528bd216656f638c92a88350dd8a8cba_77.png)

![](img/528bd216656f638c92a88350dd8a8cba_78.png)

![](img/528bd216656f638c92a88350dd8a8cba_79.png)

![](img/528bd216656f638c92a88350dd8a8cba_80.png)

![](img/528bd216656f638c92a88350dd8a8cba_81.png)

![](img/528bd216656f638c92a88350dd8a8cba_82.png)