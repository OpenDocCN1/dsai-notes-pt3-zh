# Stanford CS221 ｜ Autumn 2025 p16 Stanford CS221 ｜ Autumn 2025 ｜ Lecture 16： Logic II [x9Mbqu06OVo] [BV1XuPrzwEes_p16]

![](img/83192f817d97f718d400a1e6182cd60f_0.png)

![](img/83192f817d97f718d400a1e6182cd60f_1.png)

All right， so welcome back everyone， this is going to be the second of the two logic lectures。

 we're going to talk about first order logic and this is where you really get to see logic shine and do something interesting。

And to motivate why logic is useful， I'm going to go through an example。U。So in this example。

 I'm going to build up a knowledge base of facts， and I'm going to ask you to really pay attention and follow along and do some logical reasoning yourself。

Okay， so here each fact I'm going to write the natural language sentence。

 Alice is a student and I'm going to write also the first order logic expression now I haven't told you what first order logic is so we're just going to go through intuitively but just pay attention to maybe the natural language。

Okay， so Alice is a student。This is written student of Alice in first shorter logic。

Aliceism from Phoenix。So from Alices， Phoenix。Phoenix is a hot city。

So hot applies to Phoenix and also City applies to Phoenix。Stents are people。Okay， so for every。X。

 if x is a student， that means x is a person as well。Cities are places， so the same thing。

 but city of x implies a place of X。If it's snowing， it's cold， so this is just propositional logic。

 but first solar logic is a super set so we can do that too。Okay。

 so now the first question I'm going to ask you， is it snowing？Yes or no， or I don't know。Okay。

 I don't know， okay， so we asked the knowledge base and the knowledge base says， don't know， okay。

 good。All right， so how about if a person is from a hot place and it is snowing。

 then they're not happy。Okay， so this will be represented like this， don't worry about it too much。

 so then is it snowing？Okay， I don't know。 Okay， what if we say Alice is happy。Then is it snowy？

You don't know or you don't know whether the answer is。You know， the answer is。

 I don't know or you don't know。It should be no。诶。So I'll let you put kind of pondered on this in your maybe offline。

 but this is an example of performing inference and first or logic。And as you can see， it's。

 it's quite powerful。 I give you a lot of sentences with a lot of hands and ors and implications and。

😊，You the question here is。You know what kind of sentences can firstorative logic represent and how can we do inference in them？

Okay so this is one example， but firstso logic is going to be able to represent any sort of complicated statement about the world and also allow you to reason about this and we also want it to be logically coherent。

Okay， so this is sort of a tall order， right， Imagine like any sentence you can you know write down。

 we want to be able to do reasoning with that。 I mean。

 as it turns out that first order logic isn't powerful enough to do all sentences。

 but it goes quite far， as we'll see。Alright， so let me just review logic。

 So last time remember we talked about propositional logic， but more importantly。

 I think it introduces the basic way you should think about logic。

 which is a language for representing knowledge and reasoning with it。Okay， so to define our logic。

 we need to define its syntax， semantics， and inference rules。

So the picture you should have is that there's syntax La， these are just symbols。

And you can perform inference ruless on these symbols。 They generate more symbols。

But what in order for these symbols and mean something， we have to define a mapping。

Known as an interpretation function that takes formulas and says。

 what statement do they make about the world？Okay， and。Later， we saw a soundness and completeness。

 which tells you how these inference roles relate to the actual reality。Okay。

 so maybe just go through the different concepts， so remember last time there were a lot of different concepts that build on top of each other。

So the first is。You know， syntax， what are the valid formulas and propositional logic。

 we've started with the primitives which are propositional symbols like P or Q or rain or whatt。

Then we can given these symbols， we can recursively combine them using logical connectives like and or not implication and bidirectional implication。

 so we might build rain and not wet。Okay， so these are remember， these are just symbols。

And in order to define say what define the semantics， we have to say what these formulas mean。Okay。

 so in propositional logic， a model is assignment of true values to propositional symbols。

 So here is a possible model Ra is true， white it is not true。And so a model。

 also you can refer to it as a world is a possible situation that we might be in， it's raining。

 but it's not wet。There are many models， and in general。

 the way to think about it is we don't know which exactly which world we live in。And by。

 and then logic allows making formulas allows you to basically。Express。

 which are the constraints on the possible worlds。So we given the models。

 we have an interpretation function which takes a formula and a model and returns essentially whether this formula is satisfied by that model。

In this case， this is true because the formula is rain and not wet， and the model is rain。

 rain is true and wet is false。If you had the formula wet。The result would be false。

If you have the formula train， that will be true。Okay。

 so interpretation function in sense is a bridge between syntax and semantics。

And the way we use that is we define a set of models， M of F， which。Says given a formula。

 what are the possible worlds that we might live in？Okay， so in this case。

 it's just the one possible world which train rain is true and wet is false。

Then we talked about knowledge bases， which is a set of formulas。

 so you should have in your head over time an agent acquires knowledge and it just adds formulas into this knowledge base。

 so for example it might know that it's raining， it might also have the general rule that whenever it's raining it's wet and then what you do is you have a new formula and you think about the relationship between the knowledge base and the new formula。

