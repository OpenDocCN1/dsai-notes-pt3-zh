# ExamPro《生成式AI训练营｜Free GenAI Bootcamp》中英字幕（deepseek - P20：-20-Backend API Writing Backend Frontend Tech Specs.zh_en - GPT中英字幕课程资源 - BV1SFEWzLEab

Hey everyone's Andrew Brown in this video。 what I want to do is rebuild the backend flask completely from scratch。

 Now I originally built this using Python。 I'm not the best at Python。

 but maybe it would be fun to build this in a target languages I don't know very well。 I mean。

 I have code to go before， but I would say that I'm not doing on a regular basis that would 100% know how to utilize it。

 So that might be a fun language for me to target this。

 The thing is is that if you are if you have good technical documentation in terms of your API specification and your schema and those things it's very easy to get these things to write today。

 I'm going to be using windsurf， I'm not using any fancy features of windsurf。

 I'm just using cascade on the righthand side。 I am using a paid version of it。

 which is the unlimited version， which is kind of pricey。 if you can't afford that totally fine。

 go use Gitthub copit， which is 100% free， but the experience is gonna be different。

 You have to work it through yourself。 So you saw a moment ago I was writing this API spec。

 But what I'm going to do is I want to basically start。Over from scratch with nothing in here。

 And I mean， this is a technical spec over here， which is fine， which will send to the recycling bin。

 But what I want to do is open up the specific folder I'm going to be working in。

 And so this is the frigene bootcamp。 and I already have the link portal。

 and I have a front in and back in here。 So I'm going to open this up。



![](img/b1e2bb7066de98c5786115c0dc7edc75_1.png)

![](img/b1e2bb7066de98c5786115c0dc7edc75_2.png)

Justin in windsurf here。 And so this is the folder that I have here。 Now， I already have a back end。

 But what I'm gonna to do。I'm gonna do something crazy。

 I'm gonna go ahead and delete this entire folder。 I'm gonna leave the frontend react around。

 It's up to you if you want to keep it around。 But because it's already done， technicalnly。

 Cascade could use it to reference this materials to help me produce it。

 But if we wanted to start from ground 0， we could do that as well。 So I'll delete that out as well。

 And yeah， now I literally have nothing。 So we're starting from scratch。

 I'm going to go ahead and make a new folder here。 And I'm going to say back and go。😊，Right。

 we're going， we're going wild here。 And if you could tell， it's still a little bit cold in here。

 So I got my snowsuit on。 but it's not a big deal。 And so I'm gonna start a conversation a chat over here with a Cla。

 and we have the option of a few models。 I personally like cloud 3。5。

 It looks like since the last update。 we can see that its showing us our credit use。

 Also if I go down below here。 I'm on pro limited。 And so it tells me how many premium flow actions I have and some other stuff。

 I don't know much about these things。 All I know is I'm gonna go ahead and start typing here。

 And depending on what task you're doing might be a little bit different。

 You can see there's flash beta， which has 0。25， which is really cool。

 But I'm gonna stick with Cla for now until it becomes an issue。 So actually， you know what。

 we'll switch over to。😊，No， for now， what we'll do is write our doc。 that what we'll do。

 So we'll make a new file here。 I can call this technical specs。Okay。

 and so there's a technical spec。 I'm gonna open up from earlier this file here。

 which kind of describes some of our stuff。 Now， you can see I started writing some of these endpoints。

 Now， the question is， is it right， I don't care。 I'm just gonna ignore this stuff for now。

 And all I want to grab in here is some of the technical restrictions。 So I want to grab。



![](img/b1e2bb7066de98c5786115c0dc7edc75_4.png)

![](img/b1e2bb7066de98c5786115c0dc7edc75_5.png)

The first part here， the business goal。 so I' going to grab this here。

And we'll go ahead and paste it in。And so I'm going to call this technical， technical specs。

Business school， a language， language learning school wants to build a prototype of a learning portal。

 which will act as three things， an inventory of possible vocabulary that will be learned。

 Act as a record learning store providing corrected wrong pras vocabulary。

 a unified launch pad to launch different learning apps。

 So those are the three things that it's going to do。Um，And so I to call this u tech back end。

Back in server， technical specs。 A language learning school wants to build a prototype type of a learning that will do the following things。

 So that is our business goal。 Let's talk about API specification。 Well。

 maybe we should talk about technical requirements。Technical requirements。 the back end。

The back end will be built using Go。 That's right。 The back end will be built deployed using Docker。

 We don't have to do that， but we could do that。 I don't want to do that。

 I don't want to do that here today。 the database。Will be SQL light。

 I'm going to keep sticking with SQL light3 here。We'll see what else suggests。

 The API will be built in gin。 Gin is a go framework。 Again， I'm not super versed in these things。

 but I know enough to remember the names of them。

![](img/b1e2bb7066de98c5786115c0dc7edc75_7.png)

So I'm just going to bring on down a menu here。 we're just going to look up go Jin。

So it is a framework that we can use。

![](img/b1e2bb7066de98c5786115c0dc7edc75_9.png)

That's probably fine。 It has a router， all this other stuff。 So that sounds fine to me。

 Let's go ahead and do that。 So we'll go here and say the API will built be built using Gin。

 The API will。Always return JO。The will be versioned with7 version， I don't think we'll do that。

