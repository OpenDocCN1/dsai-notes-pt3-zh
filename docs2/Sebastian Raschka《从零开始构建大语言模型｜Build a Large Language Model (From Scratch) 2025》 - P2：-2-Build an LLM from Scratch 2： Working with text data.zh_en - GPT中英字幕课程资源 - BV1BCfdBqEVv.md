# Sebastian Raschka《从零开始构建大语言模型｜Build a Large Language Model (From Scratch) 2025》 - P2：-2-Build an LLM from Scratch 2： Working with text data.zh_en - GPT中英字幕课程资源 - BV1BCfdBqEVv

Yeah hi and， welcome back everyone to the supplementary coding a long video series for theBuild a largege language model from scratchbook Here we are now going to talk about chapter 2 working with text data which means essentially that we are going to prepare the data that we are going to use to train the LLM Yeah just to go to the chapter itself Cha2 you can see there are lots of sections。

 starting at the top the goal really here is to prepare the data set for the LLM So there is actually a nice figure here that shows you this step in the grand scheme of the whole LLM building process So here building an LLM means setting up the data set coding the attention mechanism coding the LLM architecture and so forth This is really the first stage of you know training the LLM and then the pretraining comes in stage two and then later on in stage3 we will be fine tuning the LLM but you know just to keep things。

😊。

![](img/d4ac733fd952997f5b89e860e95e4d9a_1.png)

![](img/d4ac733fd952997f5b89e860e95e4d9a_2.png)

![](img/d4ac733fd952997f5b89e860e95e4d9a_3.png)

Fcused here we are going to talk about preparing the data。And yeah， to give you another view here。

 essentially what we are going to do is we are going to take text and tokenize it and then convert these tokenized。

Subparts of the text into token IDs which we will be then encoding into vectors。

 I know this is maybe a bit faster here in this video。

 so I mentioned before the videos are not as detailed as the book itself and they' are more focused as supplementary resource for the coding examples but yeah just to give you the big picture here so the goal is really to yeah prepare raw text data so that the LLM can then process it it's really that the LLM works with text but you know we have to first convert it into a format that it can be yeah that can be read。

 let's say in a form that the LLM understands which in that sense here is actually vectors like mathematical vectors。

And if I scroll up a bit， it's really like the idea also that。

 yeah vectors are numeric representations here of this text so so that is our goal going from letters and words into a more numeric representation。

 which can then be used later on during the pretrain to optimize the weight parameters of that LLM。

But yeah， I don't want to go too far ahead and talk about pre training。

 The focus here really is on preparing here the。Input data for the LLM and specifically in section 2 tokenizing text。

 the focus is really also only on this supperpar here at the bottom where we take some input text and we yeah we break it down into individual smaller chunks。

 And yeah， and this is the process known as yeah tokenization。 just to show you an example。



![](img/d4ac733fd952997f5b89e860e95e4d9a_5.png)

So we will be using a library called tickk toking later。 and there is， I think， a nice。



![](img/d4ac733fd952997f5b89e860e95e4d9a_7.png)

![](img/d4ac733fd952997f5b89e860e95e4d9a_8.png)

Nice， yeah， virtual visualization T tokenizer when we go here and they do have different LLMs。

 For example， there is this GP2 LL M。 If we type some text， let's say hello。



![](img/d4ac733fd952997f5b89e860e95e4d9a_10.png)

World something like this this。Is a test。 So here you can really see how it's broken down into individual token so you can see hello is a token。

 the comma is a token world is a token dot is a token and these are the token Is We will get to the token Is later on how they are created for now the focus is really like to just break it down into individual parts and we are not going to implement actually the exact same algorithm that is used here。

 I do have some bonus material on doing that as we'll share later。

Im here first we want to do the big picture level of how we can actually break down text into individual chunks。

 So one way would be essentially to yeah use just regular expressions。

 but yeah starting starting sequentially like how I did in the book let's actually download the data set first and we will be using the data later in this chapter to actually yeah implement the data loadus in Pythtorch so let's let's start with the data set here before I go too much ahead and talk about all the other things。

 so we are going to use the library OS which is just a standard Python library and URL request which is。

Also， a standard Python library。 This is usually for working with files。

 and this is for downloading things from the internet。

 So the data set we are going to work with here。It's called the verdict。

 So let me just go here and a new tap。 And the verdict is。



![](img/d4ac733fd952997f5b89e860e95e4d9a_12.png)

A short story by Edith Wtton， Wharton。

![](img/d4ac733fd952997f5b89e860e95e4d9a_14.png)

So it's。Available as public domain data。

![](img/d4ac733fd952997f5b89e860e95e4d9a_16.png)

I think that's a Wikipedia version that is actually quite nice。



![](img/d4ac733fd952997f5b89e860e95e4d9a_18.png)

Here， so this is a very short story here and I've picked this one as the data because yeah we want to keep things simple that it doesn't take too long when we are actually pretraining the LLM because it's more for educational purposes and it's also you know pretty simple readable and most importantly it's a public domain data or a book so that means we can use it without having to worry about copyright restrictions for example。

 in the United States at least so in that case this is an open public domain data there is no yeah concern using this for example for LLM training。



![](img/d4ac733fd952997f5b89e860e95e4d9a_20.png)

![](img/d4ac733fd952997f5b89e860e95e4d9a_21.png)

![](img/d4ac733fd952997f5b89e860e95e4d9a_22.png)

![](img/d4ac733fd952997f5b89e860e95e4d9a_23.png)

Okay， so we would download this data set so we could what we could do is we could go here。



![](img/d4ac733fd952997f5b89e860e95e4d9a_25.png)

Just copy and paste this。And create a new file， a text file。

 insert this and save it and so forth I have a little bit of a quicker way here so I actually let me just copy and paste this I have it also in the Github repository here for the book and so this link is a URL link to the place on Github where I provided this data set just in case you know in the future the data set might become unavailable from Wiki PDF or something here you can find a version in the books GitHub repository RA ASBT atMs dash from dash scratcht。

😊。

![](img/d4ac733fd952997f5b89e860e95e4d9a_27.png)

![](img/d4ac733fd952997f5b89e860e95e4d9a_28.png)

![](img/d4ac733fd952997f5b89e860e95e4d9a_29.png)

And in chapter1， sorry， sorry， Cha 2 in the first folder， main chapter code。

 I included the verdict here and。If you want to copy something from yeah Github as raw text。

 you have to click on this raw here。 and then yeah， you get the the raw text， which in this case。

 yeah， as you can see is。

![](img/d4ac733fd952997f5b89e860e95e4d9a_31.png)

Similar。To what you can see on this page。So。If I copy it this URL now。



![](img/d4ac733fd952997f5b89e860e95e4d9a_33.png)

Insert it here， the three the same URL that you have seen earlier without the line breaks。

When I execute this code， it will download this data set and save it to a file。

 the dash verdict ort text。Let me do that and then maybe refresh here。 And yeah。

 you can see it's now in this folder。 So it's locally now on our computer。

 The next step would be opening this file in Python。

 So right now it's just sitting in our computer and the next step would be yeah are opening this。

 So let me just。Copy this。And we are just reading it so the R here and then on Windows it's I think required to specifically say which encoding we are using。

 so UTF8， the standard encoding。Yeah， then we can just。Read the raw texture。

And then let's double check so we can double check that the text looks okay。 so we can see， yeah the。

Python interpreter has successfully loadedud the text here。

