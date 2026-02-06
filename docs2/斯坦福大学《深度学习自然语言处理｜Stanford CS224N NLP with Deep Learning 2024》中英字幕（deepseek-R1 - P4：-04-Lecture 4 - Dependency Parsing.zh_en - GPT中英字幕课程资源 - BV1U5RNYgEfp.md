# 斯坦福大学《深度学习自然语言处理｜Stanford CS224N NLP with Deep Learning 2024》中英字幕（deepseek-R1 - P4：-04-Lecture 4 - Dependency Parsing.zh_en - GPT中英字幕课程资源 - BV1U5RNYgEfp

![](img/ff5b0ccbb341c33606125428d1852278_0.png)

![](img/ff5b0ccbb341c33606125428d1852278_1.png)

Okay， hi everyone。Okay， so for today we're going to you know。

 guess do a 180 from where we were on Tuesday。 and so today I'm going to talk about。😊。

Syntactic structure， linguistic structure of human language sentences。

 dependency passing and how well dependency grammars and then how you go about building dependency passes。

 so we're solidly into linguistics zone today。😊，How many people in the audience have done a linguistics class。

 Yeahy， okay， there are some people have done linguistic classes。 Okay， great。

 and for the rest of you， well， you know， this is your chance to see a little bit of human language structure。

 And if you like it， you can enroll in the linguistics class later on。 Yeah， so。😊，응 없어。

So you know so assignment2， we handed out on Tuesday。 So in the second half of assignment2。

 what your job to do is to build a neural dependency PAs using Piytorrch as you will sort of come to later on really the bit that you have to build is just the machine learning bit of making decisions and really we give you most of the rest of the neural dependency PAs。

 but this is also then a chance to remind you that assignment2 in that second half users Pitorrch。

 one of the leading deep learning frameworks。 So if you're not familiar with that it would be a really good idea to also go along to the Friday Pitorrch tutorial though we have tried to make assignment to So it's a fairly good place for learning Pitorrch as you go along we'll say more soon about final projects but you're certainly already encouraged to come and meet with Ts or me about。

😊，Final projects。 And we're putting up information about the T so you can know more about them on the office hours page。

Okay， so let's get straight into it and start looking at linguistic structure。 So in。In。

Thinking about linguistic structure of human languages。

 there are two primary ways that people have thought about it。

 So one way is using the idea that linguists normally call free structure。

 which is then represented in terms of what computer scientists normally know as context free grammars。

 So I'm going to spend a couple of minutes going over that view of things。

 but you know actually is not the main one that I'm going to talk about in this class I'm going to spend most of this class talking about an alternative way of thinking about things called dependency grammars。

 there are actually some correspondence as you can make between the two ways of thinking about things。

 but I'm not going to go through into those here today。

 So for the constituency grammar or free structure version of things。

 The way that you go about thinking about the structure of human languages， is。Well， there are words。

 languagegus have lots of words， hundreds of thousands of words。

 but it seems like a lot of the words， nearly all the words， in fact。

 fall into a few basic classes that represent their nature and how they behave in sentences。

 So for words like the examples here。 we have nouns。 So cat is a noun， door is a noun。 but， you know。

 something like linguistics is also a noun。 So we have nouns。 And then we have other kinds of words。

 So something like cuddly is an adjective， a word that can modify nouns。

 And then we have the the for the cuddly cat。That is sort of。

A slightly more complex one as to how to name， normally in model linguistics refer to words like that as a determiner。

 you might also see the name article。 and when sometimes when people are trying to shoehorn。

Human language into eight part of speech categories that they say it's an adjective。

 but doesn't really behave like regular adjectives。

 And then we have words like by or through or on and two and ones like that。

 And so they're then prepositions。 right， So we have these classes。

 And with lots of words fitting into each class。 And so they're referred to conventionally as parts of speech。

 But then once we've got words， we start putting them into bigger unit。

 So the cuddly cat is some kind of unit。 And so it seems like this is a explication of a noun， a cat。

 And so this gets referred to as a nouned phrase。 And then by the door。 Well， this is a phrase。

 But actually， it has inside this the door。 And that's a nouned phrase。

 But this bigger unit here of by the door is then a prepositional phrase。😊。

And we can continue to build bigger units。 So inside， you know。

 this we have this phrase that we've already looked at with a noun phrase and a prepositional phrase。

 But then we can have another noun phrase， the cuddly cat。

 and we can put them together and build a bigger noun phrase， the cuddly cat by the door。😊。

And so to represent this， you can start to write a free structure grammar or a contextfree grammar that represents what are the possibilities for building up sentences here in English。

 those similar kinds of free structure grammars can be written for other languages。

 So this is sort of starting to give you possible structures for a noun phrase。

 So you can have a noun phrase just goes to a determiner followed by a noun。

 But then as well as the cat and a dog， you can have the large cats。So you might say that， okay。

 rather than that， I might want to have as a better rule that a noun phrase goes to a determiner and optional adjective。

 and then a noun。 If you think about it， you can sort of have multiple adjectives。

 So you can have the。The large green cat or something like that。

 So you can really get multiple adjectives that are hearing。 And that sort of star。

 the clean star says you can have lots of them the large cuddly green cat。

 But then you can stick things after the noun phrase。

 So you can put these prepositional phrases like in a crate。

 So we might also want to say that a noun phrase can be rewritten as a noun phrase followed by a prepositional phrase where a prepositional phrase can be represented by preposition followed by a noun phrase。

 And somewhere we're also going to want to represent how parts of speech membership。

 So a determiner can go to words like a or the and an adjective can go to words like large。

Cudly or many other words that I'm not going to write down。And a preposition can go to words。

 like in on under。Et cetera after that。 Okay， so now I've got a little grammar here。

 and this little grammar here could sort of make everything I've got in these sentences。 Well。

 actually can do this one， too， It can do the large barking one where there are multiple ones。

 But then if I start going beyond these noun phrases and see。

 think of sentences like talk to the cat or talk to the large cuddly dog by the door。 Well。

 now I've got here a verb talk。 And I've again got a preposition。