That sounds a little bit like too much work there。So， there's that。呃。I don't know。

 There's like an equivalent of。Rake task。But this is our starting point for technical requirements。

 We also have our database schema。We have the following tables。So the tables that I want is。

 I'm got to match what I had before words。Word groups。Groups。Study sessions。Study activities。

We'll have study。呃。Word。Review items。We have that word word groups， groups， study sessions。

 study activities， word review items。 If we go back over to this。 I'm pretty sure that's what it was。



![](img/b1e2bb7066de98c5786115c0dc7edc75_11.png)

![](img/b1e2bb7066de98c5786115c0dc7edc75_12.png)

Yeah， that's everything， right， So we'll go back here。 And so this will be。Join table。

For words and groups。Many to many。Right。Sttores， vocabulary words。啊。Thematic。Groups of words。

Represents records a study sessions。嗯。如边。Word review items。A specific。Study activity。呃， linking。

Liinking a steady session to a。A group。And then here this is records a word So a。Record of。

AOf word practice。Weather。Determining。If the word。Was correct or not。 Okay。

 so here we're starting to get kind of our stuff here。 And we do want to do API and points first。

 but we want to just describe some of the stuff in more detail。 So I know for words。We will have。

I'm trying to indent。 It's not let me indent。 It's being a little bit silly。

And I want to have we'll have our ID。嗯。I think for this， I use。嗯。I would have the Japanese word。

So have the Japanese word。The Ramaji， the English， and then I have parts。

 which is Jason Jason structure。Sping parts of。呃， specifying the。The anyway， well， well。

 we'll talk about this later on the parts。So we'll go down， we have word groups。

This should be an integer。This is a string。This is a string。 This is a string。This is JO， right。

Jason。Then we have a word group。 So word groups is a menu to many。

 So it's going to have a reference to a word group。 And that， that's right。

 It should have its own I D， as well。That we have our groups that's ID and name。

 that's totally correct。So that is good as well。And again， it's auto completing here。

 So let's figuring it out。 So we have。Integer group ID， user ID kind of right。

 but we're not going to have user ID。There are some other things that we said over here。

 so technical requirements。There will be， there will be no。Authentication or authorization。

Everything will be treated。As a single user。Okay， soca down below here was trying to generate and saying like。

 oh， you want user I。 And I'm like， no， there are no users。 So we have study activities。Oh over here。

 So have group I D。 This is the bird review item。 So it has to。 Well。

 the thing is it doesn't really need that。 All it needs is the word I D。

 But what it really needs is actually the study sessions I D。 That's what it needs。

 And then we need to know whether it's correct。 This will be a boolean。 And then the created at time。

 We definitely need that。 So we have our study session。 This should have it created at time。

Everything should really have us created at time if we can have it。

 I guess doesn't really matter for these other ones。 Word， word groups doesn't really matter。

 We have word review items。Well， you know what I think I got mixed up here because I was thinking this one was Word review items here。

So， this actually should be。This is study sessions， right。

 So this one actually is going to go down here。 I got mixed up。

And this one here would actually have a group I D。 That's right。

 And it would have it created at time。But it would also have a study activity。There we go。

So now we've defined our schema， you can see it doesn't take too long here we're 10 minutes in。

 and we've already defined our schema。 Let's go down below and think of our API。

So we know we need to get words。We also need to get word I Ds。

 It's getting a little bit aggressive here。 I don't want that much stuff。

But I do want to get a group to see the groups。 I do want to be able to get an individual group。

I want to be able to get a few other things here， like words。

But you know when I was building this out， I ended up having to have more components on the pages。

 And so I would say that the front end really did influence the way I was building this thing。

 So like if I go back over to get this running in another one。

 maybe we can take a look at it and try to figure out what these are because when I originally did this。

 I had very bare bones APIs， but then I ended up implementing more because I wanted to show more stuff on the page。

 But anyway， what I'm gonna to do here， is I'm gonna get the back end running。

I'm doing this off screen in visualsual Studio code， this is the other one that I just have here。

Right， that I showed you earlier。Because I know some folks said， well。

 can we have some screenshots if we can see what's going on， Andrew。

 And so I they go run this in the background。I'm going to go ahead and grab。Gra the link for this。



![](img/b1e2bb7066de98c5786115c0dc7edc75_14.png)

So now we have our portal here。

![](img/b1e2bb7066de98c5786115c0dc7edc75_16.png)

Right， I'm going to just switch this to light mode。Yes， there's a light mode。



![](img/b1e2bb7066de98c5786115c0dc7edc75_18.png)

And so we have different screens here。 So we have this page， which is the dashboard。Okay。

 and maybe I'll take some screenshots so that we have some references。



![](img/b1e2bb7066de98c5786115c0dc7edc75_20.png)

So go here。 and I'm just gonna go ahead and make a a new folder。Can I make a new folder。

Reference images。And in here， I'm gonna go ahead and start placing them in here。

 So we just got that one。

![](img/b1e2bb7066de98c5786115c0dc7edc75_22.png)

It's kind of annoying because I got to open paint every time。



![](img/b1e2bb7066de98c5786115c0dc7edc75_24.png)

But I'm going to go ahead and just save each of these individually， save as a P and G， yes。

And so I need to navigate to wherever this is。 Give you just a moment。Do you find that sites。

This is sitess。Omen King Free Gen EI Lng portal reference images。

 So this is gonna be the dashboard as a reference page。Dashboard PNng。



![](img/b1e2bb7066de98c5786115c0dc7edc75_26.png)

