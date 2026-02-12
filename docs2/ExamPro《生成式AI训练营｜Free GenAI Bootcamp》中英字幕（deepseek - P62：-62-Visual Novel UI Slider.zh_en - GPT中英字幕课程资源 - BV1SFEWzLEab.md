# ExamPro《生成式AI训练营｜Free GenAI Bootcamp》中英字幕（deepseek - P62：-62-Visual Novel UI Slider.zh_en - GPT中英字幕课程资源 - BV1SFEWzLEab

All right， let's continue on here。 And so we have。

![](img/02e91e1e898b239782016249d85ace35_1.png)

The new button working here。 So go over here， I can see my new button is working so events are emitting。

 which is great。 I don't really need to print them all to here， but for now， that is totally fine。😊。



![](img/02e91e1e898b239782016249d85ace35_3.png)

And yeah，'m just observing that that is working。 So we should now be able to start the game。

 do settings， other things like that。 I want to focus on the settings pages。

 If we get that out of the way， you know， then we can like reset the game。

 or I guess we'd just delete or make new stuff there， but。😊。



![](img/02e91e1e898b239782016249d85ace35_5.png)

That's where I want to focus on first， right。Over here， we have。Open settings。

 continue game start games， so。I'm gonna go here and we'll just say， whoops。Continue game。

And in here I know that we have the EV dot scene， so we have that。V dot scene。

And then we have the button itself if we need to do something with it， so。

How are we going to transition from one scene to another， There supposedly is the scene trans。 Well。

 actually， we're not even transitioning scenes。 are we。

 We're just showing UI in place of where we are if we were， if we were to go to the settings。

 And this is not actually the one that I want。 I want the settings， the settings game here Se game。

 So we're actually not transitioning right now。 We're just building another UI。

 that's going to get displayed over top of whatever existing UI we have and then lock out any controls。

 which well figure out as we go here。 And so here this is console log。Settings。You I。And over here。

 we have our settings G， where we have some stuff。嗯。What do we have in here？Hi panel。scen input。

Handled dragging。 We do need a draggy thingy。But there are a few things we need to set up here。

We have the UI here that's being set here into the， well， this is the UI manager。

 but we go back over to our menu settings here。Oh no， not menu menu settings scene。And in here。

 we need to set up the other scene。Set up。Gy， okay， that's fine。Where did we create the UI。

 I could have so it was in here somewhere。Cre your live buttons。 okay， so it's right here。

There's this one， then there is the settings UI。UI settings， and this will be new settings， UI。

This one here doesn't need an input。 it's going to take up the entire screen。

 we'll say this UI settings。Dot create。 so that's going to be our。Our stuff here。

 I'm going to go over into our index HTML。 we're going to go ahead and grab up here Se UI。



![](img/02e91e1e898b239782016249d85ace35_7.png)

Settings UI， and if I go into。Here。We got a menu。嗯。The， yeah， the， the two things we need is。

 is the UI manager。 So we need the UI manager and the scene。

And here we have a scene and we have UI Manager whoops。So this is U I am。

 We just call U I am in here。 this it's a little bit more clear。

 And so now what we need to do is we need to create some options。

 So I'm just trying to think of like。What configuration options do we have。

 I guess we would know we went back to our config page here。And so you can see here that we have。Oh。

 it's not here， it's in our settings。We have language duall。Tech speed， auto advance， auto speed。

Background volume。 So we have volume font。 Those are definitely gonna make things。 languageage。

 typewriter effect currency。 These are these don't go in here， right， These shouldn't be here。

So take those out。And if we go up to here。We'll need our create function， right？

And so we'll know we'll need to make a whoops。This dot create background B， G。

 That'll be the first thing that we need this dot。Create。

 I don't like that it keeps starting to autocompte that。 We'll have create。Bgm。BGm。Volume slider。

And then we'll also have the sound effect slider。Okay。And then we also want fonts。

 so we'll say create font slider， we've got a lot of sliders in here， not buttons， so to speak。

And then this dot actions， create actions。Right。There's things like tech speed， dual。

 I'm not really sure about that right now。 So I'm gonna leave that alone。

AndSo we have create setting panels。 So first， we have a background。

So I'm going to go ahead up here and we'll just say create PG。We'll bring this on in here like this。