So I might then have more rules that says I can have a verb phrase and the verb phrase can go to a verb and then a prepositional phrase。

 And then that could explain these two sentences as well。 And in this kind of way。

 I can start to build up a grammar of the structure of English sentences as a context3 grammar。

 Make sense。Yeah， okay。And so that's what is being quite commonly done in linguistics and elsewhere。

Okay啊。Yeah， so let me just do that once more behind in this one。 So one thing I can do here is say。

 oh， I have， I'm going to look at this with its phrase structure。

 And if I write it upside down to give myself some space for later， you know， I could start。

Making a phrase structure that is of this sentence。 and I'll start to run out of space。

 but I can sort of start to make this phrase structure of the sentence。 So that's phrase structure。

 But there's another form of representation that has been fairly widely used in linguistics。

 and were going and has been commonly used in NlP and we're going to use for the pars we build。

 and that's dependency structure。 So dependency structure represents things in a slightly different way。

 It thinks about words that are the main word or head or something。

 And then which words they take as modifiers or arguments。

 So for look in the large crate in the kitchen by the door。 Well。

 this is describing a looking command。 So the head of the whole thing is looking。 and then looking。

Taking one or more arguments or modifiers。 And well， what the looking is saying here is， well。

 what you want to do is look in the large crates。😊，We are looking in something。

 And then when what we're looking in is a crate。 And then the crate has some modifiers。

 It's a large crate。 It's the large crate。 And then the crate is also。Place somewhere。

 It's placed in the kitchens so that in the kitchen is also modifying Cate。

 And then we've got over here the by the door， well。The by the door is also modifying crate。

 So we've also got a link down over to here。 And that gives us our piece of structure here。

 which having filled that in makes me realize actually got it wrong And when I was sew the constituency representation。

 whoops C。 So I should get my because in the constituency representation。

 I made the kitchen by the door into a phrase。 that was actually wrong。

 whoops spared me So what I should have actually had was we had another prepositional phrase that went to a no phrase of in the kitchen。

 and then both of those。😊，Were coming off a bigger noun phrase like that。 Whoop， see， okay。

I get it right most of the time Okay but so this idea of dependency structure is that we're sort of finding what is the head word and then we're saying which things modify the head word and either of these representations we can be using to sort of work out what the structure of sentences is in terms of which words go together and which words modify other words and so the basic idea is so when humans communicate we communicate in a linear stream right so that if it's conventional writing systems。

 it's a linear stream of words that you're reading if it's spoken language like your understanding me speaking right now。

 it's not a linear stream of words， it's a linear sound stream and you know like when people speak。

 there aren't any you there isn't white space between words， when people speak。

 you know occasionally。😊，People pause at the end of a clause or sentence or something。

 But in general， I'm just sort speaking continuous words that run one into each other so that there's a linear sequence of sounds coming up by mouth。

 and you have to do all of it like that。 But but if you're then thinking， oh， gee，😊。

I can actually understand Chris talking。 Then somehow you're taking that linear stream and you're turning it into a meaning where certain words are modifying other words。

 and you have these bigger units， like constituents that are understanding the meaning of the sentence。

 And so human listeners need to work out what modifies what to be able to understand sentences correctly。

😊，And so similarly， our models need to be able to understand sentence structure in order to be able to interpret language correctly。

 And so for what we're going to be doing for building dependency passes is we're going to be explicitly building a neural network model that says。

 let's find the structure of these sentences。 in a way we actually move away from that later on。

 because when we move into transformer language models， they just take in the sequence of words。

 But actually inside the parameters of the neural network。

 they're recognizing and building the same kind of structural units and we'll talk about that later in the class。

 to give you more of a sense of how these you know understanding what modifies what is important for interpretation。

 here are a few funny examples from newspaper headlines。 and theyre funny examples because you get。😊。

Their sentences don't just have one way of interpreting them。

 when you have a sequence of words commonly in human languages， sequence of words are ambiguous。

 and it's relying on human interpretation of what makes sense and what goes together to work out how to read them so。

Here's a first example， scientistsists count whales from space。 Now that's ambiguous。

 And you can give this two possible readings。 So how can you give this headline two possible readings。

Yeah， one is that they are in space counting whales and the other one is that there are whales from in space。

 Yeah so one possibility is so we've got this prepositional phrase。

 this is the prepositional phrase here， one possibility is that this prepositional phrase is modifying or is the yeah。

 is modifying whales So there whales from space and the other possibility is that it's the count that's happening from space。

 So the scientists accounting it from space。 Okay， so that corresponds my two pictures here。

 So in one pictures the counting that is happening from space。

 which is actually the right interpretation what the article is about but in the other interpretation we have space whales and and the scientists count the space whales that are。

😊，Or something like that。 And so then we have the from space that are modifying the whales。 Okay。

 so what we have here， right is a prepositional phrase， which comes after a noun phrase。

 it's just a one word noun phrase here， whales， that's fine。 And then before that is a verb。

 And so the thing， so one place in English where you get a lot of ambiguities is from these prepositional phrases。

 because whenever you get prepositional phrases and prepositional phrases are really common in English。

 if you think about it， whenever you get them like this， it's always ambiguous as to。😊。

It's always ambiguous as to what earlier thing in the sentence theyre dependent of and so。You know。

You can sort of put in another prepositional phrase in the morning or something like that。

 And so then the ambiguities just multiply。 And so the important thing to notice here about human language is human language is in syntactic terms globally ambiguous right So in programming languages you have local abiguities is interpretation。

 how many people have done a compilers class。 I think very few these days。

 anyone done a compilerrs class， Okay it looks like less people have done a compilers class than a linguistics class。

 that's interesting。 okay well， I make too many analogies to compiler class then you know when I was young。

 you know， if I was still the old days kind of C curriculum where writing interpreters and compilers as seen as the mainstay of a computer science education。

 but no more， I guess yeah， so。😊，In programming languages， you can have a local ambiguity。

 but ambiguities are always resolved， right， so we have simple rules and programming languages that it else has construed with the nearest if。

