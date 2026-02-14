# 吴恩达《LLM应用程序的质量和安全性》《Quality and Safety for LLM Applications》中英字幕 - P2：01_Overview.zh - GPT中英字幕课程资源 - BV1Sa4y1S7Y4

In this lesson， I'll introduce the data set of LLM prompts and responses that we'll use throughout the course。

 You'll detect issues such as data leakage， prompt injections and hallucinations with techniques that well explore in greater detail in later lessons。

 Let's take a look。

![](img/54bcd02b89e9efb5f56167fe92fbf95a_1.png)

![](img/54bcd02b89e9efb5f56167fe92fbf95a_2.png)

So what are we doing here。We're going to develop metrics to help us look for problematic prompts or responses in our LLM application data。

So it's almost like your professional flycatcher。 And you're trying to find the right net to catch different types of flies or bugs。

 Some of those metrics are to be very simple， starting from scratch。

 because even those are used in practice， but will also recreate some of the state of the art metrics in later lessons that have been discovered in the last year or so。

We'll use all of them to find rows in our data that contain issues and then evaluate them to make sure we've captured the phenomena that we're looking for we'll start with some setup。

 we'll import a helper module that I've created to give us some visualization and data exploration tools that we can use as well as evaluation of our metrics。

Next， we'll import pandas。I've created a data set with user prompts and LLM responses and labeled them as normal or having issues such as refusals。

 jail breaks， hallucinations， toxicity， or data leakage。

You'll notice that chats is in the folder above the current one we're in。

Let's look at a couple of rows from our data。You'll notice the dataset set has a prompt in a response column。

 These are prompts and responses collected from N LLM， particularly Open AIs G 3。5 Tbo。

We'll use these for our evaluation。 The data set isn't representative。

 They'll have a lot of these special cases that we're looking for because we can't see the full prompts and responses for some of the text。

 We'll use a pandas setting to display the full column with。Now we can see the full text。

We'll use Ylogs and open source data logging Python library made to capture machine learning data。

 Let's import it。In order to see visualizations together， we'll call Y dota。

The parameter is just so you don't have to enter a username and password For metrics specific to text and L Lms。

 we've released the open source la kit package that runs on top of whylogs。

 Both la kit and whylogs use a schema object that defines which columns to summarize and which metrics to calculate。

We'll call this one LLM schema。LLM metrics use a number of language models。

 so we'll see those download。So now let's logger data using our LLM schema。

So we use the Y dot log command。The first thing we want to pass in is our data。

So chats are Panda's data frame here。The next thing we want to do is give it a name。

So I'll call this LLM chats dataset set。And finally， we want to pass in that schema。スmaい。

Once the data is logged， we get a nice link to click and see the visualization and we can confirm that we have 68 rows of data。



![](img/54bcd02b89e9efb5f56167fe92fbf95a_4.png)

This is the Insights and Profiles page where we can see a number of metrics that automatically get collected with the LLM metrics setting。



![](img/54bcd02b89e9efb5f56167fe92fbf95a_6.png)

When we click on show Ins， we can see some helpful tips to understand our data better。



![](img/54bcd02b89e9efb5f56167fe92fbf95a_8.png)

For example， we see that we have at least one negative sentiment prompt。

And that we have pattern matches in our data set that relate to often data leakage。

 such as mailing addresses。

![](img/54bcd02b89e9efb5f56167fe92fbf95a_10.png)

So at a high level， a hallucination is just an LLM's response that is either inaccurate or irrelevant。

You may be familiar with cases where L L M's responses are factually inaccurate。

 but even if the answer is correct， it may be irrelevant。 For example。

 if you ask an L L M for a cookie recipe and I give you a recipe for a birthday cake。 that's correct。

 That's also a hallucination。 I irrelevant responses happen when you're asking the L L M something it doesn't know the answer to。

 Ki of like when I was a kid taking the exams in school。 Sometimes when I forgot to study。

 I'd write long responses to the question with whatever I remembered from studying。

 even if it wasn't directly answering the question。

Another quality of a hallucination is that often they look realistic。

 If an L L M outputs a bunch of nonsensical text， it's pretty uncommon to call that a hallucination。

 A hallucination looks readable and coherent and looks like it could be a valid response to the prompt。

 Hallucinations are really interesting because they're hard to measure。

 And there's many different ways people have proposed to measure them。

 We're only going to look at too in this course。😊，Right now， let's look at prompt response relevance。

 A common way for practitioners to measure relevance is by looking at how similar the response from an L L M is to the prompt it was given。

 We use the cosine similarity of the sentence embeddings to do that and link it。

We'll import the input output module from Lankett。 We'll use one of the helper methods to help us visualize this。

First， we'll pass in our data chats。And then we'll pass in the name of the metric that we want to use in La kit。

 this is responsepon。 relevance to prompt。Okay， so now we can see the distribution of this new metric we've calculated。

 low scores near zero are more likely to be hallucinations。😊，For now， we'll use this helper function。

 but later we'll dive into some of the methods that are used inside of it。

