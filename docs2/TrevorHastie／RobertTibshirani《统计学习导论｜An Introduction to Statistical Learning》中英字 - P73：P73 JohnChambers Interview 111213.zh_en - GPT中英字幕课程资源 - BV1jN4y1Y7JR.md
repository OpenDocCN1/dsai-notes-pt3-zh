# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P73：P73 JohnChambers Interview 111213.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

。Well we have a guest here today Dr。 John Chambers John was the invent of the S language which is the language that we use in R John was also my department head the AT&T Bell Labs when I worked there in the 80s and 90s so John welcome and great to be here thank you and please tell us about this and how it became more it's an interesting story actually it's an interesting combination of ideas and the context for the ideas and outside events that we had no control over。

It has a very specific birth date actually， which is the 5th of May 1976。

that was a day on which five of us at Bell Abbs and Bur Hill sat down in the conference room and started to talk about what we might do to create an interactive system。

 as we called it at that time。But it's very important as part of the story that that was far from the beginning of statistical computingut research at Bell Labs。

 my own involvement had gone on for more than a decade before that。And as another example。

 about a year before that， we hired a really bright young guy named Rick Beckcker。And Rick and I。

 the first thing that we worked on together was a system of software for statistical graphics for scatter plots and other kinds of things like that called GZ。

And you have probably never heard of GZ， but you've used it because the base graphics inR is essentially designed on the way that we structured GZ never knew that。

And in addition， we had lots of other software， numerical software， random re generation。

 data management， all that kind of stuff。The catch was that all of it was in the form of4n coable subroutines。

 So in order to use it， people had to construct4n main program job control and all that kind of stuff。

 And the result was that there was a delay and lots of people were involved and by the time you got the results back。

 you'd kind of forgotten what the idea was in the first place。

 So our goal was to provide an interactive system where the people actually doing the statistical analysis or doing the research could sit down themselves and express what they wanted in some fairly natural way and get the results back right away。

But at the same time， and this is also important。We wanted them to still have access to the best computational methods that existed。

 regardless of where they came from or who had written them and including things that would be developed later on。

 so that was the basic philosophy and when you think about it that's not a bad description of what we try to do nowadays with R。

So in the first next few months， we did put together an initial version of the system and started to have people use it。

In the statistics research area and other colleagues at Murray Hill。

That takes us to sort of late in the 1970s around 1978 or so。And meanwhile。

 the next event on the floor above us at Murray Hill。

 there were some guys in computer science research who were busy creating a new kind of operating system。

Which eventually was called UniX。And in particular， around 1978 or so。

 a new version of UniX was developed that was based on the C programming language。

And was portable amongst different computers。In particular， it was portable to 32 bit machines。

 which meant that it was now a candidate for doing scientific computing before it been on a 16 bit machine。

Rick and I immediately realized that this was the way that we were going to get a portable version of S。

 something that we had been worrying about for a while。

 so in the late '70s we rewrote us to use the sea language and the UniX operating system。

That was the first version that was licensed for people outside of AT&TDs。And there too。

 we piggyback off UniX because the UniIX folks had arranged with AT&T to license their software。

 their operating system， and in particular to license it with a very favorable rate to universities。

 basically free universities， just for the cost of copying the tape。

We managed to get the same arrangement for us and so at that point we started to have outside users。

 mainly universities where there was a lot of interest in statistics and computing and things like that Carnegie Mellon。

 Toronto， Berkeley and John was that S very similar to what we use today not so similar there were two books that Rick and I wrote that described that if you looked at it and just looked at what somebody written down。

 say to do a linear regression， it would look similar。

 but as soon as you started to do anything nontrivial it was very different。And in fact。

 that's sort of the next part of the story。So then some other events started to take place。

 one was that in 1981 I left statistics for a few years and went to head what was called the Adv software department。

Their job was primarily to produce。Computing tools for the company。

 particularly for what would nowadays be called analytics。And so while I was there。

 I started to look at some other ideas in programming languages。

And it started to write a new language， a different language called a quantitative programming environment。

 which originally wasn't going to have any connection directly to us at all。

But while all that was happening on a much， much larger scale， AT&T， the old Bell system。

 agreed to be split up to divest itself of all of the local telephone companies in response to an antitrust suit from the federal government。

This took place between 1981 and 1983， as part of that。

 Bell Ebbbs spun off a fair fraction of itself， including research to a new company called Belco。

And as part of the rearrangements and reorganizations and everything that went on at that time。

 I came back to statistics as head of the statistics and Data analysis Research Department。

And Rick and I got back together， we decided to merge the sort of stuff I'd been working on with what he'd been doing to improve as itself and to create。

A new version， what we call the new S language。That describes。

That's probably the first one I got to know it probably is there were a few universities who got into the old S。

 but this is when S began to really sort of take off with universities。And research labs。

 and to some extent， third party resellers。So done。And then of course， as you very well know。

 we went on to also produce the statistical models in S effort that you and I edited。

And along with that came the first version of object oriented programming for us。

So West Texas now to the middle。I notice how much more play that book gets to this grubby old blue book anyway。

 so that now takes us to about the middle of the 1990s。

Things were're kind of taking off and doing quite well。And now we come to the next event。

 which is in 1996。Rossy Haa and Robert Genman published a paper。

On something they just called a language for data analysis and graphics。

And just happened to have the name R。So this was expressed some ideas that particularly Ross had about better ways to do some of the things that were done。

 but as Ross was prone to say in talks at the time， it was a language that was not unlike S。

 and in fact， once it was out there， there was a lot of enthusiasm amongst number of people to make it into a free open source clone of the S language and over the next few years in the late 1990s group which came to be called ACO。

Got together and did that Ross and Robert very wisely and very generously。

Transferd control over R to the RA group， and at that point it really started to take off。

And the process was to replicate the facilities that were described in the blue Book and for the most part。

 in the white book in a new open source and portable language， and that's our。The event there。

 which is also has a very specific date， was on February 29th， 2000， which by the way。

 is a very unique date。And on that date version 1。0 of R was was produced。

 I wasn't part of ourco at that time but I was very friendly with them and one of my most treasured souvenirs is serial number one of the CD roms that were produced at that time for R autographed by all the members of our part very treasured momentum so that basically you know in a sense that was it and the rest has kind of been history R has really taken off and has introduced a number of additional ideas that we never had。

And there are now millions of users and many thousands of packages and on the whole it's a great thing and I'm just overwhelmed by it all。

 Well， I think the generations of statisticians that today's generation can be really grateful for all of this are is wonderful I've used it for the last 10 years love it Ive written packages to and it's just such a wonderful environment to be able to work in and it's free so really good and very high quality。

I think the most important thing， from my point of view， is that it's head。Very strong effect。

 I'd almost be tempted to call a revolutionary effect in the way new results in statistics are communicated。

 used to be people would just write a paper and then you would write to the author and try to figure out if theres some way you could implement what he'd done in some form or other。

For many things now， not all， but many things now people produce the code。

 they produce in our package and instantly everyone else can use what they've got freely and contribute their ideas to let things evolve and that I think is。

To my mind， the most beneficial result that's happened。 Well， thank you very much， Don。 My pleasure。

 John retired from Bell Abbs a few years back， and we have managed to lure him to Stanford where as a consulting professor in the statistics department。

Thanks very much thanks， bye bye。