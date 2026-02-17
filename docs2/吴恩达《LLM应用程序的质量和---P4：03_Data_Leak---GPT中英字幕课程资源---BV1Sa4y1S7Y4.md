# 吴恩达《LLM应用程序的质量和安全性》《Quality and Safety for LLM Applications》中英字幕 - P4：03_Data_Leakage.zh - GPT中英字幕课程资源 - BV1Sa4y1S7Y4

In this lesson， you'll practice detecting data leakage。

 which is where private data appears in either the prompt or the L LM's response。

 You'll go from simple metrics to state of the art methods。 Let's try this out together。



![](img/bcc9159ebf7d99d4996e39f7204ddf80_1.png)

Let's get started with data leakage and a bonus section on toxicity。

 Unlike our previous lesson on hallucinations， which can be considered largely quality metrics。

 data leakage is more of a safety issue。There are three data leakage scenarios that are relevant for LLMs in particular。

 One， when a user shares personally identifiable information。

 commonly called PII or confidential information in their prompts。2。

 when a model returns PII or confidential information in the model response。For example。

 let's say there's a very rare disease with only a handful of documented cases in medical records。

 a specific person's name or maybe their hometown might be included in the data with the disease。

The model may respond with that person's name， even when we're asking generally about the disease if that data was included in the training set。

This is really concerning more so than the first， because we know now the model has memorized this information and it may be spread widely to any prompts to the LLM。

For a third type of data leakage， we have leakage of our test data into our training data set。

 since many of the LLMs that we use are either proprietary or difficult to nail down exactly what the training data set is。

 it can be nearly impossible to know if the data we want to use to test a model has been seen in training。

 and that would invalidate our tests for generalization and accuracy of the model。

We won't go too far in detail for this third one， but we'll see one and 2 by looking at prompts and responses in our example data。

 First， let's do some setup。We'll then use our same setting for pandas to better see our prompts and responses。

We'll import Wlocks。And we'll import our helper functions that we've been using。 Next。

 let's import our data。Okay， now we can take a look at an example of data leakage。Okay。

 so here we see what might come up for data leakage for many because we're asking for a number of credit card numbers that we see in the response and admittedly this may be data leakage and we don't quite know if these responses include fake credit card numbers as we've asked or real credit card numbers that happen to be in the training data。

This is a complex case。 One thing that's really interesting about data leakage is that you can go really far with really simple tools。

 One tool that we have available to ourselves are regular expressions。

 These are specific patterns that we're looking for in the text to pull out things like email addresses。

 Social Security numbers and others。😊，We'll first look at how to do this with Lnkkin。

So first thing we'll do is import the Redexs module from linknk kit。Okay。

 we see that we have a number of patterns in our data， exactly two email addresses， phone numbers。

 mailing addresses， and Social security numbers in our prompts。

 and we can look at a similar visualization for our responses。Here we see one more。

 so now we have mailing addresses， email addresses， Social Security numbers。

 phone numbers and credit card numbers。 You can customize your patterns in link kit using a Json file。

 We won't use that here， but we'll see this in the later lesson。 Okay。

 let's look at the queries that gave us a has patterns response。Okay。

 so we see a number of them here。 One where we ask for some example data and get some phone numbers。

 some with fictitious mailing addresses， and one with a real mailing address。

 While our helper function calls link kit under the hood。

 let's call it a different way to package up our results for the evaluation。 So first。

 we're going to need to import UDF schema。

![](img/bcc9159ebf7d99d4996e39f7204ddf80_3.png)

UDF schema is a function that grabs all of the metrics that we've defined and linked it。

 and we can apply them to our data set to annotate our data line by line。

 so let's go ahead and create a new data frame called annotated checks。If we want to take a look。

 we can do that。Let's just look at the top five。Okay。

 so now we see our prompt and response as we had before。

 but now our prompt has patterns and our response has patterns。

 and you'll see while there are many nuns， there's also phone number and different types where we do find a pattern。

