# UCLA《计算统计学｜Stats 102A - Computational Statistics with R 2024 Summer》中英字幕 p17 [17]Stats 102A - 2024 Summer - Video 17 - Basic Webscraping in R with rvest.zh_e [BV1jizNBrEm2_p17]

![](img/196d94282b44318cec5f01262cabb3b0_0.png)

Okay， let me introduce web scraping with our vest。So package RV is kind of a play on the word of harvesting and it's kind of all about scraping data from the web and you can read more about it and especially one of the important articles will be the article on selector gadget。

 so I have that open here and you can follow the instructions on installing selector gadget and using it。



![](img/196d94282b44318cec5f01262cabb3b0_2.png)

![](img/196d94282b44318cec5f01262cabb3b0_3.png)

Okay， now a couple things， one thing to note is our is good for fairly static web pages。

With well definedfined HTML tags， but it doesn't really work well for sites that are generated via JavaScript or sites that have like infinite scroll or things like that。

 also is not going to work well if you have to be logged in to view the content。

 so sites like Facebook or X not going to work well there。Okay。

 just a very basic and brief understanding of HTML and CSS can help you understand how RV works in that a lot of web pagess are mostly written up in HTML and formatting as applied by using these different tags and to keep a page's format consistent。

 the designer will use these things called CSS classes and specify how each of those classes should be displayed okay。

So for example， a very kind of simplified version of what you might see on a page is you're going to see these different tags。

 so UL is like unordered list and list item is this and each of these things have these different kind of classes like this is a flat list of buttons and。

You know， you have this thing that says class comments， class share button， class save button。

 class hide button and。They kind of correspond to the different buttons or the different links that you can click here okay。

And then if you want to select them， you can specify which class or things like that a lot of these you also have these links like share and save and stuff and links are done by using anchor tags and a tag and then the。

The HTML reference， and I'm certain that the reference。

 the HF is kind of like the hyperlink reference that it should go to。



![](img/196d94282b44318cec5f01262cabb3b0_5.png)

Okay。And so。This is how we're going to specify which bits of information that we want to get from the page。

 Okay， so selector gadget is this little。Applet that you installed to your web browser and it looks at the CSS tags。

And it selects all the tags on the web page。That has a specific tab and the way it works is you go to the site and you click the tag that you want to capture and then the gadget highlights everything that it's going to capture。



![](img/196d94282b44318cec5f01262cabb3b0_7.png)

So to install selector gadget， first you have to kind of bring up your browser bookmarks bar。

 so in Chrome or Edge or a lot of things it's going to be command shift B as in bookmarks or control shift B and then basically you'll take this link for selector gadget and you'll just drag it up to your。

Browser browser bookmark here。 Okay， and I've already installed it。

 so I'm going to just go ahead and delete that。 Al right， so I'm going to go to。



![](img/196d94282b44318cec5f01262cabb3b0_9.png)

![](img/196d94282b44318cec5f01262cabb3b0_10.png)

The web page old。 reddit。com and it just kind of has some content up on there this is what I see right now。

And what I'm going to do is I'm going to click selector gadget。Okay， all right。

 so now now it appears， the selector gadget appears here and then as I go over the web page。

As I hover you'll see these all these different kind of orange boxes。

 so let's say I want to select just kind of like the headlines of each of these things I'm going to just say I'm going to click this and it highlights a whole bunch of stuff in yellow so I don't actually want all of these things I don't want this or this I'm going to。

Uncheck some of the things I don't want， so I'm going to like say I don't want that。

 so I click that and now it only highlights one thing， so I do want to get this。



![](img/196d94282b44318cec5f01262cabb3b0_12.png)

Let's say I don't want this。

![](img/196d94282b44318cec5f01262cabb3b0_14.png)

I do want this。So it's like trying to figure out。What set， So maybe。嗯。Yeah， okay。

 so sometimes as you're clicking， sometimes you just have to kind of start over to try to get it right。

 so let's see。I want that， but I don't want。

![](img/196d94282b44318cec5f01262cabb3b0_16.png)

This， this looks better。 This is the title tag， I think I want to avoid。



![](img/196d94282b44318cec5f01262cabb3b0_18.png)

