# ExamPro《生成式AI训练营｜Free GenAI Bootcamp》中英字幕（deepseek - P57：-57-Visual Novel Story Design.zh_en - GPT中英字幕课程资源 - BV1SFEWzLEab

All right， folks， we are back and probably about two hours。 It took me to generate the images。

 I would say that in some areas， it was easier in other parts， it was harder。

 So if we go over to here。 I obviously I'm not going to show all the generation here。 But I mean。

 this one， I had a really hard time getting the top of the head in the bottom。

 So that took a lot of attempts。 This one was really hard because it kept generating out them sitting this white background that didn't cut out very well。

 You can see from Canada that was trying to Canada everywhere on them。

 as it was a little bit too much。 This one was hard。

 theres the only one where I could get a Spanish person that was standing looking at the screen。

 therere still not looking at us and you could see the lightings an issue one thing I realized like having lighting directions。

 I found this all the g and Gock just does not listen to the commands， it still does a good job。

 This one turned out really well， but I realized it was like trying to put a woman in the bottom。

 be specific to be a man。 This one actually had a lot of good generations out。

 there's one where like it was with a。

![](img/8ee636b7434260228c14bd833e1071d7_1.png)

at a table。 but I didn't know how to incorporate that。 So I kind of gave that one up here。

 This one here。 You're supposed to have like clips in the hair。 I didn't tell to do that。 I mean。

 to generated that stuff there。 So this is a woman from South Korea in her 20s。

 It's hard to say she looks like she's a bit younger than that。

 But it was generating kids first because of the aesthetic。 And so I told to go older。

 And it made people that were way older。 I probably still have some of the ones around here。

 I'm not sure if they're still here this suppose to have a button in their hair， I guess。

 but like they look a cross side there。 I never noticed I don't really see a button there。

 but that's totally fine。 But some of the generations out for this one was was quite funny。

 But this one here， you can see like this is the only time I got an image where it like boom all I had to do is grab it and remove the background。

 So that was really lucky。 And then our original one here。 And so there's inconsistencies。

 And mostly it has to do lighting。 But I would say the photos are still pretty good。

 but I had to do a lot of touchup for scenes。 We got。😊，We got a cafe。 we got a classroom。

 We got the cho store。 We got a post office。 I don't know what a Japanese post office looks like。

 but we'll assume that's what it looks like。 And I would say that they're fine。

 Like there's some distortions and stuff like that。 But I think it doesn't really matter。 well， look。

 there's chairs outside， right， maybe those are that's the outdoor classroom。 And so。😊，You know。

 we can fix those。 I don't really care。 I think it's good enough for this。

 And so we are now ready to do our coding implementation。

 So I guess what we need is we need some kind of narrative to drive this， right。

 And so the idea is that we have these scenes， these areas and we need to figure out what's going make this an immersive game。

 right， So usually visual novels have a story arc that you go through。

 They don't really give you flexibility to move around where you want to go。 I mean。

 there are things like called daily life simulators where they do let you go places and do things。

 And it depends if we want to move from a visual novel to a daily life simulator。😊。

ADa simulator would actually be really， really good because then you'd have repetition of things that you're doing。

 So that would be really good for immersion。 I don't know if we could。

Really incorporate that because we don't have enough assets per se Like there has to be， I guess。

 a lot more going on， not necessarily， but more， maybe in within the shots and expressions of folks。

 something we could do is try to， you know， have more face expressions。

 That's something I didn't really try， like。Again， it's just because I don't want to spend a lot of time here。

 But we could go here and just， let's just see if we can do this say like change。

 change face to be angry。 Okay， like， I don't know we'll get， But normally when it swaps out faces。

 it really distorts them in my prior experience。 So we'll try it here。

 But I really don't think that it's gonna to do a good job。

 we might as well try and see what happens here。That's weird。嗯。You know what I mean like。

 does this still look like the same person？You know， we go here and we say。嗯。Like， maybe。