And we can also just double check you know how long it is， so。

I maybe recommend running this if you are running the code to check that you get approximately the same number here。

 which means you are not missing any character， so it should be about 20。

479 characters if you loaded the dataset correctly。So。

Let's now briefly introduce the concept of tokenization with regular expressions。

 which is just like a warm up。Before we use the real， let's say tick token library for tokenization。

 so we are going to use a Python regular expression and let's actually use some simpler text let's for the warm up here。

 let's use the text I just typed in here。And provide it here。

Then we can type resolve and then the regular expression and I must say that regular expressions are my weak spots。

 I'm really not that good at them， but honestly nowadays with LLMs like Chayt it's actually pretty easy to figure it out。

 So this is essentially just a regular expression that splits on whitespace characters And by the way。

 you don't have to really know what regular expressions are for the bigger context of training LLMs because we are later using a tokenizer based on Bte pair encoding。

 And I also have a from scratch implementation， it's not in the book。

 but it's in a supplementary materials that I can also maybe show you later but yeah for simplicity。

 our goal here if you remember what I mentioned earlier。

 our goal here is first to split up this text into individual tokens。

So let's do that with this regular expression and then maybe print the result and see how it looks like。

 And so yeah， we can see we have now the individual words。

 and we have white space characters and so forth。 one thing we might want to do is also to have the punctuation as separate characters。

 So for that， we would have to make a little bit of a more sophisticated regular expression。

 And like I told you， I'm not very good at regular expression。 So let me just copy and paste it here。

 So this is now a regular expression that is slightly more sophisticated So this one。😊。

Will also include the punctuation as separate tokens where before they were part of the word itself。

Okay， so this is our simplest way of， you know， tokenizing Now， as you have seen here， if I go here。

 there are actually no white space characters。In， in the output here。

 So one thing we to mimic this could be， for example。

 that we are also going to strip the white space characters。

 This is just like an optional thing we could do。 We can just get rid of the white space characters。

 So here I just have a simple list comprehension that will strip out， yeah。

 the white space characters。So you can see now that is the result without white space characters。

 it's a bit different from what you see here。😊，Because this is a sophisticated byte pair encoding algorithm。

 and I will talk more about this later。 I will share some。

 we have a dedicated section on this actually。 But so here for now。

 we are just building a very simple version of that to understand roughly yeah what we are doing here。

 like how we are tokenizing text。 doing it a bit more advanced Now， I mean。

 this is a nice way to yeah handle。😊，Simple cases。 But now imagine we have a more complicated case like that。

 So this， this will actually fail really， it doesn't really take care of special characters like。

 you know， the double dash and everything。 So we can actually make it more sophisticated。

 So I have now like。More sophisticated regular expression。 and also again， the white space stripping。

 And that does a good job of you separating words and special tokens。

 So we did a lot of work here now to yeah prepare our。

 our text by split splitting it into individual tokens and punctuation characters。

 So we tested it on this simple example。 But let's actually use this on our， yeah， on our real text。

 So for that， what we have to do now is we have to actually use our。😊，Raw text。 Well。

 raw text is what we have here。At the top， so that's our raw text。

 Let's actually see what happens when we do that。So yeahep， so we tokenized our。Raw text。

 And now let's see how many tokens we have。 So we have length of。Let me actually save this SLM。

Variable， because this is a lot of code。It's just called a pre processsed。😔，And then。

So yeah we have here 4690 tokens， so what we have done so far in section 2。

2 is we took raw text and we tokenized it and now in the next section we will be talking about converting this raw text into these socalled token IDs。



![](img/d4ac733fd952997f5b89e860e95e4d9a_35.png)

![](img/d4ac733fd952997f5b89e860e95e4d9a_36.png)

Yeah let's not talk about converting the tokens into token IDs So previously we talked about breaking down the text into individual tokens here and now in this video we are going to talk about converting the tokens here into token IDs which are socalled yeah token IDs and they are essentially unique integers so how do we do that the first step let's maybe go to section 2。

3 here the first step would be building a so-called vocabulary so the vocabulary is the unique mapping between each word that can occur and a unique integer so for example for simplicity if we have a very small data set here the quick brown fox jumps over the lazy do the first step would be breaking down the text into tokens which we have done before and now we are going to sort them alphabetically making sure we don't have duplicates in there and then we are going to assign a unique mapping here to integers so how do。

Do that in Python。So we already have the preprocessed from the previous section。

 so preprocess is all the unique tokens in in the data set and so what we can do now is we can get rid of the duplicates first so we can do set preprocessed which will get rid of the duplicates and then let's also sort them with a sorted function in Python and we can assign。

All words are variable to hold them， so let's just make sure it worked so we can see these are all the unique words。

It's a lot of words。 We can actually also look at how， how many we have， how long this list is。

 So that's about thousand。1 30 words， so it's four times smaller than pre processcessed。

 so we had a bunch of duplicates in there。 let's actually save that for later we call that the vocabulary size so how many unique words we have。

And yeah， so the vocabulary size is。Stone below 1130。 So next， let's actually build the vocabulary。

 This is actually quite simple in in this illustration for educational purposes。

 what we can do is we can for each token， assign an integer。

 a unique integer for each integer token in enumerate。😊，Oh， oops。Words。

 so what it will do is it will。yeah， iterate over all the unique words and then assign and asc sendingending order these integel labels so we can actually take a look at this。

So you can see it's yeah， essentially mapping each word to an integer here。Yeah。

 and this is essentially yeah what we are doing here， so now we have the vocabulary。😊。

So maybe going to the next figure， so the next step would be now that we have this vocabulary。

 we use this vocabulary to actually tokenize training data into token ids。

 you can see the vocabulary is in a sorted order so we have the alphabetically sorted with this mapping and now for any new text for example the training text。

 but also later on when we want to use the LLM we are going to use this vocabulary to convert any text into token IDs here。

 So basically using the vocabulary mapping， if we have the word the we would find the word the in the vocabulary and find the corresponding inteteger for example。

 So the here it's not shown because it's too long would correspond to integer 7 and then the second word brown would correspond to integer 0 and then doc would correspond to integer 1 and so forth And so this way we are going to encode the given text into these token IDs。

So let's yeah do this in Python。 So I will actually copy and paste it because otherwise it will take too long if I just type it and I will make errors because typing in front of a camera is quite different than coding in yeah silence。

 But so here what I'm going to show you is a simple tokenizer class and that's a Python class。😊。

And that does the following things。 So in it is usually yeah executed when you are instantiating a new object。

 which we will be doing later。 Let me just maybe first explain。

 and then we will create a new object here so in it is the constructor it takes a vocabulary and it defines or it will just save the vocabulary as the string to integer mapping So string to integer means that we are mapping from strings to integer representations。

 and then we also have the same thing inverted So we are here instead of having I we have S I which inverts string and integer So what it will do is。

It will yeah create this mapping from integer to string now so we have integer and string inverting this essentially Yeah。

 so here we have now two vocabularies， the regular vocabulary and the inverted vocabulary。

And then we have an encode method that takes any text and uses the regular expression from section 2。

1 sorry 2。2 and breaks down the text into token So this is what we have seen earlier。

 This is quite the long vocabulary if I scroll up so let me actually maybe comment this out。

