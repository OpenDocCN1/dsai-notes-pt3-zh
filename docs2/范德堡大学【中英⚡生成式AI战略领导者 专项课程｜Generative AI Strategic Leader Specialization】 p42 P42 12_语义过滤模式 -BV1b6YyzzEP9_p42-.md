# 范德堡大学【中英⚡生成式AI战略领导者 专项课程｜Generative AI Strategic Leader Specialization】 p42 P42 12_语义过滤模式 -BV1b6YyzzEP9_p42-

Large language models really excel at working with text and understanding patterns of language and a lot of times text is something that's really difficult to work with because we tend to have to have a human go and look at it to do a really good job of analyzing or we used to need a human to do that now we use large language models。

 but you know going through and trying to understand text to manipulate text is one of the real strengths to the large language model。

The next pattern。Is called the semantic filter。 So this is basically a filter that can take in text and remove information from it or only keep information that has certain meaning or has a certain certain qualities that we specify。

 And so this can be a really useful pattern for a variety of different cases。 Now。

 I'm going to show it in the case of taking text and filtering out and removing certain things that we would like to get rid of from those text。

 This might be secret information of some kind。 it might be you know。

 removing things that aren't public。 It could be all kinds of different things or removing reddonant information。

 whatever you need it for。 But this is kind of a useful pattern and taking a manipulating text。

 So let's look at an example of it。😊，So I'm going to start off with a very simple example of the semantic filter。

 and I'm going to say filter this information to remove all dates and rewrite the text as little as possible to fix issues caused by the date removals。

 and then I've pasted in some information about Vanderbilt University from Wikipedia and in this information there's a whole bunch of dates And so I'm creating a complex filter that's going to basically take in information。

 It's going remove all the dates， and it's also going to transform the information a little bit to rewrite it just in case I'm removing a date and it sort of makes a sentence awkward or there's obviously something missing。

 And so I'm going to take in information， I'm going to remove all the dates and I'm going to slightly rewrite in order to do this。

 So I've got the Vanderbilt now Wikipedia information and by using this pattern which is to clearly say that you're going to know serve as a filter。

 so we're going to say filter this information。So we're clearly indicating by saying filter that we want to preserve but remove。

 We're not trying to create new。 We're trying to take an information and filter out or remove。

 So the pattern is basically the semantic filter pattern is we're going to tell it to filter something。

 and we're going to give it sort of rules， semantic rules。

 rules about the meaning and what we're trying to remove the meaning or the purpose of what we're trying to remove。

 So then what it does is it goes through and it rewrites all the text。 And you notice that。

It does a pretty good job。 It removes all of the explicit dates。

 Now one thing I noticed is that I might need to go and rethink my prompt and how to express dates because it says founded in the 19th century and that might be too specific for me depending on what my meaning of date is So I think it took a literal interpretation of it like if it's you know a specific date。

 So if you go back and look it originally said founded in 1873 So it removed the date 1873 and replaced it by rewriting it with found it in the 19th century So it's actually kind of removing information。

 but I asked it to rewrite so it's transforming it a little bit but this shows you kind of the power it's understanding the text it's understanding what a date is it's removing it and in this case we're also transforming it to rewrite it in some way。

Now let's show you a more interesting example and kind of where semantics and understanding of the meaning of things really gets used。

 so I'm going to say filter the information below to remove any information that would help someone figure out that the patient has diabetes。

First， explain what information you're going to remove and how it might help someone figure out that the patient has diabetes。

 then provide the filtered information。So what I've got below is a fictitious medical record that describes a patient Jane Doe。

 has a number of symptoms the patient presents to the clinic with complaints of increased thirst and fatigue for the past two weeks。

 history of present illness right here， past medical history down here， medications down here。

 allergies， a variety of things。And then I'm going to actually have chat GBT go into a semantic filter on this information。

So now let's take a look at what it's going to remove， so it says。

 well the chief complaint of increased thirst and fatigue should be removed because increased thirst polygypsia is a common symptom of diabetes。

 the history of present illness mentions increased thirst and not checked or blood glucose levels。

 both of which should be removed because they are related to diabetes symptoms and management。

The past medical history includes type 2 diabetes meitis。

 and Im apologize if I'm mispronouncing this， which should be removed because it directly indicates that the patient has diabetes。

The medication metformin 1000 migs twice daily should be removed because metformin is a medication commonly used to manage diabetes。

 So this is taking the semantics of， I want things that could give away that this patient has diabetes。

 I want them filtered out and removed。 So I'm giving some semantic rules about what type of information to get rid of and has to understand to some degree the meaning in the text。

Or at least， no。Based on its training data that these are things that are commonly discussed around diabetes。

 so one way or the other， it's figuring that out。And then it goes through and rewrites the medical record and notice it rewrites the chief complaint B to the patient presents the clinic with complaints of fatigue for the last two weeks。

 the patient reports that she has been feeling more fatigued， should die any recent weight loss。

 blurry vision or infections， past medical history is rewritten， the medication is rewritten。

 and so now we have a filtering of what was here before。And so we notice that like the history。

 it removed this， the patient reports that she been or she has been experiencing increased thirst for the past two weeks。

So。We can use these large language models to develop sort of powerful semantic filters using the semantic filter pattern。

 Now， is it perfect。 No， as we've seen， there can be， know issues with it。

 and as we've talked you about before， you know， they're not always perfectly repeatable。

 but is a starting point to help， maybe support a human process that then looks over to second time。

 or to try to help prevent accidental release。 It's just one more check in the system。

 This is a fairly low cost check to try to remove extra things， Should it be the only check， no。

 if we're going to filter things out， particularly for privacy or other reasons that are where we have information that we don't want to get out。

We should always have other checks in place because this is not going to be a perfect filter。

 it's going to have some randomness， it's going to not always do exactly what we expect。

But as a part of another process， as a component to help， it's a very。

 very powerful technique that we could potentially employ in parallel and conjunction with other checks。

 other types of removals。