Okay， so we have that one。Then I'm going to go back over to our browser again， wherever that was。

Already lost it。 Let me go find it。Too many things。 too many things。



![](img/b1e2bb7066de98c5786115c0dc7edc75_28.png)

It is this one here。So we have that there。

![](img/b1e2bb7066de98c5786115c0dc7edc75_30.png)

We have our study activities。So we have this page here。



![](img/b1e2bb7066de98c5786115c0dc7edc75_32.png)

![](img/b1e2bb7066de98c5786115c0dc7edc75_33.png)

Okay， no ma， no crazy magic here。 Just taking screenshot。 Sa S P and G。

We have the actual launch page if we go into it here。



![](img/b1e2bb7066de98c5786115c0dc7edc75_35.png)

So。Then we can go into this page。 This is， we can view it， right， We can view it。



![](img/b1e2bb7066de98c5786115c0dc7edc75_37.png)

So we have this。

![](img/b1e2bb7066de98c5786115c0dc7edc75_39.png)

![](img/b1e2bb7066de98c5786115c0dc7edc75_40.png)

Go ahead and save that。 save us P And G。This is the study activities。Show page。Right。



![](img/b1e2bb7066de98c5786115c0dc7edc75_42.png)

Then we have。The launch， that's its own page。

![](img/b1e2bb7066de98c5786115c0dc7edc75_44.png)

You can see the links up there too，h。

![](img/b1e2bb7066de98c5786115c0dc7edc75_46.png)

So we have this。So we'll go ahead and I'll paste that in here。And it'll save this。 This will be our。

Study activities。Launch page。I'm going to go back over to here。 We're going to go into words。

 So you can see we have a list of words。And'll save that， save as words。We have。

An actual word itself。So， we have。New pace， save as。PNG。Word。We'll go over to here。

 we have word groups。Paste file， save as。PNG。Word groups。



![](img/b1e2bb7066de98c5786115c0dc7edc75_48.png)

We have an actual word group itself， so we'll click into this one。



![](img/b1e2bb7066de98c5786115c0dc7edc75_50.png)

And I'll paste this in file， save as PNG。Word group， not groups， but group。

Then I'll go over to this one here。 We have sessions， so here we can see our sessions。

We'll go back here， paste this in， file， save as。Study session。We'll go over to the next part here。

 By the way， I realize my heads are little big and get right down small here。 We got study sessions。

We did that， right， We did this one， right， I don't。 I forgot already。



![](img/b1e2bb7066de98c5786115c0dc7edc75_52.png)

Yeah， study sessions。We clicked into a study session。 I'm not sure about that。



![](img/b1e2bb7066de98c5786115c0dc7edc75_54.png)

Oh， well sorry， the study session is right here。 we click here， that's the study session。Okay。

 so we'll do this。Go ahead， say false say as。Study session。嗯。I'm gonna save that， but I。

 I have a feeling that we didn't save study sessions。 So I'm gonna go back one。

 And this will be study sessions。

![](img/b1e2bb7066de98c5786115c0dc7edc75_56.png)

![](img/b1e2bb7066de98c5786115c0dc7edc75_57.png)

We'll say save as PN G study sessions。 Okay， so that ones saved。 And then I'm gonna go into settings。

 There's not really anything。 Well， there is a reset history button， which I did implement。

 So there is that。And so we'll go ahead and we'll say， we'll paste that in。If it save as。嗯。Setting。

 so we have all these particular pages that we can work with now。



![](img/b1e2bb7066de98c5786115c0dc7edc75_59.png)

We have to kind of think about like what's on each of these pages so like we know we want to get words and words ID。

 but there are some subgroups that we might want And so sometimes what helps is if you know what you're building as your front end。

 then you can kind of understand what you're building is your backend And so I know we're focusing on our backend server technicals spec but I'm going go ahead here and I know we don't have a front end one。

 I'm just gonna to move this out here。

![](img/b1e2bb7066de98c5786115c0dc7edc75_61.png)

![](img/b1e2bb7066de98c5786115c0dc7edc75_62.png)

And I'm going to rename this to backend technical spec。I'm going to make another file here。

 we'll call it front end technical spec。So somebody' got to jump between the two that you want to define。

 right？But I would say that when I created the front end or the back end， I created。

 and I made the front end。 and then I was iterating on creating new endpoints。

 And it was so easy to make extra endpoints。 But if we can kind of square them all off in one go。

 that'd be really nice。 because we don't know exactly what endpoints we need。

 So what we need to do is take a look at our U I here。 I still have it here。

 And so we have our dashboard。 And so we have some kind of study materials here。

 And so we need to describe what's going on on this page。

 I'm going see if there's a way that I can split this here。

 So it's a little bit easier so we can type while working with this。😊。



![](img/b1e2bb7066de98c5786115c0dc7edc75_64.png)

![](img/b1e2bb7066de98c5786115c0dc7edc75_65.png)

![](img/b1e2bb7066de98c5786115c0dc7edc75_66.png)

So we'm going to bring this on over here。 We'll close out this and bring this over like this。



![](img/b1e2bb7066de98c5786115c0dc7edc75_68.png)

And then I'll bring this down here so we can look at both of them at the same time。



![](img/b1e2bb7066de98c5786115c0dc7edc75_70.png)

So let's describe what each of these pages are doing。 So we'll just say front end。Technical spec。