😊，Yeah， it's a bit different in Python because it's indentation。 but you know。

 there are rules that so there's never global abiguity in a programming language。

 and but human languages just aren't like that， right。

 that there's nothing that resolves which of these two readings is correct if I made it a bigger sentence that still be ambiguous。

 Youre just sort of meant to read it and use context in your intelligence to decide what's going on。

 And so to take a bigger but real example This is the kind of boring sentence that you can read in the Wall Street Journal most mornings。

 The board approved as acquisition by Royal Trustco Limited of Toronto for $27 a share at its monthly meeting。

 So what you can see in this sentence as we've got a verb。 and then we've got a noun phrase。

 and then what after that， we have four。😊，s in a row。 Okay。

 so what do these prepositional phrases modify， So what does by Royal trustsco Limi modify。

The acquisition， right So it's the acquisition by Royal Trustsco， then of Toronto modifies。

So it's raw trustco limitedmited of Toronto。 So yeah， later on。

 prepositional phrases can also modify earlier prepositional phrases。

 or at least the noun phrase inside than World trustco Limited。 Okay。

 for $27 a share is back to modifying the acquisition。Okay， at its monthly meeting。Yeah。

 it's the approval， so it's gone way back up to there， right？😊，But， you know。Yeah， so， you know。

 so if you start having sentences with a whole bunch of prepositional phrases like this。

 you can start getting more and more ambiguities of attachment。 I mean， you don't get the full。

🎼You don't get the sort of full free choice factorial number of attachment points because there is a restriction that these dependencies don't cross。

 So once you've gone back further， you have to stay equally far back or go even back further back again。

 But nevertheless， so the number of readings you get is the cut alarm series。

 which is a series you see in a whole bunch of other places。

 if you've done any graph theory or anything like that， you know， if you're doing triangulations。

 you get cut alarm， because you get the same property that things don't cross。

 So it's an exponentially growing sequence of possible readings， And so it quickly gets very big。

 So I think when you you've got four。Prepositional phrases， you get 13 readings。 And if you have 5。

 you get 27。 and you know， grows up from there。 So you get a lot of ambiguities。

 But the crucial thing to notice is， you know， human beings read sentences like this every morning。

 or at least people who work in banking do。 Well， you know， having their cornflakes。 And， you know。

 they， the brain doesn't explode， trying to think about the 13 different readings and which one is correct。

 right， We just sort of do this as we go along。 And it's sort of obvious。 Okay。

 let's do a couple more examples of where we get ambiguities。 And。😊，In human language。

 So a different one you get is coordination， scope， ambiguity。

 So shuttle veteran and longtime NAer executive Fred Gregory appointed the board。

 How is this sentence ambiguous。If mean two people or one。Yeah， so there can either be one person。

 Fred Gregory， and they're both a shuttle veteran and a NASA executive。

Or it can be that there are two people。 There's a shuttle veteran。

 and there's long time That'ser executive， Fred Gregory。Okay， yeah。

 so and we'd be kind of capturing those by having extra grammar rules where a noun phrase and go to a noun phrase。

 a conjunction and a noun phrase。 But then another。

 another thing that you get in English's app So you can have a noun phrase that's a descriptive noun phrase of another noun phrase like a name。

 you know， the author， Fred Gregory or something like that。😊，Saying the word English again。

 I meant to comment。 So you know I'm only going to give English examples here in different languages you don't get all the same ambiguities。

 So if you're familiar with same Chinese。 you might have thought about the prepositional phrase example of wait a minute。

 we don't have that one because the prepositional phrase modifying the verb would appear before the verb and the object now would be afterwards。

 So it' would be completely unambiguous and that's true。

 but you know that doesn't mean that Chinese is unambiguous。

 Chinese has lots of very bad ambiguities。 and yeah。

 it's just that you know different languages have different syntactic structures。

 Okay here's so sometimes in English especially when you're sort of in a more written form rather than having。

😊，An explicit coordination word。 You can just sort of use juxtaposition with a comma to have the idea of coordination。

 So here's a fun example from the first Trump administration of how we can have a coordination scope ambiguity Doctor Nohar cognitive issues。

😊，Right， so again， this is the same kind of coordination scope。

 ambiguity that it can either be kind of no heart and cognitive issues being conjoined together like that。

 or else it could be that it's no heart or cognitive issues being conjoined together like that。

 You make the choice。Okay， let's see。This， this is。

 this is my rique one for a different kind of ambiguity trigger warning。

 Students get firsthand job experience。😊，So this one is also an ambiguity， you know。

 as to whether you're having the， the firsthand and then both the job and the firsthand a modifying experience or there's its other reading。

 if you have a smutty mind that might come to you。😊，Okay， one more fun one。 Okay。

 mutilated body washes up on Rio Beach to be used for Olympic speech volleyball。 Okay。

 so what what are the two possible readings of this sentence。 You know， these are real examples。

 from quality newspapers。😊，Okay， one are the two readings of this sentence。 Yeah， so we've got。

 So so here we have one of these infinitivval。😊，So in aphittial verb phrase to be used for Olympic Beach volleyball and for these。

As well， you know， they kind of have the same effect as prepositional phrasers that they can modify different things。

 So it can either be the Rio beach that's going be used for the Olympic Beach volleyball or it's going be the mutilated body that gets used for the beach volleyball。

Okay， yeah， so so these are the kind of ways in which we sort of want to use the structure of the sentence to understand what they're meaning。

 We also use it in lots of sort of just sort of mundane practical ways when we're building various kinds of natural language processing systems。

 So， you know， a kind of thing that people often in practical systems do is that they want to get out facts of various kinds。

 So for people who do stuff with bioinformatics that they commonly want to get out things like protein protein interaction facts。

 And so commonly， you can get those kind of facts out by looking for patterns。 So you know。

 have a verb of interacts。 that's going to be indicating an interaction pattern。 And well。

 it's going be taking argument。 So it's going to be taking a subject and interacts with the prepositional argument。

 And so that will be。😊，And interaction that Ka C， whatever that is， interacts with Sa。

 But in this case， the SA is coordinated with the KA and the KB。

 So it's also going to end up interacting with those two other things as well。

 And so you can use the sort of sentence structure patterns of a dependency pars to be getting out the kind of facts and events that you're interested in for something like an event understanding system。

 People you know， do these kind of analyses over biomedical text to build up the kind of structured databases of known protein protein interactions and things of that sort。