The ads， though。So when I clicked that， okay。Seft dot title， let's see if we can get that in there。

And that in there。

![](img/196d94282b44318cec5f01262cabb3b0_20.png)

Okay， so now it's。嗯。

![](img/196d94282b44318cec5f01262cabb3b0_22.png)

Yeah， it seems like。It's getting most of things， maybe I don't want that。



![](img/196d94282b44318cec5f01262cabb3b0_24.png)

All right， I'm having trouble figuring out the exact。



![](img/196d94282b44318cec5f01262cabb3b0_26.png)

![](img/196d94282b44318cec5f01262cabb3b0_27.png)

Okay， so maybe I'll just use title。What if I undo that， no。



![](img/196d94282b44318cec5f01262cabb3b0_29.png)

Okay， well， the path that I'm currently getting when I do this。



![](img/196d94282b44318cec5f01262cabb3b0_31.png)

It's just going to be title， so I can try selecting that， I think。



![](img/196d94282b44318cec5f01262cabb3b0_33.png)

Earlier I did it， oh here I was going for comments， so here let me。



![](img/196d94282b44318cec5f01262cabb3b0_35.png)

Like if I want to get the number of comments， I can click this。I don't want any of that other stuff。

 okay， so I can do dot comments and it selects all of the things with comments on here。



![](img/196d94282b44318cec5f01262cabb3b0_37.png)

![](img/196d94282b44318cec5f01262cabb3b0_38.png)

And then so here I can。

![](img/196d94282b44318cec5f01262cabb3b0_40.png)

Read in and I can select the comment nodes， HTML nodes。

 and then in there I put do comments and quotes there， and then I'm going to extract out the text。



![](img/196d94282b44318cec5f01262cabb3b0_42.png)

And。And so this kind of corresponds， it the numbers have updated a little bit， but 10，0241， 5097。



![](img/196d94282b44318cec5f01262cabb3b0_44.png)

And here we have 10，233，5096 and so on and so forth。

 so these are kind of the the comments that that go there Okay。

 so it extracts out the text there and then from there you can then。Apply， say， like a。

Regular expression， which I haven't taught you yet。

 but with regular expressions you can say anything that's digits。

 so here we're going to extract out the digits and we just get the numbers and we convert them to numbers and now。

Now， we can。Work with them， okay？Okay， hard for RV yet it doesn't work with the JavaScript pages。



![](img/196d94282b44318cec5f01262cabb3b0_46.png)

If you use title the node， I guess dot title dot may dash blank。

 then you're able to select basically the titles of these things， let me see if I'm able to。



![](img/196d94282b44318cec5f01262cabb3b0_48.png)

![](img/196d94282b44318cec5f01262cabb3b0_49.png)

Get it。don't want this。 So we got thatt title。Maybe必。Okay， there we go。 That's what we want。 Okay。

 dot title dot May blank， and this will get。

![](img/196d94282b44318cec5f01262cabb3b0_51.png)

Get the。The the titles from each of the things。 and then so here I've got。You know。From。Our vest。

 we read the HTML from the website and then we select the nodes。



![](img/196d94282b44318cec5f01262cabb3b0_53.png)

With that。UmWith the tag right here， Okay， so you just kind of highlight the tags here， you copy it。



![](img/196d94282b44318cec5f01262cabb3b0_55.png)

And then you put it into our vest as far as which tags you want。

 and then you can say extract out the text and then we get。You know。

 who do you wish would run for president of the US all right， so that's right up there？



![](img/196d94282b44318cec5f01262cabb3b0_57.png)

AITA for slapping a teenager that shows up there， okay？



![](img/196d94282b44318cec5f01262cabb3b0_59.png)

So so that's， you know， how you go about selecting。



![](img/196d94282b44318cec5f01262cabb3b0_61.png)

Tags okay there are other options as far as web scraping goes， they are a little bit more involved。

 but you can kind of look it up and there's say our selenium and then if you use Python。

 there's scrappi and beautiful soup and then Selenium also works in Python as well。



![](img/196d94282b44318cec5f01262cabb3b0_63.png)

Okay， ourV also supports automated。

![](img/196d94282b44318cec5f01262cabb3b0_65.png)