I think it's out of completing。And what' to say， pages。So here we have our dashboard。And。

We can see what kind of elements are on the page。 So we have a last study session。Study progress。

We have a。

![](img/b1e2bb7066de98c5786115c0dc7edc75_72.png)

Quick stats。We have a start studying button。Okay， so。This page contains the following components。

Its URL is going to be for slash dashboard， right， So we'll say this。 We also put it up here。

 as well。Like this so that we know what it is。Well need the following。AI endpoints。

 So we might say dashboard。I might able to do this in one go， but。You know。

 we might have last study session。Get last study session， gets。Dashboard， study progress。

Get quick stats。 We might be able to just make this all one end point， but it really depends。

 We might have to refactor that afterwards。Okay， and so we're just gonna describe what these components do。

 So last study session。Shows last activity used。Shows when last activity used。Summarizes。

Wrong versus correct from last activity。嗯。Has a link。To the group。So he says to view a group。

 but it really should link to the last session。 That's okay。 has a link to the， to the group。

So that should kind of indicate as to like， what should be in there for the API。

 We'll go to study progress。 So here we have。Total words。Total words studied。嗯。Out of。Entire vocab。

So， so like。Across all study sessions。So， total words studied。So we'll go down here。 So across all。

 all study sessions。Show the total words。Studed。Out of all possible。不呃。Words in our database。Right。

 so， and then we have a mastery link。 So， but that's just kinda being displayed there。

 So display a mastery progress。So we have that。 Then we have quick stats， which is。



![](img/b1e2bb7066de98c5786115c0dc7edc75_74.png)

Success rate。Success rate， E G 80%。Study sessions， total。Total amount of study sessions。4。嗯。

Total active groups。B G3，3， study study streaks。Stud streak。E G like four days， right。

 So we have this。You say， goes to。Study activities page。

And while we're really interested in the back end， you know， as we document this out。

 it's gonna help us figure out or as we talk front end， we figure out back end。

 So we know that we need to have these here for this。



![](img/b1e2bb7066de98c5786115c0dc7edc75_76.png)

And we would have to go back over to our other doc and bring those over。Right。

 so we'll go back over to our back end deck。And so we'll go ahead and grab these endpoints。

So to power this。Page， right， So we'll go ahead and grab this。Pste this in here， whoops。That did not。

Takeake it will copy。Paste。OkayOkay， so now we have。Those dashboard words， right？



![](img/b1e2bb7066de98c5786115c0dc7edc75_78.png)

Sorry， I thought my phone was ringing。 It's not。 So that's just the dashboard page。

 Let's go over to study activities。 Sty activities is pretty simple。



![](img/b1e2bb7066de98c5786115c0dc7edc75_80.png)

嗯。So I'm just going to save this and get the out of the way。 We just work on our front end here。

So now we need to talk about the。Study activities page。Which will be study activities。

So we have here。The typing tutor。 and so what we're looking at here is。

And we could describe these pages as well， this page。 So the purpose。

Of this page is to provide a summary of learning。And act。Has the default。Page， page。When。

 when a user visits。呃，外8OK。So we'll go down here and we'll say the purpose。Of this page is to show。

A series。A collection of。Study activities。嗯。With a thumbnail。And its name。Do you either lo。Or view。

The study activity。So here we have components。 so should。We'll need the following components。

What we call up here quick stats。So this page contains the following components。If we really want to。

 we can say。You know， components here like this。 instead， components。Purpose。And， you know。

 the way I wrote this before is never exactly always the same。 But the point is。

 is that as you work here， you start to find a structure that you can work with。These are。To say。

 needed。A P end points， you can kind of see that we're summarizing this as we go to make it a little bit easier。

 And this will be easier for the LM， I think as well， right？ And we're at for four indentations here。

 So we have purpose components。Needed API endpoints。And then。

iss that everything componentson need APIM points purpose， Yeah。

 so now we have those three as our structure。And that way。

 we can just copy this down below here as our template when we need the these。Okay。

 so's go here for a second。 put that down there like this。

 And so now we need to think about the components。 So we have a。Study activity。Card。嗯。

Represents or shows a thumbnail。Of the study activity。In the name。Of the study activity。

A launch button。Take。U to the launch page。The view page to view more information about past。

Study sessions。Or if therere。Or this study activity。Okay， so we have that， right。

 Then we have needed API end point。 So here， what we want is probably get。Study， so up to you。

 if you want to do underscore or hyphen， I kind of like hyphen。

 but we'll do underscore and just try to be consistent with this。 So we have to study get activity。

 So what do we need for this， We need pagination， probably。

I'm not saying that hasn't been auto completely。 I'm not here it's because I maybe because I don't have it open。

Which is fine。 I don't really need it， but。But， but that's the thing is you。

 sometimes you don't even notice when it's not providing any API toggle cascade with it。

So we have pagination。I don't really need pagination becauseuse I can't imagine there be that many study activities。

So really it's just get study activities and there's no extra instructions that I need to provide here。

Ca I think that one's very， very clear。

![](img/b1e2bb7066de98c5786115c0dc7edc75_82.png)

Let's go on to our next page。 So we actually have the actual view page as well。

 So we'll take a look here。

![](img/b1e2bb7066de98c5786115c0dc7edc75_84.png)

I said now we have study activities。嗯。And。I think one thing that we should probably define is like this is the API just to make it more clear as we have the actual web app and then the API。

 And I know they， they have their own apps。 but just to make it very clear， we'll do that。 Okay。

 we'll have to update our backend at some point here。 That's not that big of a deal。