So earlier in the previous video， we have， yeah。Broken down text into tokens。

 So we used this regular expression。 So here we are just going to reuse that regular expression from earlier and then strip out the white spaces。

 And then here， this is the interesting part。 This is where we are creating the token I。

 So we are going to use the vocabulary from here。 And for each token or string in preprocessed we are going to are converted。

 So just to show you what that means。 So if I just take， let's say。Jack here。And I pass it to my。

W up so if I have something like this。So this should give me an ID。Right， so this is essentially。

 yeah， the the token ID。 and I can also maybe just show you。Cre a reverse mapping here。

So if we want to go back。To string and type 57 this should give us the original word back so this is basically what's happening here。

 we have a vocabulary inverse vocabulary here we are just going from string to integer so string to integer means this one here we are going from string to this token ID and we do that for each token ID in the in the data set here。

And the data set is， yeah the tokenized version of the text。Yeah， and this is really it。

 And then we have a decocode method and the decocode method goes backwards。

 So here we are going to recreate a text by mapping back from integer to string。

 which is what I've just shown you。 So intege to string means that we go here from the integer back to the string。

 And I think yeah， this might be relatively yeah， I mean， complicated， maybe not。

 but it's a lot of information。 So in this case， that's actually use it。

 And I think it becomes more clear when we actually use it。 So that's simple。Unfortunately。

 I don't have auto complete here， so let me just copy it from here。

 that's actually just instantiate a new object using the vocabulary。Like this oops， not defined。

 I need to execute this cell first。 This always happens when I yeah talk and code at the same time。

 I forget things。 then let's just use some text here instead of me typing it I'm just copy and pasting it。

And so the first step is converting text into these IDs so let's do tokenizer encode and then text So this is essentially calling this encode method and then we will hopefully see that those are converted into token IDs so we can see now this would be the token ID representation for this particular text yeah and we could also go backwards so if we have these token IDs we can do tokenizer。

 decocode。And Is。 And this would correspond to this code。

 This will be converting this back into text essentially。 And yeah。

 what's nicest you can do also the round trip， which means。What we can do is let's do it like this。

Decode and then put this encoding inside here。 And this should give us the original text or something that is close to the original text。

 You can see there are a few slight differences。 For example， here。

 have there's additional white space， for example。 But overall， this works quite well。

 We have a way of yeah converting text back into。kenFrom token IDs back into text so this would be a very simple tokenizer that's not the real tokenizer that is used by GT models that's why I'm calling it simple tokenizer but I think this illustrates the concept of tokenization quite nicely how we go from text into integer presentations and now in the next video we will talk a bit about yeah special coding special tokens and how we handle those。

😊，Alright， let's not talk about adding special context tokens。

 So previously we talked about creating the so-called vocabulary from all the different tokens in the training set。

 and then we use that vocabulary to create the token Is。

 Now we are going to talk about extending this vocabulary with special tokens。 So for example。

 we might want to add depending on the tokenizer， a token for unknown words that are not in the training set。

 or for example， we could indicate when there's a end of the text by using a so-called end of text token。

 and we will talk more about this end of text token later on when we are actually pretraining and fine tuning the LLM。

 So here， though the goal is essentially to extend our simple tokenizer a little bit to handle these special tokens。

 and also wanted to just show you one shortcoming of our tokenizer。 So if I go up here。

 we defined our simple tokenizer here。😊，Based on the vocabulary。

 if I have some text now that is slightly more I would say sophisticated。

 So before we used this text here， if I have text let's say let's let's do something not super sophisticated。

 but something different like hello maybe do you like T is。I don't this。A test， for example。

 and let's try to see what our tokenizer does when we actually try to encode this。So as you can see。

 there is an  error now。 it says key arrow， hello。 and hello is a very normal word。

 So why would there be an  error。 And that reason is because the text that we processed apparently。

 So the the verdict here， apparently， it does not contain the word hello。 Now。

 if you are creating yeah， an LL M。And train it on trillions of tokens。

 the chances are that this word would be in the training set。 For example here。

 we have only this very small data set， it might not even contain simple words as hello for example。

 And by the way later on I will also tell you more about an algorithm that can naturally handle unknown words So for example。

 if the word is unknown， it will just break it down into individual characters So maybe to show you what I mean。

 So if I type just some something like this， you can see if if it does know the word。

 it will break it down into individual characters， but this is a more advanced algorithm So now how can we actually you know make our simple tokenizer slightly more sophisticated by handling unknown words。

 So what we could do is we can extend our tokens。 So if we have all tokens which word。List of the。

Pre processed text， tokens or birds。 So this would essentially recreate our yeah。

 unique tokens from the data set。 And now what we could do is we could actually extend it。 So if we。

Use。The extent method on on Python lists， we can actually add additional tokens， for example。

 we could the add this end of text token that I mentioned earlier。

Or we could also add token for unknown words。 so we can really add anything we like here。

So just extending it。 And so the difference is to what we did before is we are are creating it similar to before。

 but now we are adding tokens that are not already in the data set and then yeah we would generate the vocabulary similar to before。

 So this is the same that we used before like this token to integer。Mapping for the vocabulary。

And then yeah， let's actually take a look at the length of the vocabulary， I think before we had。

 let me scroll up a bit1130。 now we should have 100 1132 tokens that's double check。 Yep。

 so we have these two new tokens added。 and let's actually print。The first the last in this case。

 the last five entries we can do the first five， they should look similar to what we've seen before。

 So just yeah special characters， but more interestingly。

 let's actually print the last five tokens in the vocabulary and we can see we now have these two new special tokens in the vocabulary in a similar way。

 we can now modify our simple tokenizer to actually use these special tokens。

So what we have to do now is we have to essentially add a special rule to to process those。

 so I will just copy and paste it here so。We will return the string if the string is not empty and if it's in this vocabulary。

 and otherwise， if it's not in the vocabulary， So else。

 we will return unknown for this unknown token。 And this way。

 we will prevent that this modified version of our simple tokenizer crashes on words such as hello here。

 for example。Yeah， and this is all we， we do。 essentially， it's a simple modification。

 and this should actually help us to run our simple text example。 That's just。

Copy this one for simplicity。 So we are reinitializing the tokenizer。

 Now we have tokenizer version2 and we'll make a new。Code cell and then tokenizer encode。Tex。

 and this hopefully works now。 And yeah you can see we now have this unknown token。 So actually。

 when we go back， let's see what happens so。Tokenizer， decode。

Yeah you can see now it handled yeah the unknown tokens。

 This is of course not desirable if we want to regenerate the original text and later actually in the next sections。

 I will talk also about an algorithm that will make this a bit more sophisticated It's called byte pair encoding and I will explain how byte pair encoding handles unknown tokens。

Let's now talk about Bte pair encoding， which is an algorithm that will help us to take our tokenizer to the next level。

 So Bte pair encoding is an algorithm that has been around for about 30 years or so。

 but it's yeah it's very popular for implementing tokens these days。 and for example， G1 G23 and4。

 they are all using this Bte pair encoding algorithm for their tokenizer and even other companies。

 for example， meta AI for their recent Lama 3 models。

 they are using Bte pair encoding and so Bte pair encoding really helps us addressing one major shortcoming of our tokenizer。

 So if I go up again a few cells here， one of the shortcomings of our simple tokenizer was that it wasn't able to handle unknown words So for example in this case。

 we had this word hello and since hello was not represented in the training data it would raise a key error。

 And so the way we handle that。Was that we yeah replaced unknown tokens by the unknown placeholder token here so we had this special rule here to replace anything that is not contained in the vocabulary So anything that it hasn't seen during the training by these so-called unknown special tokens So what happens is for example if we have some text like this here so these unknown words get replaced by UN K placeholder tokens and this one as well but the main shortcoming of this is now to the LLM this all looks the same so the LM doesn't really know what's here and what's here because it receives the same token I for both of these cases and in many many realworl task where you have specific names or anything that we're not included in the training data the LLM wouldn't have any idea what you are talking about or what you're referring to if you have multiple of these unknown tokens in your text and so forth and yeah this is not ideal so the by pair encoding algorithm。