So now we need to filter this data。 Let's go ahead and define some filter using just the nulls。

 so I will copy this over here。So we have our annotated chats。 and inside of these square brackets。

 we want to filter for。Annotated chats where prompt has patterns is not null and annotated chats where response has patterns is not null。

This will give us a number of lines that we think have data leakage issues。

So we can go ahead and evaluate our example using our evaluation helper function。

And we're going to set our scope to leakage。Okay， so what do we see。

 we see that just this simple rule using the patterns that comes and link it。

Will pass all of our easier data leakage examples， But I put in some very difficult examples for this problem so that we can learn to make more complex metrics。

 Another thing you might notice is that we have several false positives。

 This is going to be the case when we have difficult problems like data leakage。

 There's a lot of complications。 And so often， if we create a rule that will capture all of what we might consider data leakage。

 we may capture more than that。 For example， those cases where we've asked explicitly for fake data。

 that may not be a data leakage or maybe be a data leakage。

 depending on whether or not the model gives the right information。

 So our next approach is going to be entity recognition。

 While pattern matching and regular expressions are really helpful for this personally identifiable information。

 There's other examples of confidential information that you want to include。 Often product names。

 employee names， project names， especially when working within the。Context of a company。

So here's an example on screen of the entity recognition task。

 We have a sentence or multiple sentences where we want to go and label individual tokens or words or spans of multiple words that represent particular nouns or particular entities。

 So Seattle is a place。 Bill Gates is a person。 October 28，1955 is a date。

 Microsoft is an organization。 All of these things are helpful in finding confidential information。

 We're going to use an existing model to find the entities in our data and create a metric from that。

 So to do so， the first thing we'll do is import our new package。This is called Sp marker。

And I've chosen a model that we can use for entity recognition today。

So let's go ahead and call this entity model。Okay， just a few things to note。

 there's many pretrained models in this package， and many of them are labeled by things like course or the type of model that's underlying。

 We want to use coursear labels here because it'll give us things like product or person things like this。

 although the fine grainined labels will give us more specific words。

 So as you work on a production setting， you may want to use a fine grainined model and really comb through the list of entities that you'd like to mark as confidential information。

 Let's go ahead and call our model here。Okay， so we have a little warning here。

 we'll ignore that for now， but our response here is a list of two different dictionaries。

 one has Bill Gates labeled as person with a score。

 The other has modelizer 900 with a label product in another score。 So this is really great。

 So next let's define which entities we want to include as possible leakage。For this example。

 I'm going to use person。Product。An organization。But I highly suggest going to the Sp marker model package and looking through the entities for yourself。

Now let's create a metric using our entity model。So we'll import Reg data UDF。

And we'll go ahead and create our metric using our decorator。

So our first metric just takes in a prompt。And we'll call it prompt。entity leakage。嗯。

I'll go ahead and pace our definition here。It's always helpful to test our decorated functions。

 and we can do that just by calling entity leakage and passing in our data set。

Maybe we'll pass in the head just for five rows just to speed things up。

But the output should be a list with five different values as responses。 So here we see nuns for two。

Organization is one of them and the nuns for the remaining two。Okay， now that we're happy with this。

 let's go ahead and make a copy and do the same thing for response。So I will just copy this here。

You can even leave the same function name because this decorator will register this function。

Let's go ahead and call this response response。And then finally。

 we need to check for response down here。And will run the cell。So now we'll do our same thing here。

 we will annotate our chat C set。Using our new metrics。Now let's check out what we got。 Okay。

 we'll use our same helper function， show link kit critical queries and pass in our prompt into theleage metric。

😊，Okay。And we see a number of prompts and responses here， that's exciting。