😊，Okay， so linguistic structure is useful。And it's syntactically very ambiguous。

 And so you sort think of humans as active interpreters that are using their contextual knowledge。

 both of earlier stuff and the text， knowledge of the world around them。

 how the world works to work out the right structure。 Yeah。

 so now I want to go on and show you a bit more about sort of dependency grammars。

 which is what we're going to be using。 So for dependency syntax that it postulates that you can capture the structure of a sentence by having these。

😊，So asymmetric dependent relations， which we might just call arrows。

 which are going from heads to dependence。 So here， the sentences。

 bills on ports and immigration were submitted by Senator Brownback， Republican of Kansas。

 And we sort of picking out heads。 And then we got things that depend on them that modify them。Yeah。

 so if you're on the video audience and you were educated in the United States and you're over the age of 50 or if you happen to go to one of those kind of private schools where they also teach Latin。

 you might have seen sentence diagraming。 So read Kellogg sentence diagraming was something that was actually very widespread in American education。

 which really was it was a it was really dependency grammar or it sort of a somewhat quirky form of dependency grammar where you had to write lines at different angles and stuff like that。

 but basically youre writing sort of heads in their dependence underneath them with different funny shaped lines。

 it also was dependency grammar。😊，Okay， so this is the start of a dependency grammar。

 But just like the the funny angled lines of sentence diagraming。

 normally people want to add some more information than that。

 And so most commonly that the arrows then typed by giving the name of some grammatical relation。

 So something can be the noun subject or an alique or an a or modifier or a case mark or things like that。

😊，And。I I'm just trying to give you the idea of dependency grammars。

 I'm not expecting you to master all of these names and ways of doing things。 And， you know。

 there are different systems of deciding what's heads and dependence and not all the details are important。

 what you should get into your head is just sort the basic idea of what one of these does and some sense of。

 oh， it should be at the phrase level， it should be representing what's modifying what。

 So we do actually ask some questions on the assignment。

 And so for the cases like the prepositional phrase， what is it modifying。

 you should be able to give the right answer to that。Okay。Yeah， okay。

 so this is just a little bit more vocabulary。 So yeah， we have these arrows or dependencies。

 And so I'm going to say that they connect between a head and the dependent。

 But sometimes people use other words like governor and modifier and things like that。

 And so dependencies generally taken and we' be taking them as forming a tree。

 So you've got something that's connected a cyclic and has a single route to it。

 So our single root is the top of the sentence here。😊，So。Depenency。

 so although what you see most often these days， either in a linguistics class or when you get taught C S 103 at Stanford or computer science。

 what you see there is normally context free grammars or free structure grammars。 I mean， really。

 you know， it is dependency grammars that have the really long history。

 So really the predominant way of representing the structure of human languages throughout human history is dependency grammar。

 So who linguists herald as the first dependency grammararian or really the first person who tried to write the grammar of a human language period was Paroney。

 So Paroney was working with Sanskrit。 Paroney lived so long ago that actually people don't really know when he lived。

 I mean， he lived somewhere in between about the fourth and 8 century before the common era。😊。

But really， no one knows when but， you know， he lived sort of up in part of actually what's now Afghanistan and for motivated for largely religious reasons。

 he said about developing a grammar of Sanskrit。 And the way he represented the syntax of Sanskrit was using a dependency grammar。

 So there was a lot of work on grammar and Arabic and the first millennium。

 they used dependency grammars in contrast， the idea of sort of having context free grammars。

 that's really， really recent。 So the first work on free structured grammars dates to the 40s。

 and then was sort of canonicalized by the work of Chomsky in the 1950s。 Yeah。

 so its a fact for the computer science， part of people in the audience。

 So computer De computer scientists。 if you know about Chomsky computer science。😊。

normally know two things about Chomsky。 One is they hate on the Chomsky hierarchy that they're forced to learn in CS103 or equivalent classes。

 and the second one is he's a very left politician But if I only deal with the first one of the two now。

 the Chomsky hierarchy was not invented either to torture elementary computer scientists or to explain fundamental facts about formal language theory。

 the Chomsky hierarchy was actually invented in thinking about human languages because at that time and in stuff that's come more often。

 it was commonly the case that people were modeling human languages with regulars。

 so finite state grammar equivalent mechanisms and Chomsky wanted to argue that that was a completely inadequate。

Formalism to represent the complexity of human language。

 And so it was in the context of arguments about human language was why he developed the Chomsky hierarchy。

Okay， yeah， so anyway， that's enough of the history of that。

 Here's my picture of part of Paroneney's grammar。 but actually， or a version of it。

 actually this is really， really misleading。 because one of the astounding facts about Parone's grammar and part of why no one knows what century he lived in was Parna's grammar was composed orally。

 So this sort of kind of blows my mind。 you know， it it seemed you know。

 some of the famous things in the West like Homer's works， the Odyssey in the Iliad。

 They were originally oral works that were passed down in oral form。 you know。

 you can that seems hard to do， but you can kind of believe if you did plays in high school or something that someone could memorize the odyssey。

 perhaps but the idea that people could。😊，Memorize a grammar of a language for passing it down for hundreds of years。

 kind of blows my mind。 But that's exactly what happened。 Yeah， with Paroney's grammar So you know。

 really， although this is sort of an old birch bark manuscript， you know。

 that really it probably dates from about a millennium after Paroney composed his grammar。 Okay。

 getting back to the modern days。 yeah， so， for things to know yeah， so， I mean。

 we don't want you to fixate on the sort of details， the dependency grammar structure。

 providing have the rough idea。 But just one thing that you can possibly be confused about is。

 you know， people do things in different ways， one way in which they don't agree is even which way to draw the arrows。

 So some people draw arrows from the head pointing at the depend。😊。

And there are other people who draw the arrows starting at the dependent and pointing back at the heads。

 So for modern dependency grammar largely follows the work of Lucant Tier， a French linguist。

 he did the arrows pointing from the head to the dependent。

 And so that's what I'm doing today but you'll see both。

 we sort of said that you know normally you assume that you have a tree with a single root。

 it's kind of common and it works out more easily for the passing。

 if you sort of add to a sentence is sort of a fake root node。

 So you know that that's going to be the starting point and it's going to take one dependent。

 which is the word that's the head of the sentence and then you're going to work down from there。