So the two things to。Keep in mind is that we have the original knowledge base that defines a set of models。

 which is the intersection of all of the models of the formulas。

 So these are the possible states of the world that are consistent with all the knowledge。

And then we look at what happens if we add F to the knowledge base。What models do we get？

So and based on the relationship between old models and new models。We， there's three possibilities。

 One is that they're equal， and that's entailment。And this means that F did not add any more information over KB。

And in this case it is entailment， wet is entailed by and rain implies wet。

It could be a contradiction， meaning that there's no possible states of the world that u no possible worlds that satisfy both the knowledge race and F。

And otherwise， it's a contingency， which is that the intersection is not empty and it's also not the original set。

Okay， so these three notions are used to implement ask ask function and a tell function。

 So ask checks whether F。呃。Is entailed or contingent or contradiction with the knowledge base。

 so this is asking yes or no questions and tell is you're trying to add F to the knowledge base and you're only going to do it if it's contingent because it's not contradicting and it's also adding you information。

Okay， so then we talked about how we can。So do inference by reducing everything to satisfiability。

So KB is satisfiable if it's sort of self consistent。

So when you model checking is the task of taking a knowledge base and determining whether it's satisfiable。

 and given that primitive， we can reduce entailment。

 contradiction and contingency to two implicationsvocations of satisfiability。

We add basically F into knowledge base， see what happens。If its if it's。You know， not satisifiable。

 then we say it's contradiction。 and we add not F into KB and see what happens if if M of that is empty。

 then we say it's entailment， otherwise it's contingency。Okay， finally。

 we talked about inference rules， which is how do you derive new formulas given existing ones。

 the set of rules remember operates on the syntax and we' talked about the moduspons。

 which is this particular rule template。If you're given a proposition of a symbol P and you're given a formula。

 P implies Q， then you get to derive Q。Okay， so。If it's a rain and rain implies wet。

 then you can derive wet。So then there's two notions here in the syntax， you have a knowledge base。

 it's a set of formulas and you can do these apply these rules over and over again。

 and if you can generate a particular formula， then you say the knowledge base derives or proves that formula。

Over in semantics land。You say that knowledge base entails F。

 and this is just by definition whether the models that are denoted by the knowledge base is equal to the models that are denoted by the knowledge base with F。

喺。😊，So these at the surface are very， very different notions。

It's not even clear what these have to do with each other。

And so the relationship is given by these two properties。

 Soundness is the property that if the knowledge base。

Can derive a set of rules can be used to derive F given a knowledge base。

 Then F is entailed by the knowledge base。So remember the glass。

 glass is the truth and soundness means that you're staying within a glass。If every time you you。

You add some water， it stays within the glass， it's true。

And completeness is saying that whenever you're filling up the glass。

So whenever a formula is entailed， you also can prove it。Okay， and ideally， you want both you want。

Soundness， which is nothing but the truth and completeness， which is the whole truth。Okay。

 so that's where we left off last time。So let's talk about why propositional logic isn't good enough。

And just to motivate this， let's just try to represent some facts in propositional logic。

So let's say we have a sentence， Alice and Bob both know arithmetic。So in propositional logic。

 remember， all you have is propositional symbols。So you might define a propositional symbol。

 Alice knows arithmetic， and Bob knows arithmetic， and you define a formula which is at the and of the two。

Okay， so， you know， it works。 seems like， okay， fine it works。

 What if you have a sentence like you want to represent the fact that all students know arithmetic。

Okay， so then you might say， okay， Alice is a student。 Bob is a student。 These， these are。

These are symbols and then you define a formula which says。

 and Alice a student implies Alice knows arithmetic and Bob is a student implies Bob knows arithmetic。

 but the problem is that if you have more student if you have1 thousand students。

 then you have a very large formula。Okay， so here's another example。

 every even integer greater than two is a sum of two primes。This is a codebox conjecture and。

In order to express this。You know now you have to， wait a minute。

 you have to list all possible integers and make them propositional symbols。

 This doesn't seem like a good way forward。 So remember。

 the goal of logic is you're representing very complicated things about the world in very compact ways。

 And this is a property that's shared by natural language。

 Language is very powerful because I can say a few words， and I can say very complicated things。

So we see that propositionit logic is very clunky and not expressive enough because all it has is these proposition。

 no symbols。So what's missing？What's missing is that we'll see that there's notions of objects and predicates。

 right， So Alice knows arithmetic is is just one monolithic predicate， which is either true or false。

But it has more internal structure， right， there's Alices， there's nose， and there's arithmetic。

So we're going to try to break that apart。 The other thing is。

It's missing in quantifiers and variables。 So all is known as a quantifier。

And this applies to all people or objects， and there's cases where you can't just enumerate all the objects。

Okay， in programming， this is kind of like trying to program without for loops。

You have to write down all the different cases， which clearly doesn't work。

So we figured out in programming that you need to have more complex languages rather than just。

 you know， I guess there's not really a language that doesn't have for loops that people really use。

Okay， so let's introduce first order logic now Okay， so remember in order to introduce the logic。

 we have to go through the syntax， the semantics and the inference rules。

 just like we did for proposition and logic， but now we're doing for first order logic。