But have to go here and try again， generate it again。 Maybe just generate， generate。

 generate till we get one that works。 But this could be very tedious。 And I'm not。

 really ready to prepare to put that kind of energy into this。 I think again。

 I would rather do this locally with comfy U I。 But right now， we are just trying to see。

We're not getting any phase changes now。 Oh， I gotta keep this here。 So we gotta see and so。

It mean like literally the facial structures is weird that we can tell。

But you can tell that's not the same phase。 The makeups changed。The eye color has changed。So this。

 again， is where they give them an hearing for some reason。 This is where that'd be too hard。 Now。

 of course， in Photoshop， we do have some options in here again。 If you don't have Photoshop。

 just work what you got。 you know， you know what I'm saying here。

And they have this thing called liquey。I really go to Photoshop for people that know that。

 And so we can change the expressions a little bit here。 Like we， we can do this and， you know， like。

 change the， change the face ship by stretching things up。

 We could also move them around a little bit。But， you know。

 we're not gonna be able to make them smile or anger or stuff like this。

 So this is not going to work really well for us， which is fine。

 We would have to go through many iterations or find another piece of software to do that。

 But the point is， is that we are， for the most part， done with Photoshop for now。

 I'm gonna close out Photoshop as it does take up my resources。 No， no， no， yes。

We do want to save that。 I don't want to lose that。 And so。The next thing is like。Oh。

 I really want to do a daily simulator now that I thought about it。

 that's like so smart for immersion。 That would be really， really， really good。

 But we don't have the time。 So I think what we need to do。Its kind of defined the story。

 So we go back over to here。We're not coding it。 We're just doing the story。 So gameplay mechanics。

 choice system， branching narrative， inventory system， no stats and skills。 No， mini games。 No。

 I mean， that'd be fine， but no the。We need， I mean， there is obviously like some U I here。

 But I guess the thought is like， okay， so we're gonna stick with cloudude 3。7 thinking。Okay。

 so now we need to think about the story arc and how it's going to be useful for language learning。

 Obviously， so can you give me an idea based on。The characters we have。And settings。

We have for a story arc。Remember， we we need branches in the story。Okay， so let's see what we get。

Develop a story language arc， so'll see what it does here。Here it's going。

 it's listening out the folks here。 So based on the characters setting you develop。

 here's a comprehensive story arc with narratives。 I mean。

 doesn't get all the details of the characters that'd be very interesting。 The main story。

 finding your voice in Japan。 the player takes the role of a foreign student。

 They are takes the role of it， who has just arrived Japan。 They must navigate daily life。

 building relationships， overcome cultural challenges while improving their Japanese skills， oh。😊。

These character interaction teaches specific vocabular grammar。

 dialogueogue choices reflect the player's current language level。

 Converations with characters adapt to be selected difficulty。

Lower levels include more English and native and stuff like that， main character， language school。

Core challenge prepping for the JLPT。 that is something that I am doing so that we got that focusing on reading。

 writing。Folks on， folks on speaking and spelling more interactions。 Oh。

 that's interesting that we have here， traditional culture path， more interactions with。

what what what。Witabe Wabe Wabe Akiko。Modern cultural path， more interactions with Yuki。 Oh。

 that's kind of cool。 Cult immersion， daily life。 This sounds like I want all of this。 But like。

 I don't， I don't see how we could get all this， right， In living， more interactions with Suzuki。

 Kenji， social interactions， more interactions with Alex， right， And here， you know。

 you might want to say like， you know， I don't know。😊。

Each character relationship must have multiple branches， conversation choices， side quest。

 So now we have the weekly story arc。 So week1。 And now it's not a daily similar， but they are。

 they are specifying time， right， So meek， roommate Alex and teacher Yo motto。