I a way that it can always break down any type of word into sub tokens。So to show you an example。

 let's go briefly to this tickk tokenizer app again and we will be in this video also using the Tk token app or sorry Python library in a few moments。

 but if I type some let's say some unknown word and then something like this here you can see it's actually breaking it down into sub wordss。

 So what happens here let's fix this it's even nicer。

 So what happens here is that I bet you that this is something that was not contained in the training data for G2 but nonetheless it's able to break it down into individual tokens without failing So without raising an error or without inserting a placeholder token or anything like that。

 So what happens is it's breaking down longer unknown words into known sub wordss So it has。

 for example seen something like some in its training set or unknown So these are unknown words so you can see here。

It's breaking them down successfully into individual sub tokens。

 And then if we have a string like this。 this is something that doesn't really correspond to anything in the training data。

 it would then always fall back to individual characters in this case。

 it will just use a single character as a token。 So in this way。

 it will never fail because it will always fall back to these individual characters if there's an unknown word。

 Now this is maybe a bit inefficient because now one word becomes a lot of tokens So it's not the most efficient way to encode input text if you have a lot of unknown words。

 However， it will never fail in this case。 So this is one improvement over our previous method which would just replace unknown tokens with this UNK placeholder token。

So if you are interested in the Bte pair encoding algorithm， how it works。 So open AI。

 they actually open sourced yeah the inference method for this byte pair encoding algorithm so they have this G2 GiHub repository so it should be just openI G2 and then in this folder SRC and then encoder they have the byte pair encoding implemented here to break down yeah words or input text into these sub tokens now they don't share the training method for this so they only share the code that you use when you have already trained this yeah tokenizer。

 however， if you are curious I implemented this from scratch so。

If you scroll down here in the bonus material of the book。

 So this is my repository RB LlMs dash from scratch。

 and then you go to the Spte pair encoding tokenizer from scratch link this will bring you to a notebook a Jupyter notebook where this implements the byte pair encoding step by step from scratch including training and then also at the end I have a method for loading the open AI weights into into this So this should work similarly to what open AI used for yeah for the GP2 model。

 So if you are interested in more details yeah I recommend checking this out but now that this is only optional。

 this is pretty advanced and this is also a very long notebook which is why I didn't include it in the book itself because yeah in practice the book is about LLMs and this is a whole different topic this could be actually the topic of a whole other book because it's actually quite。

So the main message here really， is that。We are going to take text unknown tokens and everything and we have now a way to break it down into individual sub tokens with this BE method and in practice we are going to use the library called T token which is an open source library from OpenmiI so the book the later chapter us will implement everything from scratch because yeah that's the title of the book build a large language model from scratch but I would consider the tokenizer not really part of the LLM itself so in this case the tokenizer here we are going to use this library from T token because it's actually also very nice and efficient and it's what most people use in practice so the reason why it's efficient for example more efficient than this implementation here this other implementation here from OpenmiI is that yeah the most expensive function calls or code is implemented in rust where rust is a different yeah programming language that is often used to implement high performance。

code and then to make it yeah easy to use people usually add a Python API around this。

 so we're going to use this library in Python， but most of the core parts are implemented in rust to make it really fast and inference。

So what we are going to do is we are going to implement sorry to import the Tik token library。

Here we go。 So the Tiktk library is yeah helping us then to use this G2 tokenizer and by the way。

 why G2 and not G3 or4， that's because later in chapter 5。

 we will be training small G2 style model And then we will also later see how we can load the pretrained weights from Opmii who shared the G2 model weights。

 Unfortunately they didn't share the G3 or G4 model weights yet。

 but the architecture of G3 is the same as two and so forth。 And in any case， so we are going to。

Use the GPPT2 tokenizer to make it compatible to the model we are going to implement later in chapter5 and so yeah we can import the TkToken library like this if you have yeah set up your Python environment as described in the first video with this requirements or text file this should automatically work if you get an import error that means you probably haven't installed the Tk token Python library so you could either use UVPIip install。

Or just Pip install Tk token to install yeah this library。

 So if you would execute this code cell here， this would install the Tk token library so but I'm commenting it out because I have it already installed And so next let me also just briefly double check which version I'm using so。

It's always a habit of mind to double check because yeah you never know if you run the notebook in a few years in the future。

 maybe if you get a different result it could be due to a different version of the library。

 so I'm using 0。9 but it should also be fine if you have an older version like 0。

7 or 6 or something like that but yeah if you get some weird results that don't really match what you expect making sure you have the correct version is never a bad idea so you could then also fix this version number like this for example。

Okay， so how are we going to use the TikTookizer now so we are going to instantiate a new tokenizer object and we are going to use the GPT2 tokenizer like I mentioned before。

 so we do get encoding and then GP2 like this and this would instantiate the GPT2 tokenizer with the full vocabulary the way it was trained in everything so this is already ready to use we don't have to train anything and then the usage is is exactly the same。

As our own simple tokenizer， this is why we went through all the work here implementing this because it helps。

 I think， illustrate how encode code and decode work like these methods。 And this。

 yeah tickk tokenizer is using exactly the same yeah， the same。APpiI。

 so you can see we are encoding this now， and then there is also。嗯。Tokenizer。Decode。Like this。

 And this gives us back the original text， which is exactly what we had before。 Now。

 let me actually show you。More advanced case where I have some copy pasted some text here。

 and let's actually。Try to encode this text So before I mentioned to you that it can handle arbitrary words。

 so it is actually able to you know break down any words into sub tokens So let's see actually what happens。

So you may notice now that actually it raises an error。

 And why is that So there is one interesting thing about the G to token as。

 And so one is that they use the so called special end of text token。

 And I think I glanced over this in the previous videos， but the。End of text token。

Is usually used if I can find the figure here。It is usually used to concatenate texts。

 let me double check。Yeah here so when you are preparing the dataset for training at LLM you usually have multiple documents and to signal to the LLM where one document ends and where the next document starts。

 you usually add this end of text token you can either add it at the beginning of the next document or at the end of the previous document that doesn't matter。

 but you usually have this end of text the delimiter to show where a new document starts so that the LLM knows okay this is a new document now it's not part of the previous document。

And this is also used in GT2， for example。And it's a special token that they used。

 but it's not by default enabled in this tokenizer。

 which is why it's complaining So what you have to do is you have to unfortunately yeah add this as a special token so you have to be very explicit here and then add this special token。