Okay， and so that's going to。Create a rectangle， I'm hoping that that covers the entire screen。

 I'm not sure if it does， but hopefully it does。We also have a title。

 I guess I can bring it into here for now， which is fine。We have our create。Actions。

So this would have our close button。Now， if we want a close button， we can just use our。

Budton code for that。 But we will just move this over here for now like that。

Make panel interactive and dragable。 So I'm not exactly sure what it thinks there because this one's creating a panel up here。

 right？This says settings， which is not， it's not really clear。

 maybe it means like the whole thing is draggable。which is not a bad idea。

 but it's not exactly what I'm looking for， I'm not looking for a draggable panel。

And so I'm going to go ahead and we have high panel settings。 So yeah。

 not a whole lot of stuff in here to work with。 I know that we want to have two buttons。

 So if we go back into our menu Ui here。Right， we can。Cray sells a couple buttons。

I'm going to just call this one this。u。Create button。And we just delete this out。

 We don't really really need that in there， and we'll see what we have。 So we need in here。

It'll say save。Re。Size X， Y position。And I'm not exactly sure where we want to place this here。

 but we'll just maybe for now，'ll just say constant X。U。I don't know。

 I'm just going to put 100 here and then for why 100 here。

I'm not really thinking about this too hard that we're going to say like button。With。You know，300。

And button height。80。Okay， so here。Like that。So we have our reply button。

We need we need two separate buttons， so we need one for create and apply， so I can say create。

Button， apply。Oh， come on。 Sometimes it's just a little bit too aggressive there。Create。Biden。Cancel。

I don't know why it's having a problem with that there。But I'm going to go ahead and just。

Grab this code like this。What's its problem oh double clearly here， okay？

And then here we'll just do this again， these are going to be on top of each other for now。

 I just don't care I just trying to get them in general， to say cancel。Cancel。

 and we're going to have to come up with better， unique names than that as that's not always clear。

Like， like settings apply。Settings cancel。 that's probably better there。 And so then in here。

 we say this dot create apply this dot create cancel， right， So now we have those there。嗯哼。😊。

So that's going to happen。And we have our background， which is supposed to cover the entire width。

So here I would probably make the width the entire screen。

 so I'd just go here and say width equals this dot dot scene。Camera。

With I want it to be the entire thing here， I know that we set it in our main scene so if we go over to menu。

And here we can probably get the full size here somewhere。Cameras main， yep， so that's what we want。

Okay， so now we are starting to get。

![](img/02e91e1e898b239782016249d85ace35_9.png)

Some things set up here， like the background。And actions， the truck is going to be the slider here。

 So I'm going to go over。I really do need help with this for the UI stuff we'll make a new one here called US Sr。

UIsder。js。Okay， I need to set up the skeleton for this。And we'll open up button here。

 and then we'll bring in slider。sorryrry， class。UI slider constructor that looks good to me。

As a start。And I'm going to go here and I'm going to be very specific。

 so I'm going to tell like I need to code a UI slider for phaseser。In the UI slider。J。嗯。Look at。

UI builder。To get an idea of code styling。Please don't change any other。

File other than U I slider or JS。Okay， so we'll go ahead and let that do that and we'll see what it comes up with。



![](img/02e91e1e898b239782016249d85ace35_11.png)

All right， let's take a look and see what it's produced。Create a track element。

 implement a drag functionality here' is an example of how we can utilize it and here is the UI slider volume change it does need to include。

The name of it inside of it。 Otherwise it's not going to be great for us。

 I almost kind of wonder if I should have put the。The name somewhere else， but it's fine。

 so we'll take a look here and。There's a lot here。The only thing that I don't think it might be doing。

 did it actually add in the event handle？Sos like an event handle because that has to be in the actual event emitters。

 it is。Okay。So yeah， I mean， I hope that just works。

 that'd be really nice I'm going to go and close this out。We're going to go over to our。Index HTML。

Here。And I'm going to go ahead and do that。And I'm going to go into。Here。And。

I'm going to go ahead and grab this here。I mean， I really only need to see the sliders right now as we can work on these other ones。

 but。We'll see how it goes。And yeah， here we have a slider， yep。I wanted that。 yup， go make it。

 go make it， go make it， go make it。 You can go ahead and do that。 There you go。Okay， so we have now。