Choose initial learning， focus， academic， cultural or daily life。 The only problem is like。

 I don't think we can have people in the same room because right now， Well， maybe we can。

 but they might be unusual to move them to other places。 But I guess we can do that。

 even though that doesn't really work because they might overlap， right。

 So that's kind of a little bit of issue that we have here。 regular is less with Yato。

 So I would just say that。One thing you need to consider is can we can't have more than one person in a conversation because the graphics will overlap。

 so we simply have to make it one on one interactions。

Interactions and interactions between characters。Can only work when they are talking about someone。

Someone not to another character。Other other than other than the main character， the main player。

 Okay， so we'll go ahead and we'll adjust that there。 But I like， I like what it has here。Okay。

 so now it's， it's making some adjustments here。Players choose which characters they interact with at specific decision points。

嗯。I don't know。 So here it says revise。 So finding your voice in Japan。

 all scenes feature only one player and。Only one player。

Fture only the player and one other character characters will reference other characters in dialogue。

 scene transitions will be used to switch between character interactions。Okay。

 so each character has their own story line that progresses independently Players choose the character to interact with。

 I don't think they choose。Because it's each location has a primary character character associated with it。

 Players travel between locations interact interact different characters， time of day system。

 So it is gonna a little bit too advance here。 So I'll have to make some changes。 So sorry。

 the visual novels， visual novels are are linear， right， So so they don't。

 they don't get to choose who they talk to unless， unless it's a story branch， a story branch。

 So all stories。Have to flow one from another， okay。Okay， so we'll go up here。

 And so now we're starting to see this。 I'm gonna go back over to our visual text back。

 And so now what we're seeing。Is。Characters。We have scene settings。

 I guess these are more like scenes。Settings。These are basically scenes。Okay。

 and then we have up here。We'll put this in here， like this。Core story framework。

 So we have here linear progression through scenes。Each scene。

 each scene features one character with one player。

 key decision points that lead to specific branches， all direction fully naturally one to the next。

 Okay， so。We'll continue on here in the right hand side。 So chapter 1。Arival at airport。 Okay。

 so look， your， there is no airport。Graphic。So， you have to。Lit。The story to the scenes， right， So。

 so like， start the player。Already in Japan， like。So this is something that it needs to understand。

 right？They have branching， only two three major points in the entire story。

 Each branch leads to distinct sequence of scenes。 Players cannot jump between branches Once a choice of be made。

 each player emphasizeizes different aspects of the language learning。

And that's something that we can， yeah， we can do。So that's going to revise the story。

I didn't realize I was writing it right in here。Has it been doing that this entire time。Okay。

Can we place the story structure。In its own M doc， just because I don't want it to。

 to make a mess of this one。 So there's so much that can be going on here。

 So we'll just separate it out， right。

![](img/8ee636b7434260228c14bd833e1071d7_3.png)

The reasoning seems fine。 again， is it better than clo clod 3。7。 It's hard to say。Anyway。

 we'll give it a moment here。Alright， so it's extracted it out into this other file here It says enhance the story。

 edit details， outlines entire visual novel， updated the specs。

 separationation makes the technical specification a bit cleaner。

 It'd be nice to like visualize what it actually looks like。 the actual the flow of the story。

 but we'll take a look here。 will say it moved it into here， which is fine， I guess， I mean。

 I would have rather just had it in here。 Cl spries over here and then it repeats it again。😊，嗯。

I guess it's fine if it's repeated。 So we have player wakes up in the apartment。

 welcomes to Alex welcomes to Japan。 Alex gives them basic information about the neighborhood and language。

 player rides at the language school meets Yamatoto sense say first basic Japanese lesson with Yamato Yamatoto assigns homework visits the post office visits the post office post office to maila form visiting to visiting to post office meeting。

Talk。To knock噶。Hero Hiroshi。Hrohi， I don't know。 I had such a hard time with Hiro， Hirohi。

Language challenge with forms。Returned to apartment， Alex suggests visiting the cafe for practice。

 visiting。Visit visit the cafe meeting。nakuura Yuki。