So let's talk about the syntax。 Okay， so syntax， remember， is what are the set of all valid formulas。

嗯。There's going to be a bit more machinery here in propositional logic， formulas denote true values。

 so rain denotes either true or false， depending on what's happening in the world。

 in forced order logic， we still have formulas that denote true values as before。

 but we also have these things called terms which denote objects。So what is a term？

There's multiple types of terms。 There's first constant terms， It's constant symbols like Alice。

 arithmetic。These are not to be confused with propositional symbols。

Because prop symbols are formulas， they represent either true or false。

 Aliceice andrithmetic represent objects， either concrete objects or abstract objects。

Alice is not true or false。Okay， we also have variables。Like X and Y。And then we have functions。

So a function is something that takes01 one or more。You know， arguments and returns of a term。Okay。

 so we might have father。 That's a function Add that takes an object and returns the object。

 Add is a function that takes two objects and returns the object so we might now we can use。

Functions to build terms by passing in other terms as arguments， so Father of Alice is a term。

And add X， Y is a term。Okay， so you can also have father of father of Alice or add X， Y。

 and then you add Z， so you can imagine building this up precursively。And in particular。

 functions are take things that take terms and return terms。And remember a term denote an object。

Okay， so again， keep the object， the terms and the formula is separate。All right。嗯。

So now we get to formulas。So in propositional logic， atomic formulas were just propositional symbols。

 like rain or we。And now， atomic formulas are going to be a bit more complicated。

 They're going to be predicates applied to terms。 So what are predicates， These are not functions。

 but。Well， they are functions in a general sense， but they are things that take some number of arguments and returns true or false。

Okay， so snowing is a zeroerity predicate， Erity means that it takes zero arguments and returns either true or false。

 it is either snowing or it's not snowing。Student is a oneerity predicate。

 otherwise known as a unary predicate， it takes an object。And returns a bo。Okay， and nose。

Is a two area predicate， so it takes two arguments and returns a bull。So for example。

 you might have a formula that says nose x arithmetic。Notice that X and arithmetic are terms。

 So predicates take as argument terms， but in returns。A booleion。Okay。

 so after you define these atomic formulas， you can apply connect them together using connectives。

So this part is the same as proposition or logic， for example。

 you can have a student of x implies x nodes arithmetic。Okay so that is a formula。And finally。

 you have quantifiers that apply to formulas， so you can take a formula with a variable and you can put either for all x in front of it or exists x where x is some variable that shows up。

Okay， so just to San check， these are not formulas。So father of X is not a formula， it's a term。

 right， you think about father is a person， it's not a true or false。

ASt is no student arithmetic is not a formula or at least not a well defined formula because student is a predicate。

 not a term。 If I had student of X。Would that be your formula？The answer is no， right。

 because a student is a predicate which returns a bull。So if I take a student of x。

 that' a that just returns a pool， and here anything that gets passed in needs to represent an object。

睇。嗯。And then this is also not kosher for similar reasons。 So if you had a function foo。

 you can't take nose， Alice andrithmetic because nose is a predicate。So this returns bull。

And you cant a pass Boolean into。Into anything。Okay。

So anything that shows up an argument has to be a term。And。The alermost function。

It is for a formula has to return in a bowl。Okay， to help you。Remember。

 so there's a convention that we've been following， so we're using lowercase for terms。

 so which includes variables， constants， functions， everything's lowercase。

 and this represents a denotes objects， and we're using uppercase for formulas。

So nose is a predicate。So it returnsable， okay。So it's just a convention。 I mean。

 you can technically name them anything you want。Okay， so just to summarize， there's two things here。

 there's terms that denote objects， these are things like Alices， arithmetic， X Y， father of X。

 add X， Y， and then there's formulas which denote truth values。So for example。

 for all x student V implies knows x arithmetic。Okay， so that's the syntax of first order logic。

 any questions？So the question is， can a function return another function in first or logic no？

Functions have to return terms。So yeah， so this is in some ways， it's。

A much more restrictive language than if you're using Python。

 which you can like have functions I return functions。

 I return functions and anything goes first So logic is much more restricted。

 which allows you to be able to compute efficient， the more restrictive language it's easier to do stuff with。

 but less expressive。So can I explain no student arithmetic and why this is not a not formula。

 so student is a predicate。Right， so。And so it's not a term。

And only thing that can go here and here is a term。嗯。So this is a common mistake because you say。

 oh students know arithmetic， then if I ask you to write down the first order logic for it。

 the natural thing would be like， oh， you know， well Alice knows arithmetic。

 I just do know Alice' arithmetic， if student knows arithtic， I just put student in。

 but that's incorrect。Okay， so that's the syntax of first orderal logic。

 remember it's all logic languages in general define recursively right so you define the atomic formulas and then you say how you take these atomic formulas and you produce more bigger formulas。

And the difference in forceso logic is we have to introduce ideaF terms and build terms。First。

 get them to pradize and those are the neoatomic formulas。All right。

 so now let's talk about the semantics of firstso logic， So what do these formulas mean？

And we're going to follow the same recipe as of propositional logic， where lets try to。So in general。

 remember that a model represents a possible world。So in propositional logic。

 a model is assignment of true values to atomic formulas。 So I might have。