We have a frontend specs pages。 we have dashboard， which is。This link here， I'm going to do this。

 that's just a little bit clear what's going on here。And we just did this one and it's。

 its link is this one。 But I I said right here， this one is study activities。

We should be try to be as consistent as we can here。

 and I'm going try to fix those as I work through this。 Notice again， we're just writing stuff。

 we haven't。Got a look at code yet。Because we shouldn't until we really get all of our specs in order。

 at least that's how I like to work。So we have our purpose。 We have our components needed API points。

 And yeah， this one's been changed over like this one。 So the next one we wantan to do is this study。

 study activity。Which is the individual page。 I'm gonna call it the show page。

 I kind of prefer calling it like that。 This one's gonna be study activities。

And this'll be an I D to indicate that there's a specific I D。 And so now we have our。A three here。

 right， purpose。This to show details of study activities in the past study sessions。 That's right。

 So we have a， what components do we have here， We have。



![](img/b1e2bb7066de98c5786115c0dc7edc75_86.png)

You。We have。Name of。Saivity description。 but guys have a description。

 We could have thumbnail study activity。Launch button。

We don't need a view button because we're already viewing it。 right。

 There's nothing to view after that。And we'll say。Study activities。APaaginated list or list。

 Paaginated list。

![](img/b1e2bb7066de98c5786115c0dc7edc75_88.png)

Right， and we might even want to be specific in terms of what is being displayed here。

 So if we look at this element here， this shows。

![](img/b1e2bb7066de98c5786115c0dc7edc75_90.png)

Cause it is a list。 We'll say I D。 This is being a little bit to we'll say ID D activity name。

Group name， start time。En time。Inferred by the last。By the last。Word review item。Submitted。Okay。

 and so we have that。 We have what else do we have here， We have review items。



![](img/b1e2bb7066de98c5786115c0dc7edc75_92.png)

![](img/b1e2bb7066de98c5786115c0dc7edc75_93.png)

Number of。Review items。So。

![](img/b1e2bb7066de98c5786115c0dc7edc75_95.png)

I think they'll probably be able to understand that。So we have that。 That's the component。

 So what do we need for this to work。 Well， we're gonna to need two endpoints。

 We're going need get that one， right， And we don't have to do this way。

 But I think like by doing this， it'll be study sessions that it'll， it'll make it a lot more clear。

 And so now we have our two endpoints that we need here。 So I'm gonna go ahead and copy these。

It's really trying to give me a stuff I don't want， but we'll go back over to here。To our back end。

And I'll just collapse this here。I'm going to paste in this section now。

And I'm gonna go modify this and call this API。 So， you know， we don't really need to call it API。

 But just so that the SDK doesn't get confused， right， or the cascade， sorry。

I'm going to go back over to here。And so， we have our。Daatase schema， which is good。 But we wanna。

 sorry， focus on a front end。 right， So now we have study activity。 Let's go take a look at launch。

 And yeah， it's， it's so boring and unfu。 but it does work。 There was a back button on this page。

 maybe。

![](img/b1e2bb7066de98c5786115c0dc7edc75_97.png)

So we might want back to activities， but I'm just going to ignore that for now for so we now have typing tutor。



![](img/b1e2bb7066de98c5786115c0dc7edc75_99.png)

I'm I type to the launch page。 So now we'll go here。And we'll say。Study。Activities。Launch page。

 and that's totally right。 That's what we want。It doesn't know where this stuff is getting from。

 Like we， I don't think we have the front end here here。 do we No， we don't。

 So it's literally just figuring this out， which is great。 So we go here and we'll see what we get。

 the participation to launch a study activity。 That's exactly right。 componentsons that we need。

 We need a。😊，Launch form。We need the name of study activity， so it knows。The launch form。

 which has a field。A select field for group。

![](img/b1e2bb7066de98c5786115c0dc7edc75_101.png)

Okay， launch。Now， button。Sorry， I just sneeze there。 So I just， that's why I paused。

 And so here you can see that what we'll need as our end point， will'll probably need post。And yeah。

 that's exactly right。 Now。 we could do launch。Or we could just say post study activities。

 That's kind of what I prefer。 That's more of like a rails way of syntax of doing it。嗯。

So that's what I would prefer。 You could you study activities， I D launch， I suppose。

I'm just trying to decide here。 Like， currently， the front end is rigged or like not rigged。

 but set up。For creating a study activity。 So I kind of prefer this syntax here。But， we do need。

We do need it to provide a group I D。Required。I mean， we don't have to write it here。

 We can write it over in the other one， but it does require the group I D and the。

 the study activity I D。 We， we definitely need those two things。So I'm just trying to see， there's。

Be。So after the form is submitted。嗯。A new tab opens。

With the study activity based on its URL provided in the database。Also， after submitting form。

The page will redirect to the study session。Show page。Okay， so this one's kinda defined。 Now。

 we're gonna copy this， and we're gonna go back into our back end just so I don't forget。

cause this one's a little bit different。As the other ones， because it requires group required。Prams。

And we'll say group I。And。Study activity I D。 Those are the two things that needs in order for this one to work。

As you see， lots of these are getss and not posts。But we will help specify that this as it goes。

We'll go back over to here。 So this one is now defined。 Let's go into words。