How you respond to Yuuki's questions about what you want to focus on， academic study path。

 cultural path or practical path。 I guess this is like a place where you can have branching。

 which is interesting。 Then we have branch A。 So again， I'm not sure if I'd like these branches， but。

Because like， I guess the question is like， well， what is it the outcome that you want in the story。

 right， I it。I don't know。 Yuki Yuki introduces you to Carlos of the cafe advanced lesson with Yamatodo Seni。

 your your approach to language learning， one thing that I think might be interesting is like since we have this stuff。

 it'd be nice if there's a wait for the LLM to produce。If it like knew like how to do that。

 And so we could focus on each of the stories。 But right now， we're just hard coding everything。

 me just， I'm gonna pause and think about this for a second。Alright。

 so even though I'm not really a huge fan of of the branching of this stuff， which is fine。

 I'm trying to think more like imagine I make it static and then I want to move it later。

 so it's dynamically generated so that an LM can drive each scene because like in my mud， it's a lot。

 I guess it's generated as well。 And you have a situation that needs to be accomplished。

 But in these situations here， we are trying to achieve some kind of repetition or goal。

 And so like if I go to the school， I want to use school vocabulary。

 I want things to be school focus， I want to know what the common things you say or stuff like that。

 But I think what we need is we need to figure out like what's going drive this here。

 So I'm trying to talk about like the engine or like the structure of it。

 So you know what is it that we want like this like。We haven't coded the game yet， Right。

 So we need a like a， a story branching system。 So I guess my thought is like。We have to specify。

You know， it's like the。Story。Here's the setting over here， which is synopsis。 This is the。

I feel like this is a technical implementation。 I'm going to take this and bring this all the way down here。

 and we'll call this。T specs。We'll go here。 It's not really text specs。

 but we'll go bring it down here anyway。 And so I'm gonna go here。 and we're gonna say like story。

storyory branching system。Okay， so。Deines the logic via J file for story branching。Okay， so here。

I'm going to go here， and I'm going to say。Right here， we'll say was it L or K over here。

 So I'm trying to figure out。How to。嗯。Store the story， the the story。As a data structure。In Jason。

 right， I would think that each scene。Is its own object。Own isolate Jason object。Okay， but anyway。

 let's see what it comes up with here。Not sure where that we。It kind of like vanished。

 where the code go。I didn't delete it。 That's for sure。And let me just rip my code out。What the heck。



![](img/8ee636b7434260228c14bd833e1071d7_5.png)

So。Oh my goodness。 Oh my goodness。 Oh my goodness is a little bit too much。

 So I just want to see a little bit here。 So we say main story structure。 So here we have。😊。



![](img/8ee636b7434260228c14bd833e1071d7_7.png)

嗯。I mean， do we even need to use Gemini can try the little thing out。

 We have finding your voice in Japan scene first scene， scene one scenes， scene  one。

 scene  two characters。Alex Yamatoto。

![](img/8ee636b7434260228c14bd833e1071d7_9.png)

Location， does this make sense。嗯。

![](img/8ee636b7434260228c14bd833e1071d7_11.png)

Scene one。 So we have an I D for the scene。 We have the title location， the character I D。

We don't need the background image if we have the location， right？



![](img/8ee636b7434260228c14bd833e1071d7_13.png)

And so here we're taking a look here and saying， we have Alex， hey there。 Welcome to Japan。 I'm Alex。

 your roommate。 Nice to meet you。 I'm excited to be here。 Let me show you around your apartment。😊。



![](img/8ee636b7434260228c14bd833e1071d7_15.png)

And。

![](img/8ee636b7434260228c14bd833e1071d7_17.png)

This is vocabulary。Okay， how is this， How is this useful。



![](img/8ee636b7434260228c14bd833e1071d7_19.png)

Branch point structure。

![](img/8ee636b7434260228c14bd833e1071d7_21.png)

嗯。Let's just focus。On the first scene。Json structure file。So we can tell if the less at the scene。

Its useful for language learning。

![](img/8ee636b7434260228c14bd833e1071d7_23.png)