If I had my propositional way of representing things， I have two。Propositional symbols。

 and this basically says this world or model says， Alice knows arithmetic， true。

 Bob knows arithmetic， true。Okay， so that's propositional logic， So what about in first order logic？

So any ideas， how should I do this？How do I just try to lift what I know about propositional logic and put it into first soil logic？

The general principle is a model is assign of truth values to atomic formulas。Okay。

 so why don't I just try to do that， So here's my first attempt。

So atomic formulas in first order logic are prediccateates apply to terms。 So， for example。

 those Alices arithmetic is a formula， atomic formula。Okay and student Alice is also know a formula。

Okay atomic formula。 So let's just define a model as assignment to true values to these atomic formula。

 So I have student Alice true knows Alice arithmetic true。Okay。😊，So so far so good。

So what might be a problem with us？So how many atomic formulas are there？Probably potentially a lot。

 Okay， let's figure out。 So the problem is with functions。 If you could actually。

 this is fine if you didn't have mostly fine if you don't have functions。 But you have functions。

 for example， father is a function。 And remember， a function takes a term denoting an object and returns another term。

 denoting an object。 So father。Alice is a term father， father， Alice， father， father， father。

 Alice and so on and so forth， So there are infinite number of atomic formulas potentially if you allow for functions。

So。Then， a single model。Would have to have a of true values to infinite number of atomic formulas。

 And this clearly is no， no good。Okay， so there's also another problem。

 which is that you could have two terms that actually might refer to the same object。 for example。

 father of Alice is this is a term。And Bob is a term， so these are both denoting objects。

But it could be the case that Bob is Alice's father， right。

But if you just naively don't pay attention to any of that， you say you might have something like。

 you know， knows Father Aliceice how arithmetic is true， but knows Bob arithmetic is false。

So there's no way of assuming any sort of coherence between different atomic formulas with respect to what might connect different terms。

So different terms might actually represent the same object。Okay， so we're gonna to try again here。

 And the key idea is is we're going to introduce a layer of indirect。

 So in instead of just taking the symbols and mapping them true true values。

 we're going to define a set of objects explicitly。 So a domain in in logic is just a set of objects。

 So I'm just going to represent them with arbitrary names like 01，02，03。Okay。

 so then I'm going to define this interpretation function that maps these symbols such as Alice and arithmetic into these objects in the domain。

So we start with a primitive symbols， constants， functions and predicates。

 So each symbol is mapped to something that involves the objects in the domain。 So for the constants。

So this is a particular instantiation I might have say Alice gets a sin01， Bob gets a sin 02。

 arithmetic gets to sinine 03。系。And then， for functions。U。I might have the father function。

 which says， if I pass in01， I get O2。So note that I'm not referencing the constants。

So the constants are in syntax land， right， so Alice bo arithmetic。

 and this maps them into a sort of a canonical object space。

 and then the functions are just all going to take elements in the object space。In the domain。

So this says O2 is a father of 01。And then predicateatess。 so for every predicates， I now I assign。

 if nose takes in 01，03， I return true。 If I take in 0203， I return false， for example。

And every other combination I guess I' just assume is false。Okay， so。So student is a unary predicate。

 it takes in an object。And for01 in my region， true，02 and 03 are false。Okay。

 so that is the interpretation。You know function。 So this interpretation。Along with。The domain。

Is going to be my representation of a model in first order logic。

So just to take kind of recap before we were saying a model is just a assignment of truth values to atomic formulas。

And those had two problems with it。The fact that it could be infinite is it also could be。

Have know two terms that reference the same object now or what is a model in first order of logic is this sort of a larger structure where I have my domain。

 which is a set of 010203 and then I have a mapping that specifies how the symbols should be interpreted in the domain。

 so I map the symbols and syntax into 010203 which are in semantics。So the question is。

 is the mapping hard coded， So I will say that this is just the way to think about this is kind of mathematically。

A mathematical object， it's written in code just to make it concrete informal。

 but this is not to say that you would actually instantiate these models。Sometimes you would。

 or more often you would like partially iniate them lazily。Right。

 so the question is if Father Alice and Bob are the same term。

 so why do they have different truth values， So this is。

 I guess part of the point is that this should not even potentially be， let's say。

 a allowed in some sense， but you can write it down and it represents a state of the world。

So you can have these inconsistencies。Okay， so a pi way to think about this is that you have a graph where objects in your domain are nodes。

And then constant symbols are basically labels or pointers onto nodes。

 so Alice points the 01 arithmetics03， Bob02， I just added Robert just for fun to suggests that there need not be a  one to one relationship between the objects and the constants。

And then for the predicate， student is a urary predicate。

 so you can attach urary predicates onto a subset of the nodes。And to say that apply。

 And then you for binary predicates， you can have edges between。Ptterters of objects。

So if you've interacted with or heard of knowledge graphs。

 knowledge graphs are basically these type of things that have some roots in first order logic。Okay。

 so now what we have so far， we've defined what a model is。Okay， just to be clear， a model is。

Has a domain and interpretation， which specifies how to map symbols into elements of that domain。