Browsing and scraping and so what you do is you basically begin a browsing session。



![](img/196d94282b44318cec5f01262cabb3b0_67.png)

And you tell that browsing session to go visit a particular URL。

And you tell Arvis to scrape the content of that page， store it somewhere。And then。

And then once you get all that content， then you tell it to go to a new URL。

 you tell the session to go to a new URL， and then you scrape the content of that thing。

 you have it go to another URL， script the content， and so on and so forth。

 okay and you just kind of repeat this until you get all the content that you want。



![](img/196d94282b44318cec5f01262cabb3b0_69.png)

Now， one thing you want to keep in mind is that most websites implement some sort of protection against like DDoOS attacks。

 which you know happens when you know all of these bots kind of just produce a ton of requests and it can't。

And the requests can't get through and so so you want to avoid。

You want to avoid producing too many requests okay so if you produce too many requests and the request is basically just anytime you visit a new webp page or you ask for you know some content there。

 if you do that too many times then the server might detect this and then it might rate limit you and it might say like come back in an hour or something like you can't visit the website road now if you do it too many times then you might even get fully banned or blocked so one thing you want to do is you want to use this package called politeite okay and polite you know intentionally slows down your web scraping and that way you avoid problems because in one of your upcoming homeworks。

I'm going to tell you to go visit a website and scrape a whole bunch of stuff and you don't want to generate too many requests。

 okay。

![](img/196d94282b44318cec5f01262cabb3b0_71.png)

And so the way it works is you load up library Polite and then you create a polite session by callingBO。

 okay， you callBO， you put in the URL that you want to go to and there。

 and then you store that as kind of your current session name。

And then when you want to kind of scrape the content， you callSpe， you give it the session name。

And then you will。Do select the content the HTML okay。

 I use a pipe so I can say session name piped into scrape， which is you know equivalent all right。

 and then when you want to visit a new page you call nod okay and nod is going to give you you request the new URL that you want to go to。

Okay， and polite is going to kind of make sure that。

Every time it wants to request a new page with nod， it does it kind of within the。You know。

 a reasonable timeframe so it doesn't overrun the server and get angry。Okay。

 let me run a little demo now。So here I have this R demo script and this is also uploaded to Canvas and let me go ahead and and run through these lines of codes。

 I'm going to load up the library Plight you might have to install R and Plight if you haven't done so already。

 we'll load up library R， I'm also going to load up library stringer which is used for regular expressions。

So first I'm going to start by going to this IMDB page for the Lego movie okay。

 so this is the Lego movie webp page and we will just start off by asking ourV to read the HTML of this thing。

Okay， and it goes to the website， it reads it in， and that's going to be stored in as Lego movie。

And then so what I want to do is from the Lego movie， I want to select the rating。

 so on the Lego movie page。I want to select this IMDB rating， let me see if I can。

Get the selector gadget， So using selector gadget， I'm going to hover over the rating。And basically。

 this is the tag that I want dot C X H HRR capital I， Okay， so this is kind of generated by。

Javascript or something， so it's not like a really， it's a bit of a nonsense tag。

 but it's enough to kind of identify this number。So I'm going to say take the Lego movie。

 this is the pipe and basically it just says take the Lego movie and from that。

Ask for the HTML nodes this All right， so if I just run this part。

You can see it extracts those nodes from。The web page， okay？Here， when you say I just want the text。

 it's going to be give you just the text that's in between。The start opening and closing tag。

 so this has an opening and closing span tag。And and I can just get the text in between there and it gets out the 7。

7 here it comes in as text， so it's character data and here if I say I want it as numeric。

It'll convert that into numbers， so now we have numbers and so I can just run that。

And so rating it gives me some。 of so for whatever reason on the web page。

 that this tag is duplicated， but that's fine，All right， there's other stuff we can do。

 let's say I want to get members of the cast， members of the cast。

 so we have Chris Pratt will Farrell， Elizabeth Bank will earn net so here。



![](img/196d94282b44318cec5f01262cabb3b0_73.png)

I'm going to use selector gadget once again。I'm going to hover over the things I want。

 I want to select the names here。

![](img/196d94282b44318cec5f01262cabb3b0_75.png)

And that actually looks correct just by highlighting that whoops。It seems like it's selected。