Like this。 And yeah you can see this one works now。 And so this end of text corresponds to 50256。

 which is essentially the vocabulary size of this tokenizer So the vocabulary has 50256 entries in this case。

 And so one more thing I wanted to mention is it might look like it's yeah not working well with things that is not denoted as a allowed special。

 but it would work with any other tokens so I can just you know arbitrary text here and it would work like this。

 So like we said before it can break down arbitrary text。

 It was just an exception with this end of text token and yeah and so this is in a nutshell how the byte pair encod algorithm works So it's essentially a method for breaking down arbitrary text into to sub tokens And if you are curious about more details how it's implemented。

 I highly recommend。not highly but I suggest checking out this source code I would say I would not highly recommend it at this point because it's pretty advanced and it can you know it can be a bit confusing and yeah if you like and can also check out my my implementation here where I added a few more comments and hopefully making this a bit more readable but yeah again this is advanced material I would say this would be almost topic for another book it's not really anything you have to necessarily understand for implementing an LLM the core message is we have known an algorithm that breaks down text into tokens and in the next video we will talk about implementing the data sampling。



![](img/d4ac733fd952997f5b89e860e95e4d9a_38.png)

![](img/d4ac733fd952997f5b89e860e95e4d9a_39.png)

![](img/d4ac733fd952997f5b89e860e95e4d9a_40.png)

![](img/d4ac733fd952997f5b89e860e95e4d9a_41.png)

Let's now talk about data sampling with a sliding window。

 So what that means is previously we talked about creating these subward tokens from a given text and then we converted the subtext tokens into token IDs and later we will learn how to convert them into vectors embedding vectors and then pass into the LLM Well for now the focus is released still on this part here。

 how can we do this efficiently For instance， the LLM it can't receive all the tokens all at once as input So the topic of the section is how do we provide smaller chunks of these token IDs to the LLM efficiently so that we can later train the LLM efficiently。

So let's go to section 2。6 here。 There's one more thing I wanted to mention before we go to the code examples。

 LLMs， essentially one of the hallmarks of LLMs is that they are predicting one token at a time。

 So if we have an input text for example， LLMs learn to predict one word at a time。

 if that is our input text， let's consider the first token if we pass only this token ideally the LLM should yeah predict the next token in here in the next row LLMs learn the next token is two and so forth。

 So the goal is yeah to teach the LLM to predict one word at a time。

 And this is one of the interesting things about LLm this makes them so efficient at scale in terms of being able to train them of very large dataset sets。

In traditional machine learning we usually as humans had to find ways to create labeled data so here it's actually very easy because we can use raw text and the label creates itself by just being the next token so we are just taking text we hide part of the text for example here we hide this text we provide one token as input and then the next token is the target label that the LLM learns to predict we will learn more about how this works。

 for example optimizing a loss function predicting next tokens and so forth in later chapters here the goal is to just prepare the data in a similar format so that when we pass an input to the LLM the LLM has then the next target that it can predict。

So if I go to my code here， so what we are going to do is we are going to yeah do this efficiently for our the verdict data set so just to。

Provided here again， the verdict was the short story by Edith Wharton that we downloaded earlier and what we are going to do now is we are going to use the tick token tokenizer to encode this into token Is and yeah if we do that we can see we have 5145 token Is just maybe to visualize them can see them So these are all the token Is in our text and now the goal is how can we provide them efficiently to the LLM in the form of sub chunks so you can see it's a lot of tokens and the LLM wouldn't be able yeah to pass them all so we want to。

 for example， provide chunks of four for because yeah it's nice and small and fits into this Jupyter lab and we visualize it and I can make nice figures but in practice the chunks are usually much larger they usually thousand4008000 tokens at a time depending on the LLM。

Here in the case of GT2， I think it was 1024 tokens that were used at a time during pretraining。

 we are in this particular notebook only using for visualization purposes just so that I can show you some things more efficiently in a figure。

So yeah， that is what I wanted to say here and we are also going to use a particular subset and we are truncating the first 50 tokens just to have some nicer examples and some nicer text。

 but this is just like an implementation detail to make this visually a bit nicer。😊，Now。

 what I wanted to show you now is the way we yeah prepare the x， the inputs and the y， the targets。

 I kind of showed it to you here already that we are concerned always with next the next target token here。

we are creating a data set here where the targets are the inputs shifted by one position。

 which then helps us to have the targets as the next token to the LLM so for instance here what I'm doing is I have this sample text so that sample text is it should be about 5000 something。

Oops。Tokens， so 5095 tokens because yeah I just truncated some tokens。 So you have 5095 tokens。

And we have a context size of four。 So we are only considering four tokens。

 So here we are going to take the first four tokens and then。

We shifted by one position so that the targets are， yeah shifted by one position。

 So you can see it here in the output。 We have the inputs。

 and then the targets are shifted by one position， so。If I show it like this。

 this is how it would look like well it's a bit hard to read So I inserted this white space so you can see where the overlaps are here。

 so you can see those three tokens overlap and this would be the next token and this would be the previous token that is not presented in the in the targets。

 So if the LLM receives this token it's supposed to predict this token if the LLM receives those tokens it's supposed to predict this token。

 if the LLM perceives those tokens， it should predict this one and if it receives those it should predict this one and so forth。

 So that's the whole idea here and maybe to make this a bit more clear what I've just shown you visually So here's some other code example。

Wwhichch is exactly doing what I just showed you where it's showing the next token and since this might be a bit abstract with these numbers we could also just use our tokenizer for example。

 let me copy this so it's easier than just retyping it。

So we can use our tokenizer to decode the token IDs back into yeah text and do this for both the targets and the input context。

 And so this is the same oops made a mistake I probably forgot。

Close parenthsesis so you can see what it would look like so we are always predicting the next word in the sentence。

And so to make this really efficient， we are going to use Pytorch where Pytorch is a very popular deep learning framework。

 it's probably the most widely used deep learning framework today。

And so we're going to import this and。Use the data laer and data classes from there because they implemented this very efficiently and we're going to reuse these parts because they're not really part of the LLM we are still talking about setting up the data and it would be a bit know tedious to reinvent the wheel and write our own data laers and so forth and so for that we are going to use Pytorch and so Pytorch is import it as torch even though the library is called Pytorch it's just a convention we have to remember and if you followed the video in the first chapter I showed you some setup tutorial if you followed this and install the requirements to text this should already work in case it doesn't work it means you don't have Pytorch installed and so。

One way to install it would be U Pip install or Pip install depending on how your system is set up and just typing this command and it should automatically get a good version for your computer however。

 if you want to be more specific for example you can go to pyth。

 org and on this website they have like this install a menu that has different commands for different computers So for example I'm running this on a Mac with Pip and then it would yeah give me that this command if you are on Linux by default here this would be the CPU code。

 it would be a bit different if you have a GPU。

![](img/d4ac733fd952997f5b89e860e95e4d9a_43.png)

By default， if you type a Pip installed torch it would come with KUuda 12。4 libraries。

 so it would support the GPU with Kuda 12。4 but if you want a specific version you can also change it and there are different URL and by the time you are watching it that might be a whole new set of kuda versions so this is really specific in terms of what GPU drivers you support but you know by default you can also just do PIip installed torch and it should technically work。

Now。

![](img/d4ac733fd952997f5b89e860e95e4d9a_45.png)

Back to this one here， I'm also just double checking which version I'm using here。

So here I we using version 2。6 and I should say when I started writing this book it was 2。

0 because that was the most recent version two years ago when I started writing the book but I tested the book on all subsequent subsequent versions of Pytorch and I couldn't see any difference in any of the code on the GitHub repository I also have automated tests so each time a new Pytorch version comes out I'm just double checking it still works and so far I haven't seen any difference in Pytorch that would make any of the code difference in this case you can feel free to also use older up version of Pytorch for example。

 2。02。12。234 and5 it should work equally fine however。

 if you notice anything that doesn't work for example。The results look different。

 You could just try also to install this specific version of Pythtorch by doing Pip install。