Okay， so。Before getting more into doing dependency passingsing。

 I just wanted to sort of take a little detour to tell you about the you know。

 the importance that happened with sort the rise of annotated data in natural language processing。

 So and you know， this is sort of an interesting flipflop that's occurred。

 But we're going to sort of today go in one direction and later class will go in the other direction。

 So in early natural language processing， people started to see all human languages have structure。

 So what we should do is start writing rules for the structure of human languages。 And you know。

 I start writing a few contextfr grammar rules for the structure of English on that early slide。

 and you could also write dependency grammar structure rules。

 So people tried to do natural language processing。😊，By having rules， grammar rules。

 dictionaries or parts of speech and things like that。 And that gave you pause that。

In retrospect worked out pretty badly， and it worked out pretty badly for a number of reasons。

 One reason is that although there are these sort of very canonical。

 clear structures in human languages， there's a very long tail of messy stuff where all kinds of weird usages start to emerge in human languages which sort of means you just got this。

 it's just really hard to get coverage for handwritten language。

 and that's because people you humans use language creatively， right， So， you know。

 you can start thinking of some of the things。That you've probably come。

 I'm probably not very good at young persons sling usages of grammar these days。 But， you know。

 the kind of ones that you might be still familiar with， right， Star Wars。

 you have Yoda talk where you rearrange the sentences。 But people still understand them， right。

 So that's changing the word order and earlier on than that。

 there was sort of a bit of a fad to putting not at the end of the sentences that's a really great idea。

 not。 And well， you know， people learn to understand that。 but it's different regular grammar， right。

 So it's really hard to write a full grammar。 But the bigger reason actually is the problem of ambiguity I talked about。

 right， that if you just write a grammar， well， you know。

 my sentence with the prepositional phrases had 13 different par。

 and you didn't have much reason to choose between them。 But， you know， if you had information。

About how often words modify other words， then you could get some statistics and start to predict in which order which things modify other things。

 And so people wanted to start to be able to do that prediction that underlies probabilistic or machine learning models And so to be able to do that that led you know。

 sort of earliest antecedents in the 60s， but really starting in the late 80s and into the 90s that people decide。

 geee， the way to make progress in natural language processing natural language understanding is to build annotated data resources。

 And so all through the 90s and the 200s decades， the name of the game for a lot of natural language processing was people building annotated data resources and then building machine learning systems on top using those resources。

 Now that's kind of gone into reverse and gone away again。😊，large language models。

 which we'll get to in another week or so。 But here's an example。

 So this is the universal dependencies tree banks， which I'm actually been heavily involved with。

 And it's a cool resource for all kinds of purposes。

 because it's actually a wide crosslinguistic database where there's over 100 different languages with sentences passed with a uniform dependency formalism。

 So it's actually really good for things like crosslinguistic work and psycholinguistic work。

 But you know， what these are is taking sentences。 I think Miramar was a famous goat trainer or something。

😊，And putting a dependency structure on it， it's sort of all written there。

 sort of very squish down and human beings are producing these dependency structures。

 And then this is giving us data that we can learn things from dependency like dependency PAs from。

 And indeed， for what you do in homework too。 This is precisely what you'll be using is data of this sort to build a dependency PAer And it's going to learn that。

 you know， that you have goat trainers。 and you have famous trainers And so it'll build up sort of statistics and information to predict what kinds of things are likely。

😊，Yeah， so starting off， building a tree bank like that。Feels kind of like。

 oh this is going to be slow hard work。 And it is actually slow hard work。

 but it proved to be a very effective strategy because it gave wonderful。

 reusable resources that once people are done at once。

 all sorts of people could use it to build parers， part of speech tags to do psycholinguistic models and all kinds of things。

 Youd get the sort of distributional frequency information that's good for machine learning。

 It also provided one other thing that's crucial is it gave a method to evaluate systems to say how good they are at producing parers。

 I mean， this may seem kind of comical to you in the modern era of machine learning。

 But the fact of the matter is when people did natural language processing in the 50s，60s，70s。

 nobody had a。😊，Uation methods， the way you showed people。

 you had a good PAser is you ran the program。 You said， type in a sentence， look at what it look。

 look has worked。 It's a really good PAer。 You know。

 there was no systematic valuation of NLP systems whatsoever。 So actually saying， look， here's。😊。

Thousand hand par sentences。 Let's evaluate how well your parer does on those。 You know。

 that was actually a revolutionary new development that happened in the。😊，Well， ended the 80s。

 but especially in the 90s。Look， hey。So now we're going have it now that we have all of those knowledge。

 we're going to want to start building dependency par。

 And so I'm going to show a particular way of dependency parsing。

 which is the one you're going to use in the assignment that， you know。

 just first of is' sort of worth just thinking for a moment。 You know。

 what kind of information should a dependency parer have to make decisions。

 So these are kind of the four factors， the sort of the obvious things that useful for dependency paring。

 I mean， the first one is sort of thinking of the two words at the ends of the arrow as to whether they are plausible。

 right， So that for discussion of the outstanding issues was completed。

 So to have discussion of issues， right， That's that's a plausible dependency， to have。You know。

 what's a silly one to have something like the being a dependent of completed that makes no sense at all。

 So you know what words there are involved。 the second one is dependency distance。

 So you can have long distance dependencies that go a long way。

 But most dependencies are short distance。 You know。

 a lot of words are depend on their neighbouring words that a very short distance。

 So that's a good preference to have。 as well as just the distance。 It's somewhat informative。

 knowing what's in between。 So it's rare for dependencies to span verbs or punctuation。

And then there's a final one， which is to think of the valency of heads。

 And that's how many arguments they take。 So that if you have sort of something like a verb broke。

 Well， it probably has something。 to the left because it probably has who did the breaking。

 And it probably has something to the right， because there might be the cup or something like that。

 But， you know， it doesn't have to be that because it could be the cup broke。

 So you can have something to the left， but nothing to the right。

 but you sort of have to have something to the left。 And conversely。

 you can't have any number of things。 you can't sort of just say he broke the cup。

 the saucer the dish right， So it doesn't take just lots of arguments to the left。

 So you've got a notion of vency like that。Yeah， there's one other tricky little notion on dependency parsing。

 which is normally， normally dependencies kind of nest like this。

 and nesting dependencies corresponds to a tree structure， as you'd have in a context free grammar。

 yeah。给。I at this。Its word。Because in a sense， when I read the sentence， which is。