![](img/196d94282b44318cec5f01262cabb3b0_77.png)

The cast members and nothing else。So basically the green is going to be what's what you clicked and it's going to also select anything else that's in yellow here。

 So this is the tag we want dot GCQ K E H。Okay， and we will use that， and so I do Lego movies。

 HTML nodes。gcq K Eh。All and it selects those tags。And these are all of the。嗯。嗯。

Basically anchor tags that it has and here I just want the HTML text。

 so I'm going to just get the text that's within there and we get Chris Pratt Will Ferrell。

 Elizabeth Banks basically the names of the cast members there so that's great so we will store that in as cast and so I have that stored there。

You can extract longer things so here。Is like the movie reviews， okay？And so you， again。

 I use select your gadget。I'm going to hover over。 this is going to be。The thing that I want。

 I really just want this one thing so I'm going to and selecting a bunch of other stuff that I don't want。

 so I'm going to just click that and and so now I just have one thing。tJCjwUR IPCHt， okay？嗯。Okay。

 well here I got a different。Different tag when I did it。



![](img/196d94282b44318cec5f01262cabb3b0_79.png)

But I can run this and this is。This is the review this is。I think it。Let me see if I get。Lego movie。

 and we're going to select HTML。

![](img/196d94282b44318cec5f01262cabb3b0_81.png)

Let me try putting in the tag that we just got there。And then let me just see what this gets， okay。

 HTML text。So。This also。Pulls the same thing。Here it's a slightly different review。

 let me refresh the page and see if。Okay， okay yeah so here we go。

 to be honest when I heard of the LGgo movie， I thought it to be a ridiculous idea and there we go to be honest when I first heard of the Lego movie。

 I thought it to be a ridiculous idea and so this is how you can extract it and so yeah sometimes when you use selector gadget。

It will give you different tags that and these different tags might both be able to give you the same kind of answer here。

 okay。So that's fine， okay。Let's say we want to visit。Chris Prettz's IMDB webp page， so I click that。

Okay， and so this is his。Web address okay， and so I can say， hey。

 we're going to go to his web address and I'm going to read the HTML there。



![](img/196d94282b44318cec5f01262cabb3b0_83.png)

And then let's say I want to get basically。The the projects that he's working on， okay， so again。

 I would use selector gadget。And I'm going to hover over these projects。

And these are this is the tag I want IPC metadata list summary item T。



![](img/196d94282b44318cec5f01262cabb3b0_85.png)

And I put that in here。And so from Chris Pratt's page。We'll load that in。

And then the projects that he's working on。Okay， we can see these are the project he's working on。

 some of them are upcoming， so if I expand that， I guess it also selected。Refresh this。Okay。

 for whatever reason my browser is not expanding this or shrinking that it's not just not responding but but we can see。

 you know we have the Garfield movie， Guardians of the Galaxy Volume 3。

 the Super Mariio Brothers movie， Guardians of the Galaxy Holi special and they kind of all appear on here as well okay。



![](img/196d94282b44318cec5f01262cabb3b0_87.png)

![](img/196d94282b44318cec5f01262cabb3b0_88.png)

So。So what I want to do now is I want to run a session that's going to visit multiple pages。

And the idea here is I want to start on the LeGgo movie page。And then。

And then I want to visit Chris Prat's page and download。The projects he's working on。

 then I want to go to Will Farrell's page。And download the projects that Will Ferrell's working on okay。

 and so on and so forth and do that for you several of these cast members here， okay？

So here to do this， I'm going to start a session， all right， so my session。

 I'm going to just call session。And I start my session by bowing to the server and I put in the URL that I want to start off at。

 which will just be the IMDB page Okay， so I click bow All right I run that and so now I'm。

I'm running a session here。And then from that session， we get the content okay。

 we we're going to store the page content I'm going to run session scrape。

And then we're going to get the the HTML content。 So I do that。 This is going to be my page content。

 This is basically the result， same thing as doing like read HTML。

 but when you're doing a session you call scrape， So basically read HTML。

Sttores the page content to whatever I have here and basically scraped does the same thing。