So it's pretty straightforward。So， we will go。Here and say 1，2，3。And I want to do words。Next。

And we'll copy in our purpose here。Show a collection of words with their。I mean。

 that' we don't need parts of speech。There we go。 All words in our database。

 And so there a component we have here is we just have a word list。 So it is。Paaginated wordless。

 cause that's what it is。 And we have， I don't need the I D。 We'll say。Japanese， I wrote kanji。

 but really Kanji is not。 That not exactly makes sense。 We don't need the part of speech。

 We're going to need correct and wrong。Correct， count。Rg count。

I'm going to go here and just say fields。Fields。So also columns， I suppose， columns。And。

Paagination with 100 per per item per page。Items per page。

The end point we're going to need here is the get API words。Okay。

 and that's all that's happening on this page。 If we go back over to this one。Well。

 some other things we should describe as like。Clicking。The Japanese word。Well。

Take us to the word show page。 So that is definitely something that we want there。

 So we'll have that。

![](img/b1e2bb7066de98c5786115c0dc7edc75_103.png)

Let's go back over to our backca and tech here。 We have get API words， right。

 We need to tell it that this is pageaginated with an item list of， of。

Thatca it definitely needs to know that， right， It would help if we were to fill out exactly what the J structure is。

But we can come back to this in just a moment。 We could fill it out as we go。

 but I would rather just kind of get all our pages。

 and then scan scan all of our APIs and see what we have here。So this one here is good for API words。

 So we're gonna move on to enact the actual word show page。

 So I'm gonna to go here and just say word show page word I D。😊，We'll bring in these here。



![](img/b1e2bb7066de98c5786115c0dc7edc75_105.png)

Let's take a look at what I put on here。I don't know if I took a screen shot of this page。

 I think I did， or maybe I didn't。

![](img/b1e2bb7066de98c5786115c0dc7edc75_107.png)

We' go check our reference files again。Do we have this one。We do。 It says we do。I don't。

 I don't remember seeing it， though。 Let's make sure that actually is there。 Oh， it is Okay， great。

 And so here， like we could do a lot more with it。 Like， we could have like grammar rules。

 all sorts of fun stuff。 But the word show page is。😊。



![](img/b1e2bb7066de98c5786115c0dc7edc75_109.png)

Let's see what says here。Clapps us up here。Show information about a specific word。



![](img/b1e2bb7066de98c5786115c0dc7edc75_111.png)

And so we'll look at what we have here。 We have for components。



![](img/b1e2bb7066de98c5786115c0dc7edc75_113.png)

嗯。Japanese， Ramaji， English。 We don't need parts of speech。Study statistics。So this will be correct。

 wrong。

![](img/b1e2bb7066de98c5786115c0dc7edc75_115.png)

I don't think we need total。 total is kind of useless here， word groups。Shown as a series。Of pills。

Uji tags。Wan group name is clicked。Take us to the show page， right。

 So that's all that's going on here。

![](img/b1e2bb7066de98c5786115c0dc7edc75_117.png)

Right， that's all we need。 So it's very simple。 We have study statistics， so that could be separate。



![](img/b1e2bb7066de98c5786115c0dc7edc75_119.png)

But I kind of feel like I would。It's acting a little bit funny here there we go。

 sometimes it does that。But yeah， that's not。 It doesn't need。

 It's really having a hard time get Let me in here for some reason。 Sometimes this happens。Come on。

We want get API API words。 That's all it needs to do， right， That's all it needs。

 And it can do those site statistics pretty easily there。 So that one is done。

 I'm pretty certain that we already have it there。 We do。 So that one is good。Continue on here。

Alright， so we have。Yeah， word show， word show page here。 need API Word。 we have that one。

 Let's go down to the next one。 So our next one is gonna be word groups。We group page。Tll you。

 the stuff is。Super fun。 It's pretty straightforward like。you get good at docs。 It's very uncit。

 But if you， if you can write your docs， you get really good stuff。 So this is going to。Xu。A list。

From database components。Paaginant gripless， that is correct。Columns， we have the group name。

 That's right， and。

![](img/b1e2bb7066de98c5786115c0dc7edc75_121.png)

Here。You just have a word count。Wet have anything else。O。We。And that's correct。

 That's where we wanted to go。We'll go here。Pretty straightforward， right。We'll go back here。

 We'll let it know that there is some pagination here。嗯。Same thing with words， yeah。

 we already have that there good。So now we'll go back。And we've defined our No。

 it doesn't need that other one。 well， actually。Yeah， yeah。 it doesn't need that other one。

 It's just， it doesn't know what it's talking about。 So we' got this one Now we got。

 that's exactly what we want。 That's the next one。 So we'll grab this。And we'll go here。The purpose。



![](img/b1e2bb7066de98c5786115c0dc7edc75_123.png)

About a specific group。Right， so here， and so。

![](img/b1e2bb7066de98c5786115c0dc7edc75_125.png)

Yep， that's what we have。 So we have actually three things here。 We have group statistics。

 words and groups， study sessions。So you have。Well， we do have the group name， that's true。

Then we have group statistics。This is going give us nope， that's nope， nope， you're doing too much。

Sometimes you gotta like tell it not what to do。 Total word count。 That's right。 You know。

 we could bring in other ones， but I， I don't really want those。

 I just want total word count to be honest。 And then here we want words in group。



![](img/b1e2bb7066de98c5786115c0dc7edc75_127.png)