Okay， so now。Now， how do I define interpretation of a formula？ So remember， in propositional logic。

 the interpretation function。Take a formula and a world and maps that to a true value。

 which means whether the formula is true or false in that world。Okay， so in first order logic。

 we can do something similar， it's going to be more complicated because there's more moving parts now。

 but it's again going to be this kind of recurrence that which I'll walk through。

 which basically takes a formula and sort of breaks it down and recursively calls interpret。Okay。

 so this is the I function for。For first o logic， I'm going to。Okay。

So I'm going to pass in a formula and a world。嗯。And。And also。

 there is a substitute this mapping from variable to object domain， which I'll explain later。

And so I'm calling this with F， which is this formula。And W， remember。

 this actually is a nice view to say this is。A possible world。

It's a mapping from all of the symbols to O's。There could be other worlds out there。

 but this is the world that we're interpreting right now。Okay， so there's a bunch of cases。

 What happens if F is a quantifier that's for all or if there exists。

 And then I look at the number of arguments， whether it's zero or one or two。

 So in this case this is a binary predicate， so there should be two arguments。

And this is a binary predicate， so I have the prediiccate's nose。

 arc1 is Alice and A 2 is arithmetic。And then what I do is the predicate。

Remember is just a symbol nose。Right， so I'm going to take that。 I'm gonna look at。W。

 which is the world and look up what this predicate means。To get its value。

 So then the meaning of this predicate knows。Deotes this。

Which is a mapping from objects to true or false。Okay。So now I recurse on arg1。

 So let's just do arg1。 So arg 1 is Alice。So there's also another function called interpret term。

 So Alices is a constant symbol， so I'm going to look up basically the constants and I say Alices is01 okay。

 so I've got I'm going to return01。So I also do the same thing with arc2。

 So remember arc2 was arithmetic and I look up arithmetic gives me03， so the value is03。

And now I look at this predicate value and I pass in the value of R 1 and value of R 2。

 and that gives me the result。 So I look at 01030103 true， so the result is true。Okay。

So the result here is true， nose， Alice， arithmetic is true in this particular world。Okay。

 so the general recipe is you take your formulaity， you break it down。

 and once you recurse and get to the leaves， you just look up what the appropriate。Items are in W。

So similar to what we did in Proal logic， but just there's a few more moving parts now。

So let me just quickly go through part of how would you do this。

 This is for all X knows x arithmetic。So。So， here。This is a universal quantifier。

So what I'm going to do is we have this a variable。 I've just kind of canonize this。

 So this variable。What it that I want to do is。Iterate over all possible。Objects in the domain。

And sort of push， put that object here and see if this holds。 And if it holds for all objects。

 then it's true。Okay， so what I'm going to do here is for each object in the domain。

I'm going to interpret the body of this， which is the body is nose。

The those variable zero arithmetic。And I'm passing in this substitution。

 So I'm going to keep track of。This assignment that says variable is zero， oh sorry， is0。Okay。

 so if I go recurse。Basically， I am。Let's see。Actually。

 let me not recurse because that's going to take a while。So。In the end here I get false。

And why is this false is's because。Not all the objects know arithmetic。Right， Alice knows arithmetic。

 but0，1 knows arithmetic and。O2。O2 knows actually here I've said O2 doesn't know arithmetic， but。

So that already makes it false。Okay， so to summarize。

 the semantics in all objects are defined by this interpretation function。So in first order logic。

 the model is a domain which is a set of objects and interpretation， which maps all of the symbols。

 constants， predicates， functions， into objects in that domain。

And then we recursively interpret the formulas and define the interpretation function recursively in terms of the structure of the formulas in terms。

Okay， let me stop there and ask if there's any questions about the semantics of sort of logic。

So the question is why is and and oral handled differently than any other predicate。

 so if you look at the code here， if you're interpreting not or let's say an and。

 this looks like what we did in propositional logic where if you have the F is the and of G and H。

 then you interpret G and you interpret H and you take the and。

And your question is why is the binary predicate handled sort of differently than that。

 So remember a binary predicate is an atomic formula。And。

The the arguments that Bi and Pra are not formulas， they're terms。

And so you evaluate the terms and the terms return not Booleanions， but actual objects。

And then the way you turn that into a Boolean is you look up the actual。

 the interpretation based interpretation under W。To see whether that that pair gives you。

AOf true or false。Okay， so let's move on， so we've defined the syntax of first order logic。

 we've defined the semantics of first orderal logic。

So now let's perform some logical inference and remember logical inference。

 we motivated with this like ask tell， and that reduces to entailment， contradiction and contingency。

 which reduces the satisifiability。So here's one thing you could do。

So suppose we have this knowledge base。And we wanted to do inference in it。

 So we want to ask questions of this knowledge base or add new facts。

One thing you could do is just try to reduce it to propositional logic because for propositional logic。

 we know what to do。We could do model checking。So obviously we can't do this in general because forceso logic is more powerful。

 so you shouldn't be able to just always reduce it to propositional logic。

 but you can in a very specific instance。As if you make two assumptions and the two assumptions are unique names and domain closure。

Okay， so this has to do with the relationship between the objects and the constants。