And then so from page content， remember what I did earlier is I got the cast names by using the HTML nodes。

 HTML text here。Okay， so the HTML nodes， so I can get those same。Tags。Okay。

 but this time I already have the so here if I do the page content and I run HTMLm nodes and the text。

 I will get the cast names okay， but what I want is I want the web address。Of their page， okay。

 this is。The web address。And it's stored under HR， and so you can extract out the web address and that's going to be under HTML attribute。

 So not just not the text， we want the HTML attribute， which attribute do we want。

 We want the attribute for H ref。Okay so I'm going to get those actor URLs and so these URLs name slash nm0695435 are now stored under actor URLs。

 okay so name Nm0694535 right there and then the next one， so on and so forth。



![](img/196d94282b44318cec5f01262cabb3b0_90.png)

For the cast， we got the cast member names and what I'm going to do is I want to associate。

Each cast member's name。With their URL， so I'm going to use ours， I'm going to take CA。

And I'm going to assign it to the。As the names of the URL， so the content will be the URL。

 but the names associated with each URL will be that so when I do this now I have a named vector where the content is the URL。



![](img/196d94282b44318cec5f01262cabb3b0_92.png)

And then the name of that URL is Chris Pratt， so then I can do actor。Underscore URLs， score bracket。

 and then I can type in Chris Pratt。And I get his web address， or I can type in。Will Ferll。

And I get his address， okay？So that that works。 Okay， and then now I can tell our session to go to。

Chris Pratts page okay， I can say session nod， what's the path that we want you to go to。

 we want you to go to this URL， so we're going to do actor URLs。

 Chris Pratt and scrap that content so that will give us Chris。Chris's page content right over here。

And then。And then again we might want to get hit the projects that he's working on。

 so from Chris Chris page content we'll extract out the that you are。

What do you call it selector gadget tag that we had earlier？And that gives us that okay。

 so what I want to do is I want to do this for multiple actors。

 so I'm going to start off by creating an empty list where I'm going to store my results。



![](img/196d94282b44318cec5f01262cabb3b0_94.png)

And I'm going to just do this for the first four actors。 Okay， so remember cast。

I have all of these things and we're just going to do the first four， so Chris Pratt Will Ferrell。

 Elizabeth， thanks Willart。And we're going to say。We're going to get each actor's page content。

 so we're going to start our session， tell it to go to the URL with that actor name。

 so first it'll do for Chris Prett then it' will do it for Will Ferrell and Elizabeth Bank。

Bas and remember actor URLs。Has all of this stuff， okay。

 we're going to scrape that content once we get that scraped content from the actor page content。

We will extract out the projects that they're working on。

 and we'll just get the first 10 of those things。I also said， hey， I want to get the years。

Asssoiate with that project。 and we will do that。 All right， and for each of these things。

 we're going to store it into。Cast movies into double square bracket actor name。

And then I'm going to so it's going to be a list of lists。

 so each actor name will have a list with movies in years。And then also their name。

 so we're going to just take repeat the actor name。You know。

 however many times and then throw that in there， so this is going to be the the loop that I run and because it's polite it'll do it a little bit slowly。

But this will prevent me from。Getting in trouble with the。With the website。

 so we'll let it run and it takes a little bit because it's doing it for four different pages。呃。

It will get there， okay， so now it's done and so now cast movies。Is kind of a is a big list right。

 so it is a list here。 Let me just do structure。

![](img/196d94282b44318cec5f01262cabb3b0_96.png)

Of cast movies。And so it's a list of four， the top level is the actor name Chris Pratt， Will Ferrell。

 Elizabeth Banks Willarnet， and each of those。嗯。Each of those actors is a list。

Each of those lists has three elements， movies， years name， movies yearss name， okay。

 so then what I want to do now to kind of combine it。

Is I'm going to create a big list of movies ears and names。

And then so for basically for each thing in cast movies， we will get。

I'm going to take the current movies， this is the inefficient code。

 but I'm just going to duplicate it and take cast movies you know that first one extract out the movies and store it in there and so here we'll get now。

A list of just movies。Years and names， okay， each one length 40。

 and then I can make a data frame out of it。And so there we go。Louiseier's name。Okay， and that is it。

For the R demo and hopefully that will be a handy guide as you try doing some web scraping yourself in homework3。