So we might make some guesses about why which entities we found in these prompts。So for example。

 we see Python and we see Parker， which is a made up programming language for this example。

 but either one of those might be labeled as product。And similarly， in this。

 the word jascript is probably the product found in this。 Now。

 we might consider javascript to be a common thing that we don't consider data leakage。

 but that's what makes creating metrics difficult。 It's really difficult to define some rule。

 I'm going come up with these specific entities that we consider confidential and not。

 So the last thing we might do is。Define some threshold。I'll just paste this in right here。

So this is taking our annotated chats。 We're going to pass in both our has patterns for prompt and response。

 but then also our entity leakage。 So this is just building on what we had earlier in the notebook。

And we see we'll have many responses for this。

![](img/bcc9159ebf7d99d4996e39f7204ddf80_5.png)

We'll scroll through them。Now let's go ahead and evaluate our examples using our helper function。

 using the same code we justused。Passen or annotated chats。

We'll close this parentheses out and before we do。Let's go ahead and put a comma and define a scope。

Okay， so this is exciting Now we've passed not only our easier examples。

 but our advanced examples made for this lesson。Great， you've just finished data leakage。

 So the last thing I want to mention in this lesson is about toxicity。

 toxicity can look quite similar to data leakage of other different concepts， but in both cases。

 there may be data included in the training data that we don't want to see in the model outputs for toxicity。

 I just want to give some quick tips for how to create metrics related to it。

 There's a lot of existing models for toxicity， explicit toxicity is when we have text that includes often just bad words。

 So may be inappropriate groups， maybe profanities， this sort of thing。😊。

This is great to capture and make sure that we're not finding too often in our LLM responses or maybe only when appropriate or not at all。

 depending on your application。 But there's cases that we want to go further than that。

 So implicit toxicity not only captures explicit use of bad words or harmful words。

 but also includes concepts and sentences that may say things that are harmful about different groups or people。

😊，Without using bad words explicitly， So this means we go beyond kind of searching for a list of bad words and really want to use a machine learning model。

So one example that I'm going to share with you that I think is great for using metrics while combining with other toxicity metrics is the toxicgen。

 data set and the models built on top of it。SoTogen includes a number of sentences。

 about a number of targeted identities shown here and shown in their kind of proportion。

 but we can use models built on top of to to create a great metric， so to use To。

 we're going to import the transformerss package from Huging face。And particularly。

 just the pipeline function。So with pipeline， we can import a model。 We're going to call this toxic。

Paper。That's what it is。 So hateper is an existing toxicity model。

 actually for explicit toxicity that the creators of the toxicgen data set doing implicit toxicity have built on top of。

 So if they fine tuned the hate model。 So we're going to go ahead and download that fine tuned。😊。

Version of the model。Okay， hopefully I spelled things right， but there's our model。

And let's go ahead and call it with actually two sentences just to show how the API works。Okay。

 so we've passed in two sentences and we'll see that we got labels of zero for both。

 so this is saying that they're both not toxic with pretty high scores。

So the second sentence here will sometimes trigger toxicity models that aren't about implicit toxicity。

 just by the inclusion of a key word like women。Race is this sort of thing。Okay。

 let's go ahead and make a quick metric for that。Feel free to copy this metric can use it in your applications or change it as you wish。

 just a quick explanation here， so we're creating this for prompt prompt。

 implicit toxicity and we'll take the last value of our label which is a string so we'll get a zero or a1 and we'll pass that in as a result after casting it to an integer。

Okay， we'll probably want to do the same thing for response。

 but you can go ahead and do that on your own time。 Let's go ahead and see what this looks like。

 Okay， so we have a number of possibly toxic prompts。With four very subtle reasons。

 so this is one thing that I wanted to show because it's quite difficult to use these very subtle metrics。

 you're really concerned about possibly having many false positives。

 so perhaps credit card numbers or things like this bring up toxic issues are in a lot of toxic sentences。

这のす。Okay， so that's the end of our lesson on data leakage with a little bit on toxicity。

 join us for our next lesson where we talk about refusals and prompt injections。

I'm excited to see you there。

![](img/bcc9159ebf7d99d4996e39f7204ddf80_7.png)