O。That's all I wanted to focus on right now。

![](img/8ee636b7434260228c14bd833e1071d7_25.png)

And I'm gonna to go back， and it's really fortunate to like wiped out some of my code there。

 But I' go back to order the story structure here。Player wakes up in the apartment seeing to Alex gives basic information about the school。

 so we'll go here。We'll give it a moment here to generate。 we'll see what comes up。



![](img/8ee636b7434260228c14bd833e1071d7_27.png)

let's take a look at the structure。 Jason。 Now， I don't need it to produce Jason。

 I mean we're just looking as examples of basic scene information， title， description。

 first day in Japan， meeting your Alex roommate location， character， character details。

 language difficulty beginner。 We don't need that information。 enhanced dialogue system。 So， Alex。



![](img/8ee636b7434260228c14bd833e1071d7_29.png)

Oh， you're up in the morning。 language version。

![](img/8ee636b7434260228c14bd833e1071d7_31.png)

Alex happy， Alex greeting， It has an audio file。 But， which is it。

 I it gonna be in English or Japanese， right， So play a response options。 Good morning。

 You must be Alex。 Good morning。 You must be Alex。😊，呃。So is everyone always speaking in Japanese。

 I mean， that's fine if they are， right。嗯。I'd probably be easier to do that because if we didn't do that。

 I don't know how this would work right because when we have I'm not saying we need audio。

 but if we want to have like the audio output to it and we bring that stuff in。

 we're going have our time over're doing English and Japanese because it's very hard to mix someone that speaks English and Japanese Now Chat GBT can do it。

 but I've never seen any other models that are able to do that。



![](img/8ee636b7434260228c14bd833e1071d7_33.png)

Comprehenive language learning section。Vocabulary items。



![](img/8ee636b7434260228c14bd833e1071d7_35.png)

Grammar patterns。Cultural notes。Now， like all all of this is is a mess like。Like， really。

All there is。Is Japanese sentence。English， English translation， right。So， you know， maybe， you know。

Then。Right， like it's just， they're making a huge mess out of this。Yeah， it's a simple game。

 We telling it this year。 I could come up with it myself， and it might be actually faster to do that。

 but。We'll see what happens here。

![](img/8ee636b7434260228c14bd833e1071d7_37.png)

嗯哼。😊，Okay， so here。We have speaker。Nrrator， text， welcomee to your new apartment。Nexting choices。



![](img/8ee636b7434260228c14bd833e1071d7_39.png)

Okay， so I'm gonna help it out here。 It's having a really hard time figuring out the structure。

 And so we'll go over to this。Back over to here。 I hope it doesn't blow it away again。

 That was really frustrating last time well go。I guess说给的。Put it back over here， I guess for now。

 And we'll just say。Soory。Data structure。Example。So here we have a scene， right？And a scene。I mean。

 first of all， there's a scene。And then we have。

![](img/8ee636b7434260228c14bd833e1071d7_41.png)

Location。Id。And then character I D。 there we go。 We don't need these two。 These don't do anything。

 Okay， so this is going to describe， you know， the image like the image for the background。

 This was going describe the character， right， Now， the next thing is we go into the dialogue。

That's a good idea。The only thing is that。That's an array。

 which is kind of a problem because we don't necessarily know。What's transitioning to what？

So I have to go here。And now we have a dialogue of this。

 and so this this will have probably its own ID， right because if we don't do that。

 I'm not sure how that would work。And so here we would just say。Right， wake up。

And now we're kind of like going through and showing this example here。And so， we have。J English。

Japanese。

![](img/8ee636b7434260228c14bd833e1071d7_43.png)

Okay， that's not Japanese。 There we go。 There you go。 Now， it knows what I want， okay。Here we have。

An나tawa Arahi apartni。So you apartment， you new apartment。N Audy， I'm not sure what Ay is。We have。

