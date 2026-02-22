# 亚利桑那州立大学《黑暗数据迁移与架构｜Dark Data Migration and Architecture》中英字幕 p69 2_David Hand暗数据分类体系.zh_en [BV1TkurzMEmm_p69]

Welcome to dark data Today we're going to talk to Dr。 David Hand。

 emeritus professor at Imperial College London， he previously chaired the Stats Department there as well as previously being the president of the Royal Statistic Society coincidentally enough。

Only two people have been presidents of president of the Royal Statistic Society twice and Dr。

 Hand was one of them he has consulted at numerous corporations and has been on the statistical advisory board for various international companies he's written over 30 books hundreds of papers on ST related fields and today he's particularly interested in dark data data quality and how you can make a valid and accurate decision based on the unknown data elements that present us in everyday society so welcome Dr。

 Han thank you for thank you。So I want to start it off with just the basic question。

 when you talk about dark data， what do you mean？Yeah right so basically dark data a data you don't have but which you think you have or hope to have or would like to have and so on their data you're missing so that the data you have incomplete you may know your data are incomplete but you may not know incidentally Gartner the Gartner organization also has a definition of dark data but their definition is really just a special case of my more general definition theirs is essentially data that you've collected but haven't made use of so obviously my definition is broader and includes data you haven't collected the Gartner definition is only one type and in my view are relatively minor type in terms of corporate success absolutely and when you think about the data you haven't collected data you you're missing as well as data that you may not even be aware of how does that factor into your definition and how people should view dark data？

I think people need to be alert the key thing， the key message I want to get across next during the interview is people need to be alert for the sorts of things that they might be missing let me give you a couple of examples of this kind of thing。

Far ways that dark data can arise are in nonresponse in surveys， people who don't reply to questions。

 you know you're missing that or dropouts in clinical trials again you intended to collect the data on these people but they don't turn up for the clinics and so on in those cases at least you know the data are missing you know people have got an age on weight and so on you just don't know what it is。

On the other hand take the example of a hurricane knocking out all the mobile phone masks in an area then you won't know what bad news about those areas you're not getting and that can be very bad news indeed and so that' dark data you don't know that you're missing with that hurricane example。

 where do we see that where do we see that problem actually first surface？

Oh was it Hurricane Katrina， I think in the east coast of the U yes， yes。

 that's perhaps in New Orleans， yeah yeah， yeah and there were。

Real examples of exactly this sort of thing you're not getting any phone messages saying please send emergency help so you think oh they're okay they don't need emergency help。

 but the reason you're not getting that is dark data absolutely absolutely in。😊。

One of the things that I wanted to sort of go back on is when you gave that first example。

How would you look at people actually retrieving the data and making some sense out of it when you're looking at surveys and people who drop out？

Would you then you know create like let's say a machine learning algorithm and try to predict what they would say or what would you do that's a very good question and we should explore that in more detail there are various strategies for coping with dark data and one broad class of strategies is exactly what you suggest develop methods which try to impute try to interpolate what you're missing but you have to be careful because maybe the data that you're missing are missing for some reason which makes it different from the data you've got so your interpolations could be biased and there's quite a lot of pretty heavy theory associated with how you can be aware of that problem and try to overcome it so would you then look at the reasoning behind missing data in that example would you look at that as a subset of dark data how would you suggest our students to look at that yeah I have actually I have a taxonomy of 15 types of dark data and those sorts of arising in survey。

Nonres surveys or dropouts from clinical trials are a particular class within my taxonomy。

 but there are well 15 types altogether。I mean， and can I just say a completely different type completely different type here is not missing characteristics within cases or like non-respons in surveys or clinical trials or dropouts or anything like that it's sometimes the variables are missing let me give you a totally trivial example but which illustrates it overall taller children have a larger vocabulary than shorter children I no reason for that is that correlation can be explained by age taller children tend to be older。

It's a trivial example if you didn't have the age in then right exactly。

 and you think if you weren't aware of that， if you hadn't measured age， you might not recognize it。

 that's the issue。😊，And that's a trivial example。😊。

What about those sorts of problems arriving in corporations， what variable haven't you measured。

 which might explain the structures in the data in a straightforward way？So yeah。

 so now we're looking at things like data accuracy， data completeness。

 so what would you say to people who would then look at dark data and say well。

 this may be some aspect of data quality I think it I think。

You can certainly look at it that way it is it is an aspect of data quality there's a lot of truth in that I mean data quality has a number of dimensions like accuracy relevance timeline this coherence completenessaccessibility security and so on and I think you can think of dark data as including all of those but with a shift of perspective the dark data perspective is what are you mis asking what are you missing what are you overlooking what don't you know about and then the corollary question of course how might you be being misled by any implicit assumptions you've made about whether you've got of all the relevant data so for yeah for things that like might mislead you you know and I know we've had some conversation before and we talked about various cases so what would be a good example that people would want to be able to sort of look at and understand when we talk about being misled by data and how that sort of。

Opers within dark data yeah okay， let me give you a trivial but illuminating anecdote to illustrate that。

This is how I kick off my book on Dark Vata you're walking down the road and you come across an elderly man putting down little piles of powder every 50 foot 50 feet down the center of the road and you say what are you doing and he says it's elephant powder it's to keep the elephants away and you look at him and say but there are no elephants here and he says yes。

 it's wonderfully effective isn't it？Of what he's missing is the fact that there are no elephants there and the elephants would be kept away even if he didn't put the elephant powder down he's missing something crucial that's a straightforward example of dark data absolutely so like how would you describe statistical relevance when people are putting together like tests and maybe like experiments for companies like AB testing ABN testing multivariate things like that how would you look at those types of tests and for the people who put it together design of experience design of experiment experiments how would you look at that in。