So， this is。对。Paaginated。List of words。Oh， my goodness， should。Use the same。嗯。Columns。Same component。

As the word index page， there we go。 So that's what I want。

I don't know why it's crossing all that stuff out，'s I didn't ask you to do any of that。

But you can see like here now it's just getting really too aggressive。

 And this all kind of happens eventually。 I don't know what it thinks it's doing。



![](img/b1e2bb7066de98c5786115c0dc7edc75_129.png)

![](img/b1e2bb7066de98c5786115c0dc7edc75_130.png)

But it's getting a little bit annoying now， But that's okay。 So we got words and groups。

And then we have study sessions。That's right。And， I mean， not study activities， but study sessions。

Okay， so we haven't really defined yet。 So here we're gonna have a few。 We have our。We do have that。

 and we do have that， but we're missing one other one。Okay， so the name and。嗯。Group stats。Okay。

 so these are， our three end points that we need。 We go back over to here。

Im to click over to this one。And in here， we have our groups。We have most of these here。

 We just don't have。 We'll take this one out。 We just didn't have study sessions， right。

 So that's the one that we were missing。Right， if we want to make this easier。

 we could obviously like put spaces in between it， but I don't want to do that。

And so that one is now done。This is word groups。Yeah， we're inside of a group。

 Now we go over to our sessions。 So now we actually have study sessions。 So we go here。

And so actually an index is fine。 That's actually normally what I call them。No up here。

 We didn't call that。 We called this one dashboard。 We call this ones study activities index。

 Like we call that index。 That's actually normally how I would call these。 I'd call it index。

 That's like a Ruby convention。 So I think it's kind of picking that up。 So we have words index。And。

Word groups index。Group show page is fine。So， yeah， we just fix some of that consistency there。

 So go ahead and copy this one here。What is this purpose here？That's right。

And we'll say components here。That is correct。That is right。

 But I'm gonna be very specific in what I want。 So I want I D。Activity name。Group name。Start time。



![](img/b1e2bb7066de98c5786115c0dc7edc75_132.png)

End time， That's right。Review items， number， number of review items。 Yeah， it already has that。

 There we go。 So， and then when we go here。Clicking the studyudy session ID。

Will take us to that page。Actually didn't fill this in。 But， I mean， technically。

 that's what that is the end point。 So that's correct。Yes， that's pretty good。

 So we'll go ahead and save this one。 We'll go back over to here。

And I'm going to open this here like this one here， study sessions。It's true。 will' have this。

 And we are gonna have this one here in a second。 I'll just leave it in there for now。

 We'll go back over to here。 And now what I'm gonna do is document the next one。

 So we're gonna go here and say。Study session show page， which is exactly correct。

 We're going to go ahead and grab these here， bring this on down。

And let's click into this page and see what it looks like。This looks very similar to。Oh， no。

 that is a word group。There we go。 Okay， so this one has。嗯。That's right。

I know sometimes it's very obvious the description， but， you know。

 we should put that in there and then we work it later。 So we have study session details。



![](img/b1e2bb7066de98c5786115c0dc7edc75_134.png)

This will have。If we don't need the I， I don't really care about the I。



![](img/b1e2bb7066de98c5786115c0dc7edc75_136.png)

But we will want。 is there anything else in here， just those。 Y， we'll have。The activity name。

The group name， that's right。The start time， the end time， I don't even have the end time。

 number of review items is perfect。And then the other thing that we need is a component for words。

Reviewed。And that's a list of pageaginny words。 exactlyact the same thing， right。

 should be the same component as the other page， right， And， you know。

 what we could do is we could even give this a unique like like shared or global components。

 and then it would make it even more clear what components are being shared。

 and it would be get it'll get less confused。 but we need an API here。We do need that。

 I might just call it words。So it's less confusing。And then we need that one。 There we go。

We should also have， like。Well， we don't have a name of the study session。

 so that doesn't really matter， does it？Okay。But some of the things we're missing are these back buttons。

 So we might regret not doing that， but usually should document everything。 Then our last page here。

 So we didn't get this one。 We'll grab this。Back over to here。Right。

And so now we need to do the settings page。 That's our last page。We already did study sessions。

 we don't need to do that again。 See now doesn't know what to do。So， say settings。Settings page。

 that's right， and。Nope， the purpose of this page is to make configurations。To， to the。Yeah。

 study portal shirt。 And so we have。Theme selection。E G light， dark system。 That's exactly right。嗯。

I mean， that would be good if we actually have different target languages。

That might not be a bad idea， but for now， I'm not going to do that if you want to do it。

 you absolutely can。 But the other 1 I want is like reset history。So this will， there's no sign out。

Yeah， this will delete。All study sessions。And we we review items。 That's all it will do， right， so。嗯。

We have that。We could also have a button here。 I didn't do this。 And the other one。

 I kind of wanted it， but this would be like。Lo。Seed data。Reset history button like。Full reload。

 or just like。Reload C data。This will。Drop all tables。And recreate， so like。放。Full reset。But。Okay。

 because sometimes we'll have like new stuff and we might wantan to clear it out of there。

 The other thing that we could do is just like have it where it only inserts new words。嗯。

It would just like load。Seed data。But this one might be a little bit harder to implement because we'd have to see like what art exists first before inserting it into there。

So we have to say， like， what is our needed APIs here？Yeah， we just have those two endpoints。