I mean， it looks like Ashta， but it's like， I guess the morning， like Asaheo， something window。

 modo no， Nokio whatever so。You wake up at your new apartment。 Yeah， that's correct。Odery。

 maybe ally is wake up in a short form。 I not。 that's not nearly what I would see here。

 It doesn't mention Japan in here at all， which is fine。 The morning sunlight。 So here's morning。

 we have bright light through the window。 And then here。😊，It's whatever。 So kind of matches。

 it doesn't really matter。 It's just kind of what we're looking at right now。 So we have the speaker。

And this is。Player， right。Right， because that's what it is。 And the next thing might be Alex。

 But the thing is like， how do we know where it transitions to next， right， Like。

 are there any choices。

![](img/8ee636b7434260228c14bd833e1071d7_45.png)

So here we'll have choices。Right， there's no choices。Because if there was something。

 then we have to go to the next step， right， That's the thing that's really important。

 I think it'd be kind of cool if it， I mean， if there's like the next arrow， that's one thing。

 but we'll go here and we'll put an Alex。So what we have。Ohio， Okita， so。Yep。Good morning。You're up。

 right。 So that's what we have here。 The only thing is that。Then we will launch some choices in here。

 so here。Going to here。Yup。And I'm not sure why I keep doing tax。 I really wants to do tax， They。

 So have。English。Japanese， there's no beginner level stuff here。Right。

 and then I'm just going to dot dot， dot to imply that there are more choices。Right。

 and so the idea is that based on your choice， that might trigger a step， right might say。Next。

 and this would be next ID。Let's also 00，2， right？Okay， and then up here。There is no choices。So。

If there's no choices like， what do you do for that transition， right， Like if there are no choices。

I guess you just。Right if。We'll go here if there are no choices。

 it's just gonna go next to the next thing。But hows it know where to go next， right？De youult next I。

Oh， what， right， so。Maybe that kind of helps， right。 So now we have。A bit of a transition， right。

 The other thing is that， you know， we're choosing that all this can do is branch。

 if it's just next I D。嗯。And these are like specifically like dialogue branch。

 So it'd be like whatever。 But I guess the question is like。

Are there things that could be additive or removed that would change the calculation or score of something？

So， I'm not sure， like。Becauseuse right now， if you want a branch to occur in the story to go to a different scene。

 we'd have to do some extra logic to do that。 And so this is the most bare bone thing that we can do here。

 So this is， I think， a good structure for a scene。 And so this is an example of scenes。And so。

 you know， willll go here and。啊。I kind of prefer if these scenes were all separate because then we could like work through them a little bit easier。

 maybe。And then that was this way， this would be a lot easier。 So we'll go here。

And I'll make a new folder。 It should have been called data here。 It's not letting me change it。

 And I gonna to go here and make a new folder called here we have characters and scenes。



![](img/8ee636b7434260228c14bd833e1071d7_47.png)

And I'll go here and just call this assets。🎼I let me move this here。 Can I move it， move， move， move。

 Yes， I can。 I'm gonna make another folder in here。 This is gonna be called。Story， right。

 so this would be story。Or。Scenes， I suppose。This is an example。

Of a story scene format that is stored。In the outputs。嗯。Assets， outputs。Sins。😔，Diirctory， okay。

 And so now。It knows this is the structure that we want。嗯。Now， we wanted this to write the story。

 like， again， we haven't done any coding。 So again， I still want to use gemmin at some point here。

But now we have this。 So I'm gonna go here。 I'm gonna to say。Look， look， I， I helped。

Figure out a structure。That I want， you can read story structure。To see the structure。And。Where to。

Output the files。Can you。Create the first。Seen。And place it。Okay。

 so now it should not luck with my stuff。 It's going to actually place this into here。 Obviously。

 these， yeah， these can be named whatever we want。 but we'll let that go ahead and work。

 work through it， okay。

![](img/8ee636b7434260228c14bd833e1071d7_49.png)