Trch and then 2。6 to 0。 And so this would then install this specific version of Pytorch I'm using right now at the moment。

 Okay， so this was a little detour， maybe one more thing I wanted to mention is if youre new to Pytorch。

 It's essentially a deep learning framework。 it's very relatively comprehensive。

 It has a lot of things。 but we are only going to use a subset here in this book。

 it's essentially more of a linear algebra library with a few deep learning convenience functions。

 there are whole courses and books about Pytorch， if you want to learn about it。 But if。

 if you want to learn about it efficiently， I also have appendix a here。

 So I've been using Pytorch I would say since 2018 for seven years now。

 And I've taught many Pytorch workshops。 and yeah I wrote another book about Pytorch and so forth。

 So what I want to say here is over the years。I used Pytorch quite a lot and I was thinking really hard what are actually the parts you need to know for this book so and based on that I compiled this appendix A which is essentially a book chapter of 40 pages approximately that just go over the essentials that you need for yeah basic LLM training and development where this should get you up to speed relatively quickly of course if you're curious I recommend yeah considering a whole course or book on Pytororch at some point but if you just want to get up to speed with Pytororch for this particular yeah book。



![](img/d4ac733fd952997f5b89e860e95e4d9a_47.png)

![](img/d4ac733fd952997f5b89e860e95e4d9a_48.png)

Try to read appendix A and maybe it's already sufficient it might be a steeper learning curve because I'm trying to keep things efficient and compact。

 but maybe this is all you need at that time to really get up to speed so you don't let's say go on a detour for a few months to try to learn Pytorch and then yeah yeah then you get maybe frustrated or get bored so I would suggest maybe trying appendix A and maybe it's already sufficient to get you up to speed here。

Now back to the data loading， so we talked about Pytorch and importing Pytorch。

 let's actually go back to section 2。6 data sampling with a sliding window。

So we talked about the target word predicting the next word。

 and so now we are going to prepare the data set accordingly。

 so we are going to take the input data and we are creating these chunks and I mentioned before we're using a chunk size of four or context size of four for visualization purposes so it nicely fits into this figure and so forth。

 but in reality these are usually larger like 1，024 in the case of the GPT2 model or newer models use 8。

0016，000 tokens in each row but it would be hard of course to visualize here。

And so as you can see the one box here， the left box that's the input X that we are creating and then the targets are shifted by one position as you can see here。

 it's the same idea what I showed you earlier， we are just creating inputs and targets simultaneously from this text so that we can feed both to the LLM later when we are training the LLM。

So let me actually do this in code and for this we are going to use a Pytorch data set class。

And so the reason why using a Pyrch dataset class is it will allow us to use the Pythrch data loaders later。

 and they are essentially a very nice and efficient way to create batches and to shuffle the data and to use multiple background processes to process the data faster。

 it has a lot of convenience added to it So how a data looks like is we have a constructor here。

 we are setting them to empty lists。And we are going to tokenize the text。

 so text is the input text we' are going to pass and so we get the token IDs and here this is the part where we are creating these socalled chunks So these chunks are these two chunks basically。

And instead of I should go back maybe one more time。

 instead of just creating one chunk for the inputs and targets。

 we are doing this for the whole dataset， so we are storing these chunks here。

 we are adding them here for the inputs and for the targets so we are appending them to these list we creating a lists we created earlier and it's the same concept as before we are sliding over the input dataset and then targets are shifted here by one position。

So what we are going to do is we are taking this left box and we are going to slide it over the input so you can see the first row is in the heart off and then when we slide it over the next one is the city stood the and then old library and so forth so it's yeah sliding it over by one position。

And it's if you have a very large data set， it's maybe not the way to do it because you can't store 15 trillion tokens in memory。

 so this would run out of memory but if you have just a few books。

 a few gigabtes or megaytes of data I mean if you have I don't know1 thousand books or something like this。

 this would conveniently fit so you don't have to worry about it and over optimizeim at this point。

 there are a few more advanced ways and tools if you are really training LLMs on trillions of tokens but for here educational purposes we are keeping things relatively simple and readable because this will this is the basic approach and yeah so to understand also how things work under the hood。

Now we have this data set now and I mentioned the data lata that we want to use。

 so let me sort of typing all the code just insert it below。

So the data loader is created here and I have a function I'm defining that returns this data loader and so here we are defining the text。

 we can set a batch size a max length of each context length so before we set four is our length here we can also this is just the default parameter or we can overwride it later we set the stride it's by how many positions we are moving the box we will get back to that in a few moments whether we want to shuffle the data set whether we want to drop the last batch or not and this is actually an interesting one This is really to avoid loss spikes So for example if we have a data set let's say example one。

Example two and so forth， if we have a data set like that， let me。Justs。Do it like this。

And suppose we have a batch size of two What the data loader will do is it will divide the data set into batch sizes of two。

 but if the data size is not divisible by the batch size you often end up with very small batches at the end the last batch because it's the remainder and this often results in loss spikes like unstable training so it's actually a good idea to always remove the last batch if you do multiple epoch training you also don't have to worry about missing certain data points by removing them。

 but also in general usually data sets are so large that you know if you don't use the last batch doesn't really matter so it's usually a good idea to have batches of the same size so you don't have these instabilities during training this is why we are why I'm recommending dropping the last batch always。

And then nu workers is for using multiple background processes。

 I have it here set to zero because I'm executing this in a notebook and in some cases this can be yeah might not work because notebooks are a bit more restricted than Python scripts in terms of spawning multiple subprocesses or if you're using Windows I think Windows generally has some problems with multiple background processes in Python so this is just like a safe choice。

 but yeah you can try also to set it to a larger number for example。

 but yeah for these purposes in a notebook this should be fine to set it to zero。

And yeah this was very conceptual， a few more things here， we are initializing the tokenizer。

 this is the tickk token tokenizer we talked about earlier。

 then we are creating the data set that is the data we have up here and we are creating it with yeah text and text will be our training dataset and here is where we are creating the data laer using the settings I defined earlier。

And we are returning it。 So all very， very， I would say conceptual。

 So let's actually see it in action。 And for that， we are going to use the verdict again。

 which is our short story that we download earlier， the short story by Edith Watton。😊，R text。😔。

So this is how it looks like we have seen it earlier and now we are going to pass it to our data set and data load。

 So let me just because otherwise it will end up a very long video。

 let me just copy and paste the code here， we are going to start with a batch size of one and a context length of one and a strip of one。

And so the batch size is how many samples are in each batch。

 essentially the max length is our context length， it's how long the context here is like the size of the box。

 how many tokens are in there。And then the stride is by how many places we are moving it。

 so for simplicity I will show you stride of one and then we will change it so if this is unclear。

Wait for a few moments we will we will get to it and whether we shuffle the data or not。

 and then we are iterating here just for demonstration purposes over the data set manually and later I will show you a different way to do that。

😊，So here we are creating an iteration object an it object and then we are taking the next sample from our data set So when we are executing this we can see the the next batch here So this is the first input it only has yeah a size of one。

And this is then the targets， so you can see the targets are shifted by one position。

So and then let's draw another batch。Now what you can see is that the targets here become those inputs。

 So the the first one is always the inputs。 the second one is always the targets because that's how we set up our data set。

 So the first is the inputs。 The second is the targets。Now you can see。