That one there。And for now， just to keep it simple。

 I'm going to comment out this one and the font slider。And this。

 And so this is all we're going to have。 And so hopefully that opens up。 Well， actually。

 we don't even have a way for it to open， right， So that is one trick that we need to figure out。

Is how do we show and hide this U I， So I would probably go here and say。We have the show function。

And then we have a hide function， right， But right now， if it creates， it actually should show up。嗯。

Itscently here， but let's go over and see what renders out because it should render on top of our existing one。

I believe， soll go back over to here。

![](img/02e91e1e898b239782016249d85ace35_13.png)

Into our game here。And we'll go back give this a nice refresh。



![](img/02e91e1e898b239782016249d85ace35_15.png)

And it's not serving up anything。 So maybe there is a bit of an issue in serving。



![](img/02e91e1e898b239782016249d85ace35_17.png)

嗯。I think we're just in the wrong directory， that's probably why。So if we go into visual novel here。

And then we do MPM Run Dev or not MPM run dev HP server， Then we can get what we want。



![](img/02e91e1e898b239782016249d85ace35_19.png)

So we'll go back over to here， I need a new tab， I lost my tab。



![](img/02e91e1e898b239782016249d85ace35_21.png)

Local host 880。And I mean， it should be serving up the correct location now。There we go。

 We do have an error as an issue of cameras。

![](img/02e91e1e898b239782016249d85ace35_23.png)

In are setting U I。 So I thought that would have worked， but I guess not， so。Sne cameras。



![](img/02e91e1e898b239782016249d85ace35_25.png)

So if we go back over to。Our menu， wherever that is。Because this is on the scene， right。

 so we should be able to call scene。camers。main。Unless that's not set。

 they actual scene for some reason。Wes just set here， but。So the other one is set。

 or is it set after the fact？Up here， it's set right here when it's initially created。Interesting。嗯。

So if we go back over to our。Game scene。 No， no， our menu scene。In here。We never passed any values。

 so that's our problem， so we'll go here， yeah， there we go， that should fix it。

I don't think we have to restart， but we'll restart it anyway。Maybe we'll go back over to here。

Just w to get that closed out of here second。Just a moment， just a moment。

And we'll give us a nice refresh here。X is not defined。



![](img/02e91e1e898b239782016249d85ace35_27.png)

This is in our settingstting UI on our panel。Fair enough。

So we are in our settings U I X is not defined。 I mean， this is width and height。 I mean。

 x constant x is going to be 0 and constant y is going to be 0 as well as we don't need it anywhere else。

Here we want it to span the entire width。 We don't need to set the origin to 0。05。

 We can just leave it alone as it is。 Looks like it's trying to make this transparent。

 I don't want that。 I want to be white。 It's going to make the background black。

 which might be a noninsue， but we'll see here。 the text is white， so that should be fine。

I don't know what the slider should look like。 So that's going to be a question that we'll need to answer as we worked with this。



![](img/02e91e1e898b239782016249d85ace35_29.png)

![](img/02e91e1e898b239782016249d85ace35_30.png)

So go through here。And we probably obviously have a new error。Create sliders not a function。

And it isn't a function if we go to our。Game manager or game UI manager under our managers here。

UI manager。Yeah， we don't have that。 So we'll go create。Slider option， slider like that。

 And so that will set it up。 You can see there's not much going on with our UI manager。

 We might be able to move other stuff to this later on。 I'm not really certain。

 like showing or hiding a U I might be something we might want to do。

Or maybe we should be registering our UIs with the UI manager as opposed to directly into the scene。

That actually probably makes a lot more sense， but we will have to think about that as we work through this year。



![](img/02e91e1e898b239782016249d85ace35_32.png)

So I'm going to give this a nice refresh here。Another new error here and we have sizes required。

Apparently we don't have size specified， are you sure？



![](img/02e91e1e898b239782016249d85ace35_34.png)

I mean， it generated out the codes if it's not there。



![](img/02e91e1e898b239782016249d85ace35_36.png)

Yeah， this doesn't follow the specs。So let's go back over to here。Yeah。

 this is what it's expecting as the slider information。So let's close out this here。And。