Or I thought that the most。Thiscus。 so if I can see your arrows and。So。So I will as fair enough。

 I will assert that this is。Sentence and discussion is the subject of the verb。Completed。 and。

 you know， normally for a sentence， we say the main thing in a sentence is its verb。 And so， yeah。

 so that's why the root is heading to completed。 And the subject of the verb is also an important thing。

 But the arguments of the verb， like the subject of the verb。 The object of the verb。

 There is one preal phrase modifiers。 They're all taken as dependence of the verb。嘢最多一。

Following up on that ist safe。I when is it not？They you start。哦， sorry。

If you have a sentence with a verb like this， it's always， that is always the answer， I mean。

 some of the details here depend on languages， but there are languages in which you don't have to have a verb in a sentence and you can get things like。

嗯。I mean， you can do it in sort of very restricted ways in in English， right。

 So if you just sort of say easiest pie， there's no verb。 And so then you're saying easy。

 the adjective， which is sort of the preddicate adjective， is then the head of the sentence。

Sorry with like a question， like what is the story is the is like we would still look at that as the。

That one isn complicated。 Some people would say it is。 And some people would say it isn't。

 And in particular， in universal dependency， we don't actually say that is as the head of the sentence。

 But I don't want to get too far into this。 If you want you could sort of look more at how things are done。

 But， you know， I want to fully admit that， you know。

 dependency grammar isn't sort of one uniquely defined theory。

 People have had different ideas of which things to take as the head in various circumstances and they argue about it。

 linguists argue about what the right structure is to put over all sorts of sentences。

 But that the fact that people do things different ways doesn't mean that everybody doesn't agree that there are units。

 There are phrases and modifiers and ambiguities and so on between them。Okay， yeah。

 so normally we get this sort of nesting that corresponds to what you can build with context free grammar structure。

 But sometimes in human languages， you get dependencies that don't nest。 So you get sentences like。

 I'll give a talk tomorrow on your networks where actually the on your networks is modifying the talk where the yesterday is an argument of sorry。

 the tomorrow is an argument of give。 And so you get these crossing dependencies which are referred to as nonproive dependencies。

 you also get them when you form questions So who did bill by the coffee from yesterday that the who is the object of the preposition from that it's been moved out the front。

 And so that again， gives us nonproivity。If you think about it。嗯。Yeah。

 you can still say that you have a dependency tree， but it's got the words in different orders。

 And so one of the things that you have to cope with for full dependency parsing is dealing with this non- projectivity。

 But I mean， actually， we're not going to deal with it in our par。

 We're only going to do projective dependency parsing。Okay。

 so there are various ways that people do dependency parsing。

 People have done it by dynamic programming， people who've done it using graph algorithms。

 If I have enough time at the end， I might mention that again。

 people have done it with constraint satisfaction methods。 If you saw those in C， S 2，21。

 But the most common way in practice that's emerged has been this transition based parsing。

Which is kind of sort of interesting as well and gives us of a very simple machine learning mechanism。

 So it makes it good for an assignment too。 And so that's what we're going to explore here。😊，Okay。

 so。What we do in greedy decisionbased parsing and transitionbased parsing is， you know。

 this is where unfortunate that only two people in the class have done a compilers class。

 So so a simple form of parsing that's also used in compilers classes。

 something called shift reduced parsing where you start sort of bottom up and you start putting little units together and build bigger constituents。

 But if most people haven't seen it， that's not going to be very much help。

 So I'm going to give you a concrete example。 So the things to know is wed have two data structure。

 we have more than two， I guess， for dealing with the sentence， we have two data structures。

 we have a buffer， which has the words of our input sentence。

 And then we start building pieces of sentence structure， which we put on a stack。

 and a little trick to know that。😊，For the buffer， the top is written to the left and for the stack。

 the top is written to the right。 And so we take actions which are like shift and reduce actions。

 And when we take arc building actions， we build up a set of dependency arcs。

 which are going to be the dependency structure of our sentence。 And that's all incredibly abstract。

 And so I'm going to show an example， which hopefully will a bit give the idea。😊。

So here's an example， so I want to do this very simple example of passing up the sentence，I ate fish。

😊，So。ISo the way I do this is I have my stack， and so I start by putting the root symbol on my stack。

 and then I have in my buffer all the words of the sentence。

 And so that's the sort of start condition I've written in very small print there。

 Then for each step of processing。 I have a choice of three operations。

 I can either shift which moves the top word on the buffer onto the stack。

 or I can do left arc or right arc。 And these are my two reduce operations that build a little bit of syntactic structure。

 by saying that one word is a dependent of another word in either a left or a right direction。

So here are a sequence of operations I can take。 And so starting off。

 the first thing I can do is shift。 So then I've moved I onto the stack。

 I can decide that I want to shift again。 And so then I'd take8 and also move it onto the stack。

 And so I've now got three things on my stack。😊，So at this point， you know， I can do other things。

 I mean， in particular， a left arc is going to say， well。

 I can take the top two things on the stack and make the thing on the top the head and the thing one down on the stack a dependent of it。

 So if I do a left arc operation， I'm effectively saying that the I is a dependent of8。

 and then I pop both of then I pop the dependent off the stack。

 but I add on that I've built a dependency that I made I a dependent of8。

 I could then do another shift operation。 So I shift fish from the buffer onto the stack。

 and then I can do a right arc which says okay， I'm going have fish as a dependent of eight。

 So then fish disappears from the stack。And I add in this new dependency。

 saying fish is a dependent of8。 I then do right arc again。

 which is then saying that8 is a dependent of root。 So I'm left with just root on my stack。

 and I built a new dependent saying8 is a dependent of root。 And at this point。

 I've gone to the finishing condition。 My finishing condition is that my buffer is empty。

 and my stack contains just the word root。And so this gives me a little set of operations referred to as the transitions of transition-based passing and by making a sequence of these different transitions。

 I can build sentence structure and I've got choices of when to shift and when to reduce and whether to reduce left or reduce right。

 the arc left arc right and so by making different ones of those choices。

 I could make any structure for the sentence that I wanted to So you know if I somehow thought that this sentence should have a different structure and that I should be the head and as are dependent of that and fish is a dependent of that well I could achieve this by making some different choices as to I'd now be saying I was doing a right arc operation so that eight would become a dependent of I rather than the other way around so the。