This is something where it's maybe not ideal because when we have this input and then the second iteration is this input。

 there is an overlap。 So these tokens are the same。 And if you do it like this。

 the LLM sees certain tokens many， many times and then it's kind of leading to overfitting。

 So what's actually better is to increase the stride by four。 So if we do that。

You can see each of the tokens are unique so you can see they are not overlapping anymore。

 And so what it does is it's moving this box by strip of four by four positions So one to34 moving it by four positions So we are at the city stood the and you can see this is what's shown here in the second row。

 The reason why I showed you just a stride of one was so you can see that this actually works and it's not missing any data because you can see。

This one picks up right here if we have a stride of one， I thought this might be more intuitive。

 but if it is confusing， don't worry about it， just go to the Str of four and then you have exactly what you can see here in the figure。

Now this is for a batch size of one when we are training deep neural networks it's usually efficient to use a larger batch size so what we can do is we can use the batch size of8 so I'm just showing you a same thing here instead of batch size of one I have a batch size of eight max length of four and a strip of four and then yeah some labeling so it's a bit more clear and yeah you can see now we have the inputs here and the targets and this is similar to what we are seeing here where we have multiple rows where each row is one training example and so we have a batch size of1。

23，4，5，6，7，8 and then the corresponding targets。Yeah。

 and this is really how we implement this data order and then。

Later we can also iterate over it more efficiently， so what this is a topic for later。

 I just wanted to set up this data order so that we have one way later on to load the data into the LLM efficiently。



![](img/d4ac733fd952997f5b89e860e95e4d9a_50.png)

![](img/d4ac733fd952997f5b89e860e95e4d9a_51.png)

We talked a lot about creating token Is， but now let's take it to the next step and talk about creating token embeddings。

 So if I go back to an earlier figure from section 2。2。

 we look at this figure where I showed you that input text gets converted into tokenized text and the tokenized text gets converted to token Is。

 Now the next step is creating these token embeddings from the token Is。

 So essentially taking an I an integer value and converting it to an embedding vector and so this embedding vector contains real numbers like a floating point numbers that can then be optimized。

So here to show you how it works， we are going to use some token ID as an example just like。

I a Pyto tensor。So that it is a bit more easy to see what's going on。

 So let's do torch tensor and then insert those。 And I should say these are relatively large numbers So let's actually use yeah。

 some smaller ones。 So we can have niceSA visualization。 So these are just like。

Some words or tokens in our input。 So we have this input tensor now。

 And then the next step would be creating a so called embedding layer， usually this embedding layer。

Is part of the LLM itself。We will revisit this many times then later in this book。

 but this would be a standalone embedding layer and there's usually something called the vocabulary size。

 so this is the size of the tokenizer， the vocabulary tokenizer。And then the output dimension。

 So this is the vector embedding size。 So the vocabulary size is in our case for the tickk token tokenizer。

 it's 550257。Sorry， that is probably not the correct number。 Let me double check actually， tokenizer。

One way if you forget like me what the name of the vocabulary is， you can use in Python this deer。

And it should actually show you。 So N will cap。So if I go up here。😔，Type in roll cap。

 and then redo the length。You can see os， let's。Not a list。 It's just an integer。

 You can see it has 50257 unique tokens。 So this would be one argument for our embedding layer。

 So it supports all these different tokens。 And the other one would be the output dimension。

 So this would be the desired size for these vectors。

 We will actually use the original G embedding size later on for simplicity。

 Let's actually use simpler and smaller values。 So it's then easier to visualize。

 So let me use for cap size6 and output dimension。Let me just copy it。😔。

Let's do three because three is also what we are seeing here， like three little boxes per vector。

 So we have a very small example that is hopefully easy to see and then。

One more thing is I'm adding a random seat here。Why am I doing that？

 It's because this is a neural network layer with random weights and so the random weights are different each time you instantiate a new layer。

 And so I just want to make sure you get the same results that I do so I' am initializing this random seat and by the way。

 if random seats are something you are not familiar with let me know I also have a nice video on random seats I can share with you。

 But yeah so this is now this embedding layer and the embedding layer。Has a weight matrix。

Wait and so this is something that is later optimized during the neural network training like the LLM training and yeah they are called weight parametersus or parametersus and these are things that are going to be adjusted and by the way if you are familiar already with linear layers or matrix multiplications and everything an embedding layer is just an implementation detail to make a certain lookup easier or more efficient this is more advanced you don't have to read this if you're not familiar with this。

 but for those who are curious。I do actually have some bonus material here。

Where it's about understanding the difference between。One moment， the difference between。

Embbedding layers and linear layers。 So if you're curious how this relates to matrix multiplications and linear layers。

 it's like a short notebook for those who are curious。 But if you are not familiar with it。

 don't worry about it， I will try to explain it in a more， let's say intuitive sense。

 So let me show you something。 So if I do embedding layer。And I call it on。

 let's say this input here。 Let's just pick one of these numbers torch tensor。

 Let's make a smaller tensor and use。Let's say the three from here。

Let's see what happens So you can see it's pulling out a vector here So there's a tensor of three different numbers。

 And if you have a sharp I you might notice it's actually this row here from this embedding matrix。

 So if we are typing three herey Python is a zero indexed so it's0123。

 it's giving us this vector from this matrix and similarly if I go here and I do let's use the first one and I do this one you can see this one。

Its the first sorry， not quite the third row， sorry，0，1，2， because that's the number  two。

 and this is yeah the index 2 corresponding to this row。 and similarly。

 if I now use the whole input Is。I'm pulling out values from this matrix， so。

I probably should show them here for reference。 So the first one， that's the two。

 it corresponds to 0，1，2 to this one here。 The second one corresponds to this three。

 So this would be this row here， the five。This one。0，1，2，3，4，5。 and so forth。

 So we are essentially when we are calling this embedding layer on the input as。

 we are pulling out vectors from this matrix and this matrix。

Technically has the size of our tokenizer。 so I can just show you this example， tokenizer dot N。

Wcap right So in this case this might be a very large one。

 Should I print it maybe let's try and see what happens。 It's actually dotting it out。 but yeah。

 this would be then 50257 rows essentially。 And yeah。

 this is essentially the embedding there that is used to convert the token Is here into these vectors and this is usually part of the LLM。

 And yeah， these numbers I mentioned before they are random。 So if I actually comment this out。

You might see。These numbers change because the weight matrix yeah。

 the weight matrix changes and so usually what we want to do is we want to start with small random numbers。

 It doesn't really matter what these numbers are， but later on during the training。

 these numbers get optimized in a sense that the LLM。Is optimized end to end to produce yeah。

 the desired text to the next word in the training text。

 And so don't worry about why these numbers are random yet because they are not trained yet。

 they are just starting values。 We are going to train them later in Chapt 5。 But now yeah。

 you have a hopefully good understanding what an embedding is。 So an embedding is。

A vector from this embedding matrix that gets later trained。



![](img/d4ac733fd952997f5b89e860e95e4d9a_53.png)

。

![](img/d4ac733fd952997f5b89e860e95e4d9a_55.png)

So now that we understand word embeddings let's take it a step further and add positional information I will tell you in a few moments what the positional information means。

 but yet just to recap we had input text， we tokenized the input text。

 created token IDs and then the previous section was focused on creating these so-called token embeddings and we only had a very small toy example and then just to use the actual sizes for our tokenizer we mentioned our tokenizer has 50。