All right， so。Dab below here， it says the files now here。 Okay， and we have information here。

 Let's go into the scene。 And let's take a look and see what it looks like。 So we have。

 can we wake up。我还有。お키 탄단네お키탄다네。It's a little bit different from before。 That's fine。 Okayki。

 I think that's kind of a softener here。 probably nobody cares。 And so here。There's no Japanese。

 I guess the player has to choose why， why is it not doing that， right？ So I noticed。



![](img/8ee636b7434260228c14bd833e1071d7_51.png)

You know， I noticed here。When you generate it out。That。0，0，2， the JP in English is blank。But。

The choices are supposed to be。In 0，0，1， because it's。A response al。Choices are from。

Perspective of the。Of the。Of the player， right， So I think it doesn't understand that because here would literally end up displaying nothing。

 right on to the thing。 And that would be a problem。



![](img/8ee636b7434260228c14bd833e1071d7_53.png)

![](img/8ee636b7434260228c14bd833e1071d7_54.png)

And so you can see we have some options here。Another thing we might want to have is like if you had a response。

 you might want an immediate response for it to transition back to it because then you don't have to create all these things separate。

 separate out here。But we'll think about this。Allright， we'll come back here。 So， you know。

 first of all， first of all， there is no narrator。It's always the player。Talking to themselves。

To someone or to themselves。As inner thoughts。I don't know why you added vocab。To the data structure。

Okay， you know， can you， can you update our tech doc， so。You better understand。So like。

 I don't know why it's to be that， right， So like， we'll go there and we'll let it fix it。 But。

 it's being， this is what I mean， where I talk about clod 3。7 being a little bit too aggressive。



![](img/8ee636b7434260228c14bd833e1071d7_56.png)

![](img/8ee636b7434260228c14bd833e1071d7_57.png)

But I don't know if it would to actually go back and fix this information here where it's like progresses through scenes so you know。

 a few things we need to note here so some notes。You know， considerations go down here。

 I'm not sure how would know that anymore， but like player。



![](img/8ee636b7434260228c14bd833e1071d7_59.png)

Dial we'll go here and just say。Speaker is always the player or。Or another character。

There is no narrator。The player。Is talking。The players inner。Modello。呃。Would act。As narration。

When needed。Okay。No， there， there， there is always an explicit next scene ID D。 So if there is no。

 if there is no choices， then the default next I will transition to the next scene。Okay。Choices。

Are always from the perspective。Of the player。So go back into here。U。

So we have this default next I D choices。 Good morning。 Nice to meet you。 That's right。

 Thanks for having me。 Your Japanese is pretty good for after only two years。

 So we have Nin N K N Nin N K de Nehga。😊，Jozoに。Notta的でしょ。なtaでしょう。Looks kind of like cry to me， Na。

But。So far good。So here I made some coffee。 Would you like some coffeeoffee sounds great。

 What time is it now， It's about this time， Some of these sentences are a little bit longer than the expected。

 Okay so Alex hands you a coffee after chatting bit more， you get ready for school， right？

 So this is the initial scene， which is great， I would say this is fine。

 one thing I' probably might do is have some nested choices because sometimes you might want someone to like transition always in the next scene。

 but the idea is that there is an immediate response， right， So we'll worry about that as at。

 we can talk about it over here。 but like choices are always from the perspective of the player。

 And so maybe here。😊。

![](img/8ee636b7434260228c14bd833e1071d7_61.png)

You know， we might have next ID over here。I might go and just give an example of something else down here。

 So we might go down here。 You know， there are， there is a a K。 There is a。A variation of choices。

Sometimes you want to have a response。For a specific choice。But the choice。Always leads to the next。

Defa。To the to the next default。So there is a nested response。Example， and so we'll go here and。

You know， we might go， we got to make another scene。 So we'll go here and go down。