😊，This of which operations I take determine the syntactic structure。

 the set of dependencies that I have built， which are my set of dependencies down here。 Now。

 the sentence of dependencies I built were exactly the right ones because at each step。

 I took the right operation。And so the essential idea of transition based passing and where it came to the fore was。

There was a particular guy whos I've got a photo of him in somewhere in a bit。 I thought。

 So Youm Nera is a Swedish N LP person。 And in the early 200s。

 he came up with the idea of rather than doing the kind of dynamic programming and chart parsing and things that people commonly used to do with PAers。

😊，These days， we have machine learning。 So maybe we could build a fast efficient parser。

 And the way we're going to build it is with this making a sequence of transitions and itll be the job of the machine learning to predict what is the right transition at each point in time。

 So if you do that， you know， at each point you're dealing with one thing。

 And so the number of operations you're doing to pars a sentence is linear。

 So this gives a linear time parsing algorithm。 whereas if you've seen contextfr grammars and stuff like that and Cs 103。

 and you' want to do anything where you're fully considering the parss and structures of contextfr grammars。

 you've then got a cubic time algorithm， which is much less pleasant to be dealing with。😊。

So for the simplest form of transition-based parsing， you do no search whatsoever at each step。

 you're just predicting the next transition and so you're doing this sort of sequence of transition predictions as machine learning operations and that sequence gives you the par structure of the sentence and the essential result the Nehrora is able to show is that machine learning is good enough that you can do this and get a very accurate PAser despite the fact that it does no search whatsoever is just doing predictions in this way。

😊，Okay。So how did so when he did in 2005， that was before neural networks came to the fore。

 And so the way he was doing it was by using sort of an older style symbolic featurebased machine learning system。

 So he had a big classifier， which might have been a logistic regression classifier or something else like a support vector machine。

 And so to power that， he was using indicator features。

 So the kind of features you'd use is that the word on the top of the stack is the word good and it's part of speech as an adjective。

 or the word on the top of the stack is good。 but the word that sort of。

Second on the stack is the verb has right You'd get these sort of combinations of matching functions。

 and they would be used as features in a machine learning system to predict the pars。

 But the problem is that once you started building these features that were conjunctions and multiple terms。

 you ended up with millions and millions of features， right。

 because you're putting particular words and features and then you're combining choices of multiple words。

 So they're just millions and millions of features。

 So you had to deal with millions and millions of features。 And furthermore。

 individual features were exceedingly sparse that you barely ever saw them right。

 that you'd have a feature that only turned up you know。

10 times and millions sentences because they were matching these very precise systems。

 So on the one hand， by making these feature conjunctions。 parsing got more accurate。 and indeed。

 people produce pretty accurate pars。😊，In those days。

 but they had some of these unappealing characteristics of this sort。Yeah。

 so before going on further， I should just explain how we evaluate dependency passes。

So to evaluate dependency passes， we're basically assessing， are you getting the dependency arcs。

 arrows you're proposing right， So here is someone's dependency pars。 She saw the video lecture。Well。

 actually， sorry， that's the gold pars。 Okay， that's the correct pars。 Okay。

 she saw the video lecture。 That's a correct par。 So you can write out what are the the different dependencies。

 right？ So one's head is2，2's head is 0， word 3's head is 5， words 4's head is 5 word 5's head is 2。

 So these pairs of numbers represent our dependencies。

 Then if someone proposes a pars of the sentence， you can literally say， okay。

 which of these did they get right， So they didn't get this one， right。😊。

They got the rest of them right。 So their accuracy are 80%。

 And so sometimes people just assess the arcs unlabeled。

 And so that's referred to as unlabeled dependency accuracy。

 But sometimes people also want to label them with subject， determiner， object， etc。 and say， also。

 are you getting the labels right。 So in this case， only two of the five labels are right。

 So the labeled accuracy of the dependency passes is 40%。Okay。So。

So that was sort of what people did until the mid 2010s。 And I sort of already started saying this。

 the problems with indicator features were they were sparse， you didn't see them often。

 they were incomplete because there are some words and combinations you'd seen and some you just didn't see in the training data。

 So youre missing features。 But the final problem is actually just computing all those symbolic features was just expensive。

 It turns out that if you did runtime analysis， most of the time in the pars wasn't in doing the machine learning decisions。

 it was just simply in computing the features that you put into this dependency parser。

 So as neural net started to show that they were successful for things。

 that suggested that maybe you could build a better dependency PAser by using a neural net。😊。

Transition based dependency par， which would benefit from the kind of dense and compact。

Feature vector representations that we've already started to see。

 And so that's what started to be explored。 and in particular。

Who was then a PhD student of mine and was head T A of 224 and twice actually in the earlier days。

 So she built neural transition based dependency PAser and showed the success of this method。

 So this was Nra's transition based dependency parser。

 people had also explored other methods of dependency parsing。

 So these were two graphbased dependency pars。 And essentially for the kind of symbolic feature。

 machine learning methods。 Nra's PAser was really fast because it was using this linear transition-based parsing idea。

 The dependent the graphbased dependency pars were way， way slower。 you know。

 they're about 50 times slower。 But they were slightly more accurate。 You can see here that。😊。

ing a bit better numbers。 So essentially， what was able to show was you could build something that was basically as accurate as the best known graphbased dependency parsers。

 But it was fast like other transitionbased vss。 Indeed。

 despite the fact that it you might think that now I've got real numbers and matrices and stuff。

 Sure that should be slowing me down。 The reality was that the symbolic models spent so much time and feature computation that actually you could make it faster at the same time by using the neural network。