😊，And tell them you need to be able to identify certain gaps in how to move forward without predicting something irrelevant or something incorrect right I think that's a great question and in a way those the sorts of things you describe AB testing experimental design in general are ways to try to tackle dark data issues there are ways to try to get access to the counterfactuals。

 the things you didn't measure you know you measure you assign people randomly to treatment A or treatment B and you don't know how the ones you assigned to treatment B would have reacted had you assigned them treatment A。

But clever experimental designs are ways to try to infer the difference between them it's had you given them to the same people so those are nice examples of tools which try to tackle the dark data problem in fact there's more than that randomization in sort of AB trials and so on is a way to take advantage of dark data by randomly assigning the treatment you're randomly deciding what not to measure on people。

 but that allows you to make clear and valid statements about expected values。Absolutely。

 so when we're looking at like a sampling or a trial or any type of testing and then even a data set when we're looking at enriching data。

 what part does enriching data play in dark data and。

When when we have issues in corporate America or in any organization where you take data transform it into something or enrich and make it better to then provide insights。

 sometimes it can be done improperly。So like what are the things people need to think about when they think about dark data and data enrichment。

 yeah I think that's a very good question because it's so important the truth is that enriching data combining data from different sources has got huge potential for all sorts of things for improving accuracy for triangulation of values for deducing unknown quantities and so on。

So they can really those sorts of tools for merging matching data can really enhance substantially enhance the value of corporate data but those sorts of things data enrichment matching merging data fusion all carry the risks of introducing errors I mean there are obvious things that people would be familiar with matching errors and duplicates arising from different formats somebody might be in one database they might be John Smith and in another JW Smith and in another John William Smith and they might not be properly matched to each other there's a lot of work on trying to overcome those problems I should say that I'm keen on the use of red teams in that role people trying deliberately to identify to spot errors in a data but the sort of answer to your question is that data enrichment has got huge potential and it carries a great risk of generating dark data so one has to have a sort of。

Associated amount of great care。And I should mention also legal constraints I shouldn't privacy and confidentiality I should never talk about data enrichment and matching data without having a sort of quaary keep your eye on the legal aspects yeah absolutely you know I've been a part of a number of projects in you know obviously my professional career where data enrichment has played a huge part in gaining value however over the years a lot of times。

I've noticed that you know depending on the company or the enterprise you get more value or less and then in most cases we're not getting all the value that's possible right so that goes into think into I guess the last sort of segment of what I wanted to talk about which is。

The dark data around and and you can I definitely want you to speak to this around how you look at this。

 but the dark data around the human element of it and what I mean by that is when you're working on a project you're doing data enrichment transformation may be doing AB testing you may be doing many different things right but the dark data around when you're working with a team and you yourself like us we may not know what we don't know right and we may not know how to enrich something to get the value that we actually need and and one good example of this is I joined this company and they have been doing marketing a lot of marketing campaigns and you know they stated well you know our campaigns have always generated results。

Always generate results and you know， you don't want to be the bad guy in the room。

 but but you then' ask， well， as opposed to what？Right like there could be more results。

 there could be better results， there could be worse results have you have we taken the time to understand if the results that we've garnered although they're good could they be better and that's sort of the sort of the centerpiece around the question is。

You know we have these teams， we have these organizations and a lot of times we believe we're performing well right and it' it's like if you look at the NFL or the NBA obviously the team that won the championship has performed the best。

Yeah。I mean typically you would say that right and that's sort of explicit but in the corporate world it's a little bit different so how would you go around assessing if we've used the data to the best of our ability and the data products up up underneath them right yeah yeah I like your examples it's like investing in the stock market in a time when it's rising and you say look I've done really well well you it have been disastrous if you hadn't you's that's a very good example。

I think I mean I think you you see this sort of issue all over the place。

 you see it especially with back testing things like stock market indice seasons and so on。

 I think that，嗯。😊，People need to。Try to。Get a handle on what they don't know or what they might not know。

😡，I think。There's no way of making the risk go away， but if you can have a diverse。

In every sense set of eyes looking at these problems。

 spotting sort of different ways that they might have gone wrong or might be making assumptions。

 you know people coming from different backgrounds will say yes I've seen this before or some of them might say I've seen this before and there was an assumption you know and it was based on the fact that everything was getting better or you know and I've seen people build retail credit scoring models in benign economic conditions which they just full the bits but if you had people who were perhaps a bit older on your on the panel evaluating these things they might have lived through the 70s when things weren't so good for instance so you need diversity I think diversity of perspective。

 many different kinds of people with different perspective different backgrounds different knowledge about different things actually you've reminded me a wise very wise colleague of mine once said to me I don't want to work with people who know what I know there's no point in that I want to work with people who know things I don't know。

I think the answer exactly that goes back to the like the concept of hiring people who can teach you right that type of a thing yeah absolutely and you know I think your insight there has been is super critical because I think that's one of the opportunities that most organizations regardless if it's you know corporation and nonprofit can really look at to figure out how they can really provide more value for their consumers and themselves so yeah so thank you thank you for the time and any other last thoughts。

Though， except for the sort of overriding point about dark data is be cautious。

 think about what you might not know because what you might not know。

 what you the data you might not have collected or be aware of。

The information in those data could be substantially misleading you， keep alert。Absolutely。

 absolutely， thanks Professor An， thank you for your time。

 pleasure absolutely have a going thank you。