So unique name says that each constant maps each object。 sorry。

 this should say each object corresponds at most one constant。So for example， in this case。

 John and Bob are two constants that map to01， so 01 does not have a unique name。

 So this is ruled out。Under this assumption and domain closure says that each object corresponds to at least one constant。

So in this case， O2 does not have a name or a label。

 which means that it's also needs to be rolled out。Okay。

So if you have to unique games and do en closure， which basically means that there's a one to one relationship between objects and the constants。

Then what you can do is you propositionize the knowledge base。 in some sense。

 we already saw this where you basically say every atomic formula。

 you just remove the commas and the parentheses and the spaces and you just call that know the name of the。

Of the propositional symbol， So if have student Alice， student Bob knows Alice arithmetic。

 knows Bob arithmetic。And then you write down your knowledge base in terms of those things。

So before we have student Alice， Bob， student Bob， those are going to be the same。

 well not quite the same because now instead of having a predicate applied to a constant。

 we now have just a monolithic propositional symbol。And then for all。

 something gets converted to the conjunction and apply to everything where the variable have been substituted out。

 so we have and something that applies to Alice and something that applies to B。

And if you have an exist。That means that converts to an ore where overall all the different instantiations of its body。

Okay so at this point， you just have propositional logic。

 and then you can use any inference technique you want from last time。So in this case。

 first all logic is， in some sense， just syntactic sugar for propositional logic。

 it's the same expressivity， but it's just easier to read and write。ok。

So that's a kind of a basic case。That's an easy case。So now let's look at。

Propositional logic in general。嗯。嗯。So you'll recall that when we talk about inference rules。

What we're saying is we have a set of rules that you pick up some formulas in the knowledge base。

 you match the rule to that formula， and that allows you to derive approve new formulas。

So let's define the modus opponentents inference row。

 which we did for propositional logic and modis opponentents assumes a special type of formula and that's called a definite clausets so if you have a formula that looks like this for all x1 through Xn a1 and all the way to AK implies B so where x1 and through xN are variables and A1 through AK and B are atomic formulas。

That's a definite clause， so an example of a definite clause might be this， so you have for all XYz。

 and then you have the conjunction of a bunch of atomic formulas， takes X Y and coversYz。

 and implies another atomic formula， knows Xc。Okay。

 so the interpretation of this is that if you have。You have。

 someone who takes someone X who takes a core， let's say a class y。

 and that class covers a concept Z， then X knows a Z。So these are not definite clauses。

So anything essentially involving disjunction is not。 So like， for example。

 if you have student L or student Bob， that's not allowed and。There exists。X。

And student and knows arithmetic。 If there's exists a students that know arithmetic。

 that's also not allowed because remember， exists is basically a compact representation of or。

 And for all， is a compact representative and。Okay， so let's now introduce mods opponentents。

 it's going to work on definite clauses。So in order to define a rule。

 there's premises and then there's a conclusion。So the premises are， I have a a set of a。Now formula。

嗯。And that look， and then I have another。A formula in the the knowledge base that looks like this。

Then I can conclude B。Okay。So this should be intuitive。 It basically says if。A1 to make K or true。

And it's also the fact that if I have a rule that says a1。And3 a K implies B， then I can derive。啊，B。

So it looks like mods opponents， The only difference is that we have this for all here。

Over a bunch of variables。 So let's let's look at the concrete case here。So you have， let's say。

 Alice has taken 221。And 221 covers logic。And then you have a rule。

 this is a sort of grand rule that says whenever。X takes y， and y covers Z， then X knows z。ok。

So intuitively， given the knowledge base， I should be able to infer that Alice knows logic。Right。

However， I can' actually apply this rule。And the reason is that。This， these rules are just， remember。

 everything is syntactic。RightSo the rule is just going to do like an equality check and it says。

 okay， well， let's see A1 could be takes Alice 221。But then I look at this A1 and it says takes x Y。

 and these are not the same thing。Right， so we can't apply the rule。So in some sense。

s iss like kind of， it's kind of dumb。 But that's that's the， the rules are just。The rules。

 you just follow them。Okay， so what can we do here？

So you can't apply the rule because the rule says that。Whenever you have anything that。A1。

 it has to be the exact same string that goes there。So remember in propositional logic。

 this was not a problem if I have rain and rain implies wet。Then I can。You know。

 match wet because these are exactly the same string， right， but if I have， you know， takes。

Alice CS221。 and then this says takes。Yeah， X， Y。And then bunch of stuff。

 Then these are not the same， so I can't。Just conclude。So there any ideas on what I should do here？

Yeah， so somehow I have to look at。Y and x， right remember x and y are variables。

And what does for all mean？It really means that for any x and any y and any Z， this holds。

 So in particular， it should hold a v in 221。Right， so in some sense。

 I need to like convert set X equals L and y equals 2，21。 and then it'll work。

 So this rule really says I can set X， Y， Z to anything I want。 So it's really like a rule template。

哎。So what I'm going to do here is introduce these notions of substitution and unification。

 which will give us what we need。So substitution is I need a mechanism to operate。

 do surgery on formulas。Okay， so。I have a formula knows X Y。No is a predicate， X and Y are variables。

And I have a substitution that says。X maps to Alice and Y maps to CS221。