😊，Okay， so how did that work？ Well， so we've already seen word embedding。

 So it's going to exploit word embedding。 so it can use word representations。

 And that has the advantage， even if you haven't seen particular words and particular configurations。

 You've seen similar words。 And so it can exploit what's likely in terms of word similarity。

 But it went a bit further than that， because why only have distributed representations of words。

 we also have parts of speech。 And although I sort of said just noun verb adjective。

 most actual systems in NLP of parts of speech are much more fine grained。

 So they have different parts of speech for plural nouns versus singular nouns。

 So they're sort of different symbols， but they're very similar to each other。

 So we might give them distributed representations。 So theyre also close to each other。

 And the same for the types of our labels for depend。😊。

Some of them are pretty closely related as well。 So all of these were being given distributed representations。

 And so then to represent the state of the dependency parza， for predicting transitions。

 what you were doing is you had the same kind of stack and buffer and you are taking the key elements of the stack in the buffer。

 which are essentially the first thing on the buffer。

 the word that you would be shifting if you're going to do a shift and the two things at the top of the stack So these are the things that if you're either doing a left arc or a right arc。

 their things that you're considering combining。 So for those。

 you're going to be taking the distributed representations of the word and their parts of speech and also with a bit more complexity for dependencies you've already constructed if maybe something on the stack is already involved in the dependency。

 each of those we going to take their distributed。ationsAnd we're going to just concatenate them together to produce a big vector in the same way。

 we're concatenating together。 The five words in the last class for predicting whether something was the location or not。

 And then we're going to feed that。😊，Into our neural network。

 So we our input layer is our concatenate distributed representations。

 We are going to put that through a hidden layer， which is like we were talking about last time。

 W X plus B， then put through a value No nonlinearity。 And then we are going to put above that。

 the same kind of another multiply by a matrix。 So we've got a second layer of neural network。

 UH plus B2。 And we're going to take the output of that。

 And then we're going to put that through a softm that gives a probability distribution over whether to shift or do a left arc or a right arc operation。

😊，And so the other way that this crucially gave us more power is that other people's dependency parers were still using linear classifiers。

 things like support vector machines or logistic regressions where we had a deep neural network that gave us a non nonlinear classifier。

 and so that's why we could be more accurate than other previous transition based parers。

 And so this essentially showed that。😊，You could build this very accurate neural dependency parser and that it outperformed symbolic probabilistic representations and basically was as good as any other dependency parser that was known。

 So back a decade ago。 This was a big hit People got very excited about it。

 The people at Google got very excited about it because this gave a scalable way。

 Remember it's linear time in which you could efficiently go off and pass the entire web So they did some further work on taking that model。

 improving it so that they made a deeper neural network version with bigger vectors and better tuned hyperparameter。

 And they added on to a beam search。 I've just presented the greedy version where you always just immediately make the best choice。

 but you can improve these pars。😊，By doing some amount of search that does help。

And so they pushed that up。 And so rather than our kind of 92 UA S here， they got it to， you know，94。

94。6。 And， I mean。You， you're probably all too young to remember this。 But， you know。

 really at the time of 2016， you know， Google did their kind of typical big PR PR splash for dependency PAser。

 which kind of blew my mind。 since I didn't ever think that anyone was really gonna be writing articles and wired and venture beat and those kind of tech blogs。

 But， you know， Google had it all over the place of the world's most accurate PAser。

 and they gave it a silly name。 Parsi MPs face， which really worked well forgetting lots of media pickup。

 And so that was then a very successful PAser。😊，嗯。I've still got a couple of minutes left。

 So let me just do the last three slides to show you sort of another way of doing things。

 which is also actually also a powerful parsing method that is commonly used。

 So that was transitionbased parsing And that's what you will use an assignment to。

 another way of doing things with dependencies and parsing that can be done neural。

 iss what's referred to as graphbased dependency parers。 And in graphbased dependency parers。

 What you do is for each word you sort of asked for each word。

 what am I a dependent of right So if the sentence is the big cat SAT， each word， for example， big。

 has to be a dependent of one of the other four words in this sentence。

 including this possibility of root。 So we ask， am I a dependent of that， am I a dependent of root。

 am I。😊，Depenent of cat。 am I dependent of satAT。 And we want to score each of those possibilities。

 And so hopefully we decide that the most likely one is the big as a dependent of cat。

 And then we're going to do the same for every other words。 So you know。

 SAT could be a dependent of any of these words。 And so we could start asking， okay。

 which of these words， Is it most likely a dependent of be to S， cat to S。 sorry。

 that's unreadable now。 But hopefully we decide， the SAT most likely as the verb。

 Is a dependent of root。 So were sort of scoring the n squared possible， you know。

 dependencies of descend sentenceants。 each one is given a score。 And then once we've done that。

 our job is。😊，Let me go to this one's cleaner。 Okay， we've decided the good one there。

 And so we're going to do this using some of the same features we talked about。

 looking at the words at each end， looking at what occurs between them。

 looking at what occurs around them thinking about things And then once we've done that。

 the only other thing that's a constraint is well we want the dependencies to form a tree。

 So that we need to do something like a minimum spanning tree algorithm to sort of find the minimum cost tree because we don't want to find a solution where there are cycles or the parts of the sentence end up disconnected with each other。

 And so that's graphbased dependency parers。 And so just as in the older symbolic parsing days where the graph-based dependency parers were more accurate than the transitionbased parers。

 that we then started doing some work on neural。😊，Grabased dependency parsing。

 And so here's our neural graphbased dependency parsing。

 which was then a bit over a percent more accurate than parsic PAs face。

 the world's best dependency pars。 so that got us to 2017。 I mean， obviously。

 this is still a few years ago。 but to get further into the latest parsing stories。

 we then need to sort of get into the era of large language models， which I'm not doing today。

 But as this neural graphbased dependency parser。 that's in stanza。

 our open source parsing software that's available and that you can see。

 It's using this algorithm as the more accurate one。 Okay。

 so now you hopefully know everything about syntactic structure， constitus， Inency parsing。

 And are fully qualified to do a assignment too。 So good luck with that。 Thanks。😊。



![](img/ff5b0ccbb341c33606125428d1852278_3.png)