So go ahead and copy。 Now we can get rid of this stuff on the bottom。And these are all of our pages。

So I'll go back over to here。

![](img/b1e2bb7066de98c5786115c0dc7edc75_138.png)

And we've just defined all of our endpoints。 These are all of them， right。

 The only one that's not on here。Because。I hate that he keeps doing that。

 The only one that's not on here is the review button。

 because that is an external one that we see here， so。The one that is missing here would be。Post API。

Study sessions。嗯。I mean， technically， it would be a very specific word that we're studying on。

 I just can't remember what I did before， but it could be like words。呃。Word Id。Review。Right， so this。

Yeah， that's right。 Parameter， correct。 That's correct。 So that's what we want。

 So whether it's correct or not， and I could say here， like study sessions。

 I D to make it more clear。 But I think it's pretty clear that that's what that is here。

So now we have our front end completely defined。The only thing we don't have here is the shared components。

but that's kind of a problem for when we work on the front end。But right now。

 we're just focused on the back end。 And so we have our schema defined our technical requirements。



![](img/b1e2bb7066de98c5786115c0dc7edc75_140.png)

And so this is a point where I would want to commit my code。

 by code because we're gonna use cascade to try to。

Further enricher API endpoint so that we get exactly what we want， because I need to see。

What our endpoints can look like。 And once we know exactly what we want our endpoints to look like and we know that we。

 we have our schema and it's in good place， then we can hold it accountable to say like， hey。

 make sure that you keep doing what you're supposed to be doing here。

 But what I'm going to do is I'm going to open up。 get smart。 You can use whatever you want。



![](img/b1e2bb7066de98c5786115c0dc7edc75_142.png)

![](img/b1e2bb7066de98c5786115c0dc7edc75_143.png)

But I use not get smart， but smart get。And if you're on a Mac it's called get X。

 but this one runs on everything。 But we do have over here the way to commit the reos over here。

 But I opened up this subfold here。 but I personally like to review my code an external editor or like get thing here because I feel like it's more clear。

 and I'm paying attention more closely to what's being committed where when I'm in V S code。

 I can't tell what's going on。 So I need to add this repository here。

 And this one can't really tell what's going on here。 So'm gonna add one。 I'm gonna select it。

 And I'm gonna go over to sites。 This is a free thing。 Smart good。

 I might have showed it in the free gen essentials。 I'm not sure。 But I gonna to go into here。

 And this is the one that I want to open。

![](img/b1e2bb7066de98c5786115c0dc7edc75_145.png)

![](img/b1e2bb7066de98c5786115c0dc7edc75_146.png)

No， no， no， that's not the  one I want to open。 The  one I want to open is in Omen King here。

 It's this one right here。Okay， so Im can open this one and say， okay。



![](img/b1e2bb7066de98c5786115c0dc7edc75_148.png)

And so now I have this repo。 So this is literally how I review code or my own or anybody else's。

 I go in here and I review all the files。

![](img/b1e2bb7066de98c5786115c0dc7edc75_150.png)

So don't like how this thing's really big。So those are a bunch of files。

 But the point is we only have two files we really need to review。 It's just this one and that one。

 There's a way to change this layout if we don't like it。嗯。I don't know。 when you first install it。

 it gives you some options。 But the point is that we're like looking at this。

 We have side by side compact。 Yeah， yeah。So we have this file in that file and a bunch of files here。

嗯。OPA comps， this is。Something for later。 I do wan to keep that， but。This is for later。

 I think I'm going to keep this。 I'm gonna keep this for now， whoops。

This is something that's supposed to happen in the future。

 But I I have things that are kind of out of order here。 So I'm gonna go ahead and just say un stage。

 Oh no， I want to stage these changes first。Sage changes。And so， now。Which is stage just up below。

I again， I use giex。 So this layouts a little bit different。 But I think down below here。

 this is what's being committed。 So I'm gonna say here， OPA A mega service。

 This is under in a future video that I've already recorded。

 I'm just doing things a little bit out of order as per usual。

 We'll confirm it that everything's fine there。 And so then I'm gonna do is commit this stuff。As。

Are technical specs。 So we'll stage that。 Now it's down below there。

 And I'll say technical specs for front end and back end。And image references。Okay。

 so now we have that， right， I'm going to go ahead and commit that。



![](img/b1e2bb7066de98c5786115c0dc7edc75_152.png)

That's all good。And if we want to go back there， we can always review those files。

 I think I'd have to do something to change the layout here a little bit。

 It's a little bit different from Gex。 And I'm not 100% happy with it。

 but I will figure that out at some point here。 but it's still better than this thing here。

 I don't like reviewing stuff in here。 And also when I use Winsurf。

 you notice I constantly open up just the subfolder here。

 just because we're working with many projects。 And I don't want to reach out to those other files。

 And but normally like if we were doing this for real。

 you might want to have all these in separate repoos right。

 And so this would actually be what the repo would contain for our la portal。 again。

 I'm trying to keep everything in a single repo。 just for our convenience。

 That's why I'm opening this willy won away。 Okay But now that we have。



![](img/b1e2bb7066de98c5786115c0dc7edc75_154.png)

![](img/b1e2bb7066de98c5786115c0dc7edc75_155.png)

This done。 I'm going stop the video here because we've。

 we've now completed our tech our draft text specs， and then we'll move on to the next step， okay。



![](img/b1e2bb7066de98c5786115c0dc7edc75_157.png)