And I want to substitute use the substitution， apply it to this formula。Okay， so again。

 I'm going to do this recursively。Where I have nose X Y and applying the substitution。嗯。

So I'm going to look at the F。It has a number of arguments， X and Y。 So two arguments。

 I'm going to recursively call substitute。And then I'm going put it together。

 So I'm going to recurse on X。 And so X is in this this mapping。 So I'm going that returns Alice。

 So I fetch Alice here。And then。Same with Y， Y gets mapped to 221。And then。

So now I have these new arguments， I apply the same function E thought decal is basically nose to these new arguments and I get my fresh formula No Alice 221。

Okay， so this is a， you know， function that basically substitutes these。

Whatevers on the right hand side with sorry whatevers on the left hand side with whatever's on the right hand side。

Okay， so that worked。And now let's try another one， so formula， student X and those X Y。

I replace X with Alice， Y with Z， and I get。And a student， Alice knows Alice Z。

 So what can be on the right hand side can also be variables。

 It doesn't always have to be a constant。ok。So I think it should be straightforward。

 substitution takes a formula and just substitutes。

 does a surgeon replace recursively in that formula。Okay。

 so unification is basically generalized equality， right。

 So the problem with takes L 221 and takes X， Y is that they're not literally equal。

So unification says。Find me a substitution that makes the two terms equal。And。

If I can't find a substitution， then I'm going to just。这 that就是哪一个。Okay， and， of course。

 I can only substitute the thing on the left hand side of a substitution。 They can only be variables。

 right， I can't replace Alice with Bob。I can replace X with anything I want。

 I can replace Y with anything I want， but I can replace Alice with something else。Okay。

 so Unify takes two formulas an empty substitution。

 which it's going to build up and tries to make these the same thing。So the recurs。

And if at any point something like you can't replace noses with takes for example。

 so if they're not equal， then we're just return and now I'm going to go through all the arguments and I'm going to unify x with Alice。

UmYou know， that。And then， unify。You， why with Bob？And that returns this substitution。X as Alice。

 Y as Bob。Okay。😊，So which means that if I applied。This substitution to both arguments。

Then the two should be identical。And indeed， if I replace x with Alice and Y with Bob。

 then these two are the same。Okay， so here's another example， knows Alice Y。Unified with nose X， Z。

So。The result here is I replace X with Alice。And then why with Z。And then I ended up。

 both things become nose， Alice， Z。And if I try to unify nose Alice Y with Know Bob Z。

 this fails and returns none because Alice and Bob just cannot be unified。Okay。

 so now I have the tools of substitution unification。

And this is basically going give me like generalized equality。 So now I'm going to try again。 Okay。

 here's mod opponents。 Take two。So the rule says the premises are， if I have a bunch of formulas。

 I'm going to use this prime to distinguish from。The non prime version。 So these are different。

 So I have a1 prime to a1 a K prime。 and then I have this rule that says a1 through a K implies B。

And then in order to apply the rule， I'm going to have to first unify a1 prime 3 A K prime with the A1。

3 AK。And then the if I can unify things， then I conclude。You know， I don't conclude B， but I。

 I can't conclude B。Because I need to take this unifier theta and do the substitution to get B prime。

Okay， so let's walk through an example to make this clear。 So again。

 I have this knowledge base takes Alice 221，221 covers logic。

 and there's a general rule that if you take a class I cover something， you know that。

So first of all。I'm going to unify the conjunction up here。

 which is takes Alice 221 and 221 covers logic。And I'm unifying it with takes X， Y and covers Y z。

So that gives me this substitution。Which says x needs a map to Alices y to 221 and z to logic。

And then， I substitute。Nos X z with that same theta， and I can conclude Nos Alice logic。Okay。

 so this version of what opponentents works。Because I can now bridge the gap between these general variables and these concrete instances。

Al right， so what's the complexity of this？ So every time you apply modponents。

 it produces an atomic formula。 for example， nose Alice logic。So if you don't have any functions。

Then the total number of。Atomic formulas you can produce is simply the number of constant symbols to the maximum preity。

 so if you have binary predicates like nose Alices logic then that would be the number of constant symbols let's say you have 10 constant symbols and maximum Erity is 2。

 then that's 10 times 10 different atomic formulas you can create。But if you have functions。

 then the complexity actually can become infinite。Um， so you can have nose Alex， Alice logic。

 nose father， Alice logic， nose father father logic， and so on。

So there might not be an even end to this。And you can definitely imagine rules that can generate infinite formulas。

 So for example， you have a rule that says if。X knows logic than the father of X knows logic。Okay。

 so you can easily see how you can just， you know， kind of just keep on generating these these addfin itemum。

Okay， so that's just how it is。 So what do we know about the properties of duties， the someponents。

 The good news is that it sound。😊，So which remember that means if the knowledge base can derive or prove of formula。

So if you can apply motive componentsents and that you get a formula。

 then that formula is actually true。 Then knowledge base entails F。But it's not complete。

There are formulas where the knowledge base entails F。But you can't prove it。

And a simple kind of example of this is you can't derive things with disjunction in them。So。

You know you need there's another rule called resolution。

 which allows you to be complete for first soil logic， but I'm not going to cover this。