It's got to start with a scene， right， So this is got to be I D。It's not doing the scene here scene。

 so we go scene。0，0，2。And then， we have。This。Alex， Ohio， good morning。

 and so now we want our choices， right。And here it says next I here。

 but it's actually called default。 Next I。 It doesn't know what it's doing。So say default。

 I'm not sure why it has。 No， that's correct。That's correct。 Okay， good。 So we have default next。

 but we'll go choices here。Right， and so I'm gonna go here， I guess it square， right。And so。

 in this case。What we'll do。We'll just say response。And in here。

It's just going to be a single response。 It's not going to be。A bunch of stuff。Speaker。I mean。

 this doesn't make sensecause it wouldn't be this， but like。We'll go here， and。

Can we update this to make sense。The response。Nested in the choices。Don't make sense。Because。Okay。

 let's see if it can fix that。 Hopefully doesn't mess up my structure。I mean。

 we could always just say undue。But now we're starting to get the structure of what we want， right。

 so then we have that。 we need to make the scene show up。 And then once we have our scene。

 then it's really just driving the rest there。 So here I'm just gonna。

 I wanted to see if the the sentence makes more sense。 doesn't really matter， but。

I'm going to go here and look at this choice。 So we have。おはようございます。おはようござ。います。阿里。

 I guess it's like Alex， Alex ones。And so I'm just gonna accept this because I can't really see what I'm looking at here。

But here， it says， Alex。Oh， you're， you're up。 Good morning。 choicesice。 Good morning。 You must be。

 Alex。That's right。 I'm Alex。 Did you sleep well， So here。It can't end like that。 Otherwise。

 it's going to go somewhere， right， And that's kind of a problem。 So we can do this。Like this。Right。

 and so。Otherwise， we're gonna end up with too much nesting， right， And， I mean。

 we could keep doing nesting if we really wanted if we wanted a complex structure。

 but we might want to keep flattening out so it makes it a little bit easier。 But here anyway。

 we have good morning。 You must be Alex。 That's right。



![](img/8ee636b7434260228c14bd833e1071d7_63.png)

And so these would naturally transition to this default I based on this scene。

 So sometimes you want to have a response for a specific choice。

 but the choice always leads to the next default， next default I。 So， so there is。A nested response。

 okay。Would it be useful to have that immediate response to go somewhere else。

 but probably doesn't really matter as that would branch off to something else。

 The only thing that we don't see here at the end is where does it go after at the end of the scene。

 So how do we know the conclusion of the scene。 And so maybe here we would have something like dot dot dot dot。

 And then we go， you know，0，3，0。I'm not sure what the number would be here。

 It can be whatever you want。

![](img/8ee636b7434260228c14bd833e1071d7_65.png)

And so here。Okay， well。2是。See you later。Enjoy getting， going to the， going to school， going。Remember。

To visit the post office。Right， and then here。The idea is that it's going to be the transition。

 right， so。When we're at the end here。This will be next。Sing。ID。Right。

 and so that could be the post office。 And so this is what I'm thinking here。



![](img/8ee636b7434260228c14bd833e1071d7_67.png)

I don't know。 It's to do here。

![](img/8ee636b7434260228c14bd833e1071d7_69.png)

And so now what we have is our structured but。We we don't have any logic coded for this。

 and we're not displaying it anywhere。 So that'll be the next step as implementing the actual engine。

 But so far， I mean， this is this is fine。 It's kind of working， right。But， I mean， again。

 we could bring an audio if we wanted to。 This is always the problem。

 You can always kind of like keep stretching， stretching out the requirements。

 I did find out that there's more or better audio generation over with Microsoft， Surprily。

 we used8 of us this generation。 And they have very limited voices。

 But there's quite a few voices on the Microsoft Azure AI platform。

 actually row code in a separate thing here for that。 But haven't integrated it yet。

 But I'm gonna go ahead here。 we'll give this nice refresh here。

 And so we have some really good generation here。 And I'll just call this my visual novel。

 And we'll continue on here， And I'll see you in the next video as we work on the actual implementation of this。

 Okay， Chow。😊。

![](img/8ee636b7434260228c14bd833e1071d7_71.png)