This next helper function shows us a few of the examples that were most likely to be hallucinations。

In row 48， we see an interesting example where we do have some words that are similar。

 like cow and mo。 They be near each other in semantic space。 But the sentence mu has one word in it。

 So this is really difficult to capture with a lot of similarity metrics。 And this isn't foolproof。

 semantic similarity is related to， but not the same as relevance。Say we have a prompt。

 like what happened to the Roman Empire under Julius Caesar？If the L L N responses。

 the empire was Roman， and Julius Caesar was a person in the Roman Empire。

 and Caesar salads are delicious。😊，The response may be semantically similar by using a lot of related words。

 but it isn't really answering the question directly。

 So that might be considered an irrelevant response。 Even if the response look similar to the prompt。

 But then there's also the opposite， right， So sometimes you'll ask a question。

 and a correct and good answer doesn't necessarily use the same language。 For example。

 if I ask what noise does a cow make and ask for a one word response like we see in our data set。

If the L L M responds with muo， that's a great answer。 and it's a relevant answer。

 even though it's not semantically similar in the text。

Prompt response relevance isn't the only metric that we can use for hallucinations。 In fact。

 we'll look at some more advanced and more recent discoveries， such as response self similarity。

 like self check P P where we ask an L L M for multiple responses to the same prompt and compare similarity between those responses。

 If an L L M is saying something different every time it's asked the same question。

 It's more likely to be hallucinating。 We'll explore these approaches further in the next lesson。

 So next， we're going to look at data leakage and toxicity。

 A common approach for data leakage is still string pattern matching with regular expressions。😊。

It works well， even in advanced applications， phone numbers。

 email addresses and other personally identifiable information tend to have a lot of structure that lends well to redexex。

 We're going to import lane kit metrics for data leakage。 Now。

 we'll use the same helper function to visualize the metric it creates。We see email addresses。

 phone numbers， mailing addresses， and Social Security numbers in our data set。

We can do the same for response。In the responses， we also see credit card numbers。

So now let's move on to a different metric toxicity toxicity can include a number of different things。

The primary thing we think of is explicitly toxic language， such as race， gender， bad words。

 malicious words。We'll use the same helper functions to visualize the toxicity metric for prompts。

We can see prompt toxicity is really long tailed。 Most of the toxicity is at 0。

 and only a few have higher values。We see a similar trend for response toxicity。

So you sometimes see an L L M respond with， sorry， I can't answer that。

 or I can't help you with that kind of request。 This is a refusal where the L L M detects that the prompt may ask it to do something Its not programme to do。

 So it provides a nonres。 So there is a cat and mouse game where a hacker may try to get around these refusals with clever prompting to trick the L L M into giving information。

 It should normally refuse to do。 This type of prompting attempt is called a jail break。

 A jail break is a particular type of a prompt injection。

 Promp injections refer to any prompt that tries to get the L L M to do something。

 Its designers did not intend for it to do。After we've imported our injections module。

 we'll use our helper functions to visualize  thesymmetric metric。

It's worth noting that the injection metric name will be upgraded to prompt dot injection and future versions of Lank。

 If you look at the distribution of jail breaks， you'll see lots of near ones and zeros。

 That's because the model is pretty confident in many examples。

 This particular data set over representspresent jail breaks for learning purposes。

 But these would normally be very rare and real world data sets。

Now let's look at the examples that are most likely to be prompt injections。

We can see here very complicated prompts， prompts that have lots of redirections such asI am a programmer and please answer in certain ways。

Now we'll evaluate our metrics for security and data quality。As we build metrics in this course。

 we'll want to check how well we're doing at detecting problematic examples。To do this。

 I made a dashboard using w logs that we'll use to see how well we're doing to use it。

 we just pass in the examples that we believe are problematic。

You see here that we're still failing all of our objectives except for one。In our final objective。

We just need less than five total false positives because we haven't passed in any data。

 We definitely haven't gotten five yet。Now， we can try a simple metric that looks for certain words in the response。

 such as sorry。 Let's see what examples we get from that and pass it in。 First。

 we'll filter our chats down to those containing the word sorry。

Then we can pass this into our evaluator， let's take a look。Now， let's pass it into our evaluator。

Which of the issues that we'll cover in the course do these examples look like？

So we see that we've passed one of our constraints that we hadn't before。

 we found all of the easy refusal examples just with the word sorry。

 but we still have more difficult examples to find using more advanced methods I encourage you to try new filters to see if you can find different problematic examples in the data For instance。

 you can try filtering for examples with long prompts perhaps more than 250 characters long。



![](img/54bcd02b89e9efb5f56167fe92fbf95a_12.png)

![](img/54bcd02b89e9efb5f56167fe92fbf95a_13.png)

Looking at the filter chats， you may have an idea of which sort of issue this brings up The next lessons are all about discovering and creating new metrics to identify these issues and get all of those tests screen。



![](img/54bcd02b89e9efb5f56167fe92fbf95a_15.png)