We have men and Max。So we might， yeah， we might want to say。I guess it kind of makes sense。

 Min and Max。The it's not width and height。 We'll just go size。380。And then here we have position。

And this was 10000。Okay， I can already see that we'll need an interval。

 Thatll be definitely something that we'll want。And there we go。 So we'll go ahead and stop us。

 start it back up。

![](img/02e91e1e898b239782016249d85ace35_38.png)

I' go back over to here， give us a refresh。

![](img/02e91e1e898b239782016249d85ace35_40.png)

And now we have a slider Now the only thing is that this is going in the top left corner in some weird way。



![](img/02e91e1e898b239782016249d85ace35_42.png)

So I mean， the slider is good， but we need to fix the background that's going to be definitely something that's kind of annoying。



![](img/02e91e1e898b239782016249d85ace35_44.png)

I'm not sure what the default origin is， but that could be our problem here down below here you can see set origin is 00 like that。

 I might say set origin and put it00 and see if that resolves that issue here。



![](img/02e91e1e898b239782016249d85ace35_46.png)

AndSo that is definitely resolving our issue。 I'm just going to change the color a little bit here。

 Maybe say F F in the middle。 not sure what that's going to do。



![](img/02e91e1e898b239782016249d85ace35_48.png)

![](img/02e91e1e898b239782016249d85ace35_49.png)

Great， so now we have green。 that's a little bit hard on the eyes。

 I just want to shift it a little bit。 So I might just go here and say。



![](img/02e91e1e898b239782016249d85ace35_51.png)

2，2，2，2，2， two， I'm not sure it's going to be some kind of gray， right？



![](img/02e91e1e898b239782016249d85ace35_53.png)

![](img/02e91e1e898b239782016249d85ace35_54.png)

There we go， and so now I can kind of distinguish that the slider here looks like it might be centered as well。

 I'm not exactly sure。嗯。M。

![](img/02e91e1e898b239782016249d85ace35_56.png)

But definitely works， which is really， really nice。So if we。I'm trying to think about the。The slider。

Like if we go position zero， zero， what do we get， right， we go position  zero zero？

Is it going to be right off screen？

![](img/02e91e1e898b239782016249d85ace35_58.png)

Yeah， see， so that's not exactly working for us。So we need to fix the positioning。 Now。

 I like the code so far， so I don't want to lose what we have。So got this nice refresher。



![](img/02e91e1e898b239782016249d85ace35_60.png)

And I'm gonna hope that this can be implemented by here。 but we all accept all， accept all。

 accept all， accept all。 Okay， so。I want it so that when I set。Position 0。

0 that it won't show off screen。I want to。The position doesn't appear。To be origin。

Top left for the entire。Component for the UI slider。Can we fix that。

Hopefully it understands what I'm trying to say， we might have to carefully look at what it says here。

Bluser wants the position to be at the top left corner。I mean， if UI button does that。

 I probably want to fix UI button too because I think it's easier to position things when they are in the top left。

嗯。So we'll let it go ahead and do that。 I didn't know the UI button was like that。

 but we'll just wait for that fix。 All right， here it's suggesting that it has fixed it。

 I'm gonna go ahead and accept all and just check。 It does have a lot of stuff it's suggesting here。

 But as long as it works。 because this stuff is always really tedious， then I'll be happy。

 So we'll go ahead， give this nice refresh。😊，And is it？There we go。 Yeah， yeah。

I would say that it's a little bit cut off， though。So， you know。I'd say it's very close。

But the slider button。Isappearing。Off screen。 so it has to take into account。Everything。Okay。

 so let' give it another try there and see what we can do。 Alright， so I don't know。

 let's see if it it fixes the problem。I'm not sure if it can understand what I'm saying here。

 there is also just if it's good enough， it's good enough。

 but we'll go ahead and try this again here。🎼And。I mean。

 it changed it so it didn't have that problem， but I guess that works as well。 So that's pretty good。

 The thing here is that this is going from0 to one。 So now I'm thinking like。😊。



![](img/02e91e1e898b239782016249d85ace35_62.png)

。You know，Does it handle fractions， right because it's going between zero and1？



![](img/02e91e1e898b239782016249d85ace35_64.png)