This was covered in previous lectures， it's a little bit more complicated。

 but we're just going to skip it this time。Okay， so here is the summary。

 so Moponents works on these definite clauses。Which have this sort of if then structure。

 so if rain then wet or if you know， city of X， then plates of X。

The intuition behind these definite clauses is that there's no disjunction allowed。嗯。Substitution。Is。

Now， search and。Replace on formula terms and a formula。

And unification finds a substitution that makes two terms equal。

 substitution and unification are required to carry out these rules and first sort logic because you need to match variables with constants。

Okay。So in the final part of the lecture， I want to talk about natural language to firstor logic expression。

 so some of the assignment will involve essentially translating natural language into firstor logic expressions。

 first or logic as I've demonstrated hopefully with the examples is a way and it' a very natural way of encoding the meaning of natural language sentences。

So we'll just go through some examples。 So Alice bought both no arithmetic。

So the way you would represent that is nose Alices arithmetic， knows Bob and nose Bob arithmetic。

 all students are arithmetic。For all X， students， student of x implies knows x arithmetic。

Some student knows arithmetic， there exist x， such that student of x and knows x arithmetic。

So I'll pause a bit and point out that。Universal quantification for all。

 is usually paired with an implication。So usually if you see for all。

 there's something implies something else。An existential quantification is usually paired with a conjunction。

 There exists x。Such that student and notes。Okay， so 99% of the time。

 this is basically the rule you should follow。So if you see stuff like this， it's probably wrong。

So why is this wrong for all x student of x and knows x arithmetic？What is this actually saying。

 That means says every object in your domain is both a student。And nose arithmetic。

Which is not what you want。What you want to say if x is a student， then student。

 that x knows arithmetic。Likewise， if you see this， it's probably wrong。

 so exist x student in X implies no x arithmetic。What this is saying is that there exists some object X。

That is either non a student or a knows arithmetic。So as long as you have a non student。

 this is true。So that's also that we want。Okay， so just remember。

 for all implication exists and you'll be fine。Okay， so here are some other examples。

 there is some course that every student has taken。Okay， so to translate that。 Okay。

 so there exists an X。Actually， I have some course should be in there， the resistant X。

Such that for all y， if y is a student implies Ta Y X。Okay。And。

Youll notice that there's an implication that's paired with the and。And technically。

 there should be like exist x course of x and this thing。mSo how about this Gold blockss conjecture。

 every evening number is greater than two is the sum of your prime numbers。So this says for all X。

Even if x and greater than x is greater than 2 implies there exists y and z such that y is prime and z is prime n when you add Y and Z that you post x。

And finally， this is the one that we kind of already saw if a student takes a course and a course covers a concept。

 then the student knows that concept。For all X， Y， Z， if a student X student x is a student。

X takes y。 Y is a course。 Y covers Z。And Z is a concept， then x knows z。Okay。So， you know。

 this is something that。You know， it might take a little bit of kind of practice just kind of reading natural language and understanding how you map to logic。

 it's not in some sense that different from you know translating informal natural specifications into code。

 but it's just like a different language that you have to get used to。

One thing to notice is you know this is a definite clause。

 so modus opponents will give you something， these are not definite clauses because there's exist x here and then there's exists over here。

 which make it more complicated。Okay， so this is just a motivating example。

 I I'll skip that since we already covered it in the beginning。

 but you can go back to this example and kind of this is more examples of how you translate natural language into。

To first order logic。Okay， so now let's summarize， so first order logic。This is the topic of today。

It gives you a language that's more powerful than propositional logic， in particular。

 it gives you notions of terms which denote objects。It gives you functions which。

could allows you to derive other funk objects from objects， and you get predicates。

 which takes objects and returns Booleance。We then can define variables and quantifiers that operate over all the objects or so you can think about this as a for loop over objects。

And this is what gives us a power。 Think about， you know， if you had a language without a for loop。

 it would be very verbose， but you have four loop， you can write one liners that do a lot of things。

So。The semantics of first O logic。Are given by the interpretation function that maps the symbols。

 which are the constants， the functions and the predicates to the objects in the domain。

So then after we define the the。Semantics the first order logic， we said， well。

 if you have domain en closure in unique names， we can propositionalize and reduce the propositional logic。

But if you can't， then or if you have only definite clauses。

 you can run modponents with substitution and unification。ok。

And if you want to have completeness and you can do resolution。

 but we're not going to talk about that。So the final thing is that our journey and logic ends here。

 but if you're curious， there are other high order logics that allow you to express more。

So for example， think about how you represent 70% of students know machine learning。

try to write that in first so logic and you'll realize that， wait， you can't actually do this。

And therefore， you need some other higher order logics that allow you to essentially not only just quantify over individual elements。

 existent for all， allow you to quantify individual elements。

 but this requires knowing us you have a set and you want to operate on that set。

 so this kind of relates to the functions of functions coming in you earlier。Okay。

 so that's it for logic next time we're going to start thinking more broadly about AI。

 we're going to zoom out and talk about language models and AI in society that's going to be the last three lectures and then we'll the final lecture will be more of like a kind of fireside chat with you know some presentations。



![](img/83192f817d97f718d400a1e6182cd60f_3.png)