000257 words。And so we pass this webab size to our embedding layer to create it in this size and now we also scale this a little bit up because before you we had like output dimension of123 tokens。

 which is just for toy example now we are increasing it to 256 which is what we are going to use to train the LLM later。

 it's a more realistic size GBT2 was originally trained with output dimension of I think 024 I'm not quite sure I would have to double check but yeah this would be something that works also well on a small computer like a laptop for example。

 you can always you know try larger values if your computer supports it。

 but I think this should be supported on most hardware for demonstration purposes。

 but also to make it a bit more realistic than having an embedding size of just three dimensions so we have now 256 dimensions。

So if we do that， so we have our embedding matrix that has 50，000 rows and about 200 columns。

 so that's our weight matrix similar to what we did before。Now， taking it a step further。

 we had also the data order。 How does it now come together with these embeddings。Previously。

 we created these token ideas， if I just。Show you this， it's the same that we've covered earlier。

 so we have a data laer that creates patches of size 8 with a max length of4。

 so four token IDs per training example and then we have eight examples。

And so now how does it actually relate to the token embedding that we have seen in the previous section。

 So what we do now is we actually convert these token ideas into these embedding vectors。

 So if I do that what I showed you earlier is if I take this and I type。Input Is。

 it would create a sample vectors for the simple input Is that we talked about earlier。

 but now we are going to use actually the data batch here， so this would be the data batch。

That we convert。 And that's maybe called this token。Andbeddings。

And let's just see what happens and let's actually look at the size of the output here。

So you can see now we have still the batch size of 8。 So it's now a three dimensional tensor。

 and the numbers correspond to the batch size。 So we have 1，2，3，4，5，6，7，8 rows，8 examples。

 Each example has four tokens， like one to。Whoops one， two， three， four。

But now it's not just the token ID。 Each one of those is actually a 256 dimensional vector。

 So here each token ID gets converted to a three dimensional vector。

 Now it's 256 dimensional vector it's hard to visualize vectors in 256 dimensions。

 but we can actually maybe print one of those out。 So if we take a look at the first one first batch first token。

 this should give us yeah the。The vector， the 256 dimensional vector corresponding to the first token in the first batch。

 basically this one。Okay， so now we converted token Is into。Token embeddings。

 the next step is adding positional information so。Let me see if I have a nice figure for this。

So previously what we've done is we pulled out these embedding vectors from the weight matrix for each input example and so I previously chose an input that was yeah I would say relatively nice for explanation purposes where each output row looked different so we had f jumps over dock these token IDs corresponding to an example input like this and then we pulled out these embedding vectors corresponding to the token IDs from this weight matrix now what happens if we have the same token ID for example Fox jumps over Fox So here this token index 2 is the third row in the weight matrix and so we get as the result this row here。

 but since in the last token ID we have the same the same word the same token ID。

It has the same vector。 I mean， it makes sense， right， we are looking up the position here。

 We are pulling out the vector and create the output like that。 Now， this is fine。 It would work。

 but we could actually add some more information to it。 So to provide more information to the L M。

 depending on where。This word is located in the input。

 We can create socalled positional embedding information。 There are different ways you can do that。

 So G2 used a very simple way。 it used the second embedding layer。 There are nowadays other ways。

 for example， using rotational positional embeddings If you're curious about those in the bonus material on my Github repository I implemented also Lama 3。

2 from scratch。 it's more advanced and more complicated and it's not as nicely described as in the book but they use something called rope embeddings that I also implemented here。

 but G is yeah fortunately much simpler in this case with the embeddings。

 it's using simply a second embedding layer。 So let me actually show you how that would work。

So we are using the same embedding class we used before， but now we have an token embedding layer。

 in addition， we have now a position embedding layer where we add positional information。

 So the goal will be maybe I have a figure yeah I do have a figure on that if we have input embeddings like this。

 the goal is to have a second set of values that we add here So position embeddings that we add we have sorry。

Token embeddings， so to step through this figure more slowly。

 I chose the same token embeddings for each example here just to keep things simple。

 So if we have just input that consists of the same word like Fox Foxox Foxox Fox， for example。

 the token embeddings would be the same in all the cases but then we add positional information on top of that so that the actual input embeddings look different depending on on where it's located Now I'm using these very nice numbers where it's easy to read those numbers in reality these are all starting with random numbers so it doesn't look quite as nice。

 but these numbers， the position embedding numbers。

 they also get optimized automatically later during the LLM training so they are random numbers to start with and later they will get optimized similar to the token embeddings。

So here yeah I'm creating a second position embedding layer essentially and then what I'm doing so here is the max length so the max length is yeah how many inputs are supported in this case we only have four right so we had a max length of four one。

 two，3，4 it can only support for input tokens in practice this is a much bigger layer so for simplicity we just keep it small。

Poil visualization purposes and just simplicity later when we train the LLM。

 we will actually use much larger values and then what we can do is we can use torch a range。😊。

So a range is。Creating in sequentialial order values here， 0，1，2， and3。So 0123 is just a tensor。

 it's a placeholder tensor for the position position  zero， position one2 and3。

 and we have this position embedding。Mattrix， and it's a similar matrix to what we had before。Oops。

And then， when we are calling。This with our a range。What it will do。

 it will just pull out the values like the in sequential order here。So you can see it here。

 So it's just getting me the values here。 And that is all that is really happening in in this positional embedding layer。

 And then what we do is。We add them on top of each other， so maybe to go before I execute this。

This one has shape 8 for 2056。And this one should have the same shape so we can then add them to each other。

 I have not executed this。Right here so I'm sorry， this is actually only for 256 because how Pytch work I mean for efficiency。

 we don't need to duplicate this over the batch dimension because this one will be added to each batch separately so。

What happens is essentially that。When we have something like this。

 the input embedding has the same size as the sorry the token embedding has the same dimension as the position embeddings and then the input embedding will also have the same dimension。

 So here there the concept is called broadcasting and pytorch so。

Let me maybe show it to you like this so。And we do this。

We can add these values together so this is the first example in the training set and then our position embedding vector and this would be essentially similar to doing this except now we are doing it for all the exampless in the batch but the first the first example maybe you can see it here should be similar so you can see this one is similar to this one。

 I mean this is like a rounding thing not a rounding thing different。Print representation。

 but this row is the same as this row essentially and so forth。

 So this is just generalizing it over the whole patch dimension。Oops。

 me just clean this up a bit and then。When I add them together， like before。

 the shape should be the same as before。 So we are just adding this additional。

 yeah position information to it。 And so with that， we now have。



![](img/d4ac733fd952997f5b89e860e95e4d9a_57.png)

Covered。

![](img/d4ac733fd952997f5b89e860e95e4d9a_59.png)

The whole input pipeline。 So we have input text that we break down into tokenized text。

 Then we convert it into token Is。 Then we create these token embeddings with our token embedding layer we create the position embeddings。

 Add them together to get the input embeddings。 And so this is all we need to know for now for the data preparation step。

 Next， let's actually tackle the inside of the G like decoder only transformer。

 So what is actually inside the model。 One more thing I should say。

And bendning layers are technically part of the GPT model as we will see later。

 I just draw them outside here because it's a bit easier to talk about it since we already talked about the data loader。

 but yeah in the next in the next chapter we will talk more about the attention mechanism that is inside of a GPT model so I hope this was useful and I hope I will see you in the next video。



![](img/d4ac733fd952997f5b89e860e95e4d9a_61.png)

![](img/d4ac733fd952997f5b89e860e95e4d9a_62.png)