So I need it to work so that it is fractional。 So I'm just saying it here because。嗯。嗯。

Now we could just have it out of a percentage， right？That's something that we can do but。Hm。

I'm trying to decide here。Yeah， what do we want to do the slider。

 Because I want the the audio to go up and down as we slide it。But。10d%， it was really loud。 zero is。

 is whatever。 But you know， we can make it 100%。 I think that's what we should do， so。

Maybe what I'll do。 Well， first of all， I'm just gonna change this out of 0 to 100 because that's what it would actually be。

Or going be 0 to 100， right。And maybe this would be 25， is there initial value here。

So I'm going to go ahead back here and give this a refresh。I got also moved it up there。

 I like how to put the label in here。 I guess it's good to have the label。😊。

But now we can see our slider here zero to 100， so that is good。



![](img/02e91e1e898b239782016249d85ace35_66.png)

Yeah， I'm just thinking about this。No， I guess it's fine， but I guess it's fine because。

We can get the value， and then we can translate that over。

 So now we just need to get the event handler hooked up。



![](img/02e91e1e898b239782016249d85ace35_68.png)

Right， so here we have this。Listen for changes on the event Ui slider settings Bg volume change。嗯。

I mean， you can do that。 I mean， it's not actually doing that right now， is it？

Like we don't hear the volume changing， right but？So we have crpe volume slider。

I think right now because set BG volume doesn't actually change the audio element。

 let's go over and take a look here。

![](img/02e91e1e898b239782016249d85ace35_70.png)

To the audio manager。If we were to change this。No， it actually does adjust it on the actual thing。

So I guess my question is it even calling this？Well。

 didn't we have our calls here earlier and it would tell us， I don't think we got rid of that code。

So I'm gonna slide it here。 we're get an error。

![](img/02e91e1e898b239782016249d85ace35_72.png)

SetBG volume is not a function， right， so go over to here。And。

We do have this on the audio manager here。But it's wrong。 It's supposed to be audio like this， audio。

 right？The only problem is that this is going to set it and make it persist。

 whereas we don't want that to persist permanently。

 so this is technically not correct because we have that apply button。

 whether we want to keep those settings or not， but we're just going to try to see if it even works。

哇喂哇哇。

![](img/02e91e1e898b239782016249d85ace35_74.png)

Alright， so right now it， it turns it into always 100% over。 Okay， I see。 So what we need to do。

We got this data value right， and so we say data do value divide by 100。0。

 and this will be the actual value that we set it to。

Because we need to take that 10 and turn into a decimal point， and so that should fix that issue。

 I apologize for the loud noise for folks here。

![](img/02e91e1e898b239782016249d85ace35_76.png)

The only thing is that it's not。

![](img/02e91e1e898b239782016249d85ace35_78.png)

It's interesting because it's not actually saving it。 It is setting it differently， right。

 But if we go over to here。I guess the thought is like， it's not persisting。

 though say that safe stuff， because that's obviously not getting set。

 But I guess the last thing we'll do here。 I mean， we have the slider here and we can finish building it。

 I got to go inside and。Make dinner soon， but。I'm thinking maybe the last thing we do here is load in the actual。

Ss for， obviously， this is kind of in the way right now。



![](img/02e91e1e898b239782016249d85ace35_80.png)

This menu from behind but。But obviously， that one is。



![](img/02e91e1e898b239782016249d85ace35_82.png)

Harder for us to figure out here it。

![](img/02e91e1e898b239782016249d85ace35_84.png)

So let me hold on second here。 I'm going to go。And， I mean， I feel like the hundreds really high。

 I'd almost like take the sound and cut it in half and like， like， do the math from 50 to 0。

 but that might be something we adjust later on。

![](img/02e91e1e898b239782016249d85ace35_86.png)

So the only thing I want to bring in here is the actual settings， right。

When we create the slider volume。We said it。Here。As its value。

 But we can get that from if we do this dot。Sne。Dot G。Dot settings。Dot get。B，G volume。

Then we get the actual value for the volume。And so that will help us set it here and so now it should come in and whatever that number is。

嗯。RightSo if we go back over to here。Says zero。Oh， you know why。

 I think it says we have to do some math on this。 so here we have two times it by。Constant volume。

Or I mean， we have it as a constant。 So I'll say let。 so volume。Times 100。0 like that。

And that will get us the。嗯。So if we divide by 100， If we times it by 100。

 we should get the value that we that we actually want， right， So we go to do that。



![](img/02e91e1e898b239782016249d85ace35_88.png)

But it's not， maybe it is set to one， actually。IfWe go into our global settings。

 wherever those are into the default ones。Not settings GY， but the settings manager。Here。

 it actually literally is set as one because it's that freaking loud。So maybe what I might do here。

Cause the audio is really loud。 It should never really be that 100%。 I feel like we need to。

Adjust it。 So the maximum value value me is here。 actually， but you just change this to 50， I think。

If we changes the 50， that would probably resolve。 Well， not necessarily because。The number here is。

50。Right， and。HI'm thinking about this for a second。So if we have 50 here。If we have 50 there。Well。

 hold on。 what does 50 sound like first。We need to figure out what is the loudest this should be。

So 50's too loud。20 is pretty darn loud too。So，10。10 sounds like the most reasonable to me。

 So I'd say like the number between 0 and 10。 Oh but the thing is that the number has to be represented by 0 to 100。

 So it has nothing to do with the slider here。 it has to do with the value that is set at this level here。

 So if we have a value here and the number is 100。Right， we want to translate the number over here。

 So I' got to go here。 And so take the range from 0。So the data value represents like zero to 100%。

But the value。Range of setting the audio。For BGM。Is。0 to，0。2。Okay。And that's not correct。

 So we'll go ahead， and I'm gonna go over here。And asked like， hey， can you， can you figure out。

 can you， Can you do the。I really hope it doesn't do anything crazy to my code。Arange right there。

MAnd so I'm hoping that this will fix that issue。I think that we'd never want it to be that value completely so。

U。No， no， no， no， no， no， no， no， no， no， no， no， no， reject all， stop， stop， stop。No， you know。

 I told you what code。To change。Okay， this line here， like it's not doing what I asked it to do。

This line。No other line。 Just this line fix。啊ha。😊，Thank you。Is it done？Great。

A little bit silly that it was doing that。 But that's okay。 We're going to go back over to here。

 It's crazy。 Sometimes it just goes somewhere else。This nice refresh here。



![](img/02e91e1e898b239782016249d85ace35_90.png)

Now， the thing is， is that one doesn't necessarily represent its actual value， right？

So now we need to go back up to here， maybe it was trying to do that。

 but I wasn't ready for it to do that and here。The value represented is not one。 Okay， so now。

I trying to see， does it actually select the line here， it doesn't we'll go here。

 maybe that's why I didn't do it。Okay。Now fix it for here so that it takes that 020。

2 value and it correctly。Mps it。The other way to0 to 100， Okay。

 and probably the formulame looks really similar。 I'm not the best of math。

 so I'm going to let it do it for B here。

![](img/02e91e1e898b239782016249d85ace35_92.png)

Okay， that looks probably right。啊。Okay， good。 And so now I'm going to save that。

 we'll go back and see if it actually mapped it。Right， we'll go down here。Refresh it。

And that says five， so that's a little bit more accurate。🎼Si。

That's nice now would the same thing be for other stuff I don't know。

I I still have to work through it here。

![](img/02e91e1e898b239782016249d85ace35_94.png)

But I didn't mean to close that。 But yeah， we now have。That implementation done。

 so we'll go over to here。Give it a second to show us what files we change， we clearly change files。

We'll say update slider。Okay。And so that's this video we need to finish up the implementation of this page now you know there's font sizes。

 there's other like we could represent font size with a value that people put in。

 but probably a slider would be just as good as I don't think people really need something other than a slider we might want to limit it to whole numbers。

But what else is there， they we might want to drop down。

 but we could probably use like a a pill button in order to do that。

 So if we go back over to our components， wherever that was。

Its sorry our settings in here to see what are the settings we have。Speed， that can be。a drag speed。

 same thing。 unless's go I put a number in here。 So toggle or sorry， slider， slider， slider。

This is a sure or false， so that can be a pill， so then we just need another pill one。Yeah。

 sliders and pills， that's pretty much all we need so。You know， we call that a toggle， but。

I'll do that in the next video and yeah。