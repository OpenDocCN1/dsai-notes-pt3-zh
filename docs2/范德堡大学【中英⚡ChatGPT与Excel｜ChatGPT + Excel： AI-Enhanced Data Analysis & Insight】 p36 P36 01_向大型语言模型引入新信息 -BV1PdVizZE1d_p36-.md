# 范德堡大学【中英⚡ChatGPT与Excel｜ChatGPT + Excel： AI-Enhanced Data Analysis & Insight】 p36 P36 01_向大型语言模型引入新信息 -BV1PdVizZE1d_p36-

One of the most important things we can do in a prompt is provide the large language model with information that it doesn't have access to。

So large language models are going to be trained up to some point and then there's going to be a cutoff and they don't know what's happened after that cutoff In addition they don't know things that aren't in their training set so it may have trained on a lot of data but it may not have access to data sources that you want to use so if you're a business for example。

 there's probably lots of private data sources that you would like to reason about。

You have your own documents， you have your own databases。

 you have all kinds of things that you would like to pull information in from in order to reason about。

 so how do you do that if the large language model wasn't trained with that information Well to illustrate how do you do this。

 I'm going to go back to an example that I provided earlier when I was talking about randomness。

So I'm going to go back and I'm going to ask a question that I asked earlier。

 which is how many birds are outside my house？Now， the large language model wasn't trained on。

Information about birds outside my house it has no idea where my house is。

 it's lacking information that it needs in order to reason。

 so it tells us as an aI language model I don't have the ability to perceive the physical world so I'm unable to know what's happening outside your house。

So how do we solve this problem， Well we give it information it needs in order to perform its reasoning。

And how do we do that， We just put it into the prompt。

 So anytime we want to go and introduce new information to the large language model that it didn't have access to when it was trained。

 All we have to do is put it into the prompt。 So here's where I'm going to do right here。

 I'm going to say historical observations of average birds outside my house on a random day。

 And then I'm going to give it some data。 I'm going to say January was 120 birds on a random day。

 February was 150 birds。 March was 210 birds。 April was 408 birds。 It's March。

 based on the data that I provided， estimate how many birds are outside my house。 And now you see。

 I've done something。😊，I've given it information that it didn't have access to before。

 It couldn't look outside my house， didn't know where my house was。

 It tried to suggest ways that I could get there， but it didn't have the fundamental data that it needed。

 And that's really what it was trying to tell me was like， hey， I can't see you outside your house。

 I don't have that data。 I can't help you。 So all we have to do is up front in the prompt。

 we give it the data。AndNow you can imagine you can do this with anything。

 you could take documents if you have private documents that you want to reason about now， first。

 make sure that you are okay sending that data to whoever you're using their large language model or if you have some large language model running locally。

 but if you have documents that you're okay sending， you could take the text of those documents。

 and put it into the start of the prompt and say here's the information you to know Now。

 here's my question about that information。 So you can use the prompt to introduce information。

 I really want to emphasize this because。A lot of what's going to be developed around large language models is going to be taking new information sources。

 information about your travel， your account with some company， you know， some。

 some other document that you need and putting it into a prompt for a large language models so that it can reason about it。

 More than likely， lots of large language models are going to be seen your information in the future。

 And this is how they're going to take is they're going to take information that's going to be aggregated into a prompt of some kind。

 and there's going be questions asked or formatting or other things done。

 So when I go through and I provide historical observations of the average birds。

 now it can go and answer。 So now it goes and it says， well。嗯。You know。

 based on the historical observations， you provided the average number of birds observed outside your house in March is 210。

 So before it said， hey， there's no way I can answer it。 Now， it still， you know。

 provides additional language around this trying to you know， give some bounds on its answer。

 but it's given us reasoning now， based on the data we provided。 And we can take it further。

 And I also want to just kind of point out an important thing as。

We always want to provide it enough information to reason effectively。

And so it can't see what's around us， it can't see the context。

 so it's really important that we provided enough information to make sound decisions so for example。

 if I have some hidden assumptions that are really important to know it needs to get those in the prompt in addition to the data like numbers。

 it needs to know the rules of the game， special things， whatever's important for reasoning。

 it could be not only the data， but it could be all kinds of rules that are sort of built into how my organization works or how my life works or whatever it is that it needs to know about。

So I'm going to give you an example。 I'm going to change up this prompt。

 I'm going to say my house is covered by a glass dome。 No animals can go in or out。

 All animals live forever inside the glass dome。 Now。

 this is an assumption that this is something that if the language model doesn't know this。

 there's no way it will be able to accurately predict。 But with this assumption now。

 it completely changes the game un reasonsoning because it sort of makes it so that it's clear。😊。

Some hidden fundamental rules。 And then I go and I give it the same data， but I've changed it up。

 I've said it's always the same number of birds。 And then I ask。How based on that data。

 estimate how many birds are outside my house。 And it says based on the new information you provided appears that the total number of birds outside your house remains constant over time。

 It then goes on and says， you mentioned that all animals live forever inside the glass dome。

 given these conditions the total number of birds will remain the same throughout the year。

 And it gives 120 is the answer in multiple places。 Now， one important thing about this， right。

m giving it information that would not align with what it was trained on。 Anims don't live forever。

 We don't have glass domes over our house。 You know， there's not going to always be the exact number。

 probably in and out， you know， or the inability for things to leave or come like we're not going to have these sort of weird rules that I put in place。

And so if we just relied on it to reason without them。

 it's not going to necessarily get the right answer。

 so if we have these things that are different from the way things are normally done。

 we have to introduce them as new information and the prompt so all of this information up here at the top。

This is me putting new information into the large language model， we don't go and retrain。

 we don't go and you know do some weird thing behind the scenes。

 we just put it into the prompt and then we ask our question or we ask for our output or give it the instruction that we're looking for。

Now if you think about how search engines are probably going to work in the future as they're going to go in search。

 put documents back together， put them into a prompt to the large language model。

 and then give your sort of original question and then answer based on the questions a lot of new applications are going to be based on going and searching databases for possibly relevant documents or bits of information。

 putting them together into the prompt and then asking the question or asking for the output So an important piece of this is going to be pulling in information in order to put it in the prompt and what we're doing is we are introducing new or new information into the large language model。

 we're doing it by putting it directly into the prompt and this is one of the things you'll always want to do whenever you want to reason on new information that is not something that the large language model would have been trained on。

