# UCLA《计算统计学｜Stats 102A - Computational Statistics with R 2024 Summer》中英字幕 p03 [03]Stats 102A - 2024 Summer - Video 3 - Configuring RStudio _ Troubleshooting R [BV1jizNBrEm2_p3]

Okay， so this video covers。Things that I think are important for getting set up in our studio。So。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_1.png)

I want to just talk about setting up a few things， a couple shortcuts。

So when you start working on your homework。I strongly。

 strongly strongly recommend creating a separate folder for each homework assignment so you know when you open the assignment on say ruin and learn。

 you know it's going to end up the file that you download the files you download will end up say in your downloads folder okay don't just open them up from your downloads folder but create a folder。

 either in your documents or even on your desktop or something。

 but create a folder called homework one and put your documents in there so say for this first homework and assignment。

 there's these different files that you need to download the the instructions PDF the。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_3.png)

The month names that TxT file and this RMD file， you're going to download those。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_5.png)

嗯。Those files put them inside your homework Now when you create your homework names。

 I strongly encourage not to put spaces if you want to have a space between words use underscores or dashes or something like that and you're going to put your files into there okay and then then you'll navigate to that file and open up the RMD file to work there and then for this first homework assignment you're going to have to kind of create a little script file a do R and you're going to put that into your same homework folder okay so。

Create separate homework folders， homework one， homework two， et cetera。

 and that's going to just kind of keep things a little bit more organized and keep things running smoothly。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_7.png)

![](img/3972f11f7ae9a1b32ed490cf975fc9e2_8.png)

And then when you're in R， okay， what you want to do is。

Let's let's say you have downloaded some of these folders somewhere。

 so you know let's say I'm going to create a folder。Called homework one on my desktop。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_10.png)

And we'll download。

![](img/3972f11f7ae9a1b32ed490cf975fc9e2_12.png)

Some of these files here， so I'm going to go ahead and click download。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_14.png)

So this is ending up over here， and so let's see。

![](img/3972f11f7ae9a1b32ed490cf975fc9e2_16.png)

I'll put my downloads folder。 so we're going。Move that into my homework one folder， okay。

And then we'll do the same with say the month names at TXT。And then the instructions folder。

 I'm going to go ahead and download that as well。And so here they end up over here。

 so instructions and month names。😔，Cut those。 Mo those into。Enter the folder over here。

So so here they are， and then you're going to， you know。

 say open up your RMD file and this will open up here， you know， you'll change your name。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_18.png)

So we'll say Joe Brun or whatever， okay？We'll save that and then what you want to do is under session。

 you'll go to set Work directory and you'll do two source file location。

And what you'll see is in the console what you should see is set working directory and this should be kind of the the folder。

 So here I created in my on my desktop homework one and yours might say like。Documents。

 stats 102 a slash homework one or whatever it might be， whatever folder， but。

 but that should appear there。 So you want to do that。 Okay， so you want to go to again， the。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_20.png)

The navigation is in the menu， go to session， set working directory。Two source file location。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_22.png)

Okay， if you don't do that， okay？If you try to do something like try to open a file。

 so inside this thing， it will say something like so one of the。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_24.png)

One of the commands here is read。 Dlim monthth namess that Txt and so because I have my working directory set here and I have monthth names that Txt set here。

 when I run this I'm able to to run that line and month names is now。

Inside inside my directory and I can I can see it right here Okay。

 so the the files are loaded up there okay now if for whatever reason。

 if I don't have the the folder in that， this file in there okay because I'm going to just kind of remove it put it back and say my downloads folder。

Okay。If I try to。Let me clear this out if I try to run this without month names at TX in there。

 I'm going to get this error it says cannot open file， Okay。

 no such file or directory cannot open the connection that means。In the directory that it's working。

 which is this folder here， it doesn't see the file and indeed that file is not there。

 It's in the wrong folder。 Okay， so this you're going to see some kind of thing if you don't have your file in the right folder or you have or maybe the file is in the folder but you don't have your working directory set So if you know if my working directory。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_26.png)

Its say set to the wrong folder。Set to desktop， okay？

If if my working directory is set to the wrong folder and I try to open up。Month names at TXT。Okay。

 maybe。Maybe I have it somewhere， but。it's going to encounter some kind of error message if it doesn't see the file in the correct working directory folder？



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_28.png)

So so if you see some kind of error like this error in the file can't open the connection， you know。

 that means are searching for that file and it doesn't see it okay， so you need to fix that。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_30.png)

Another big thing is in our studio， you have this environments。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_32.png)

Pain， okay。

![](img/3972f11f7ae9a1b32ed490cf975fc9e2_34.png)

And the environment's pain。This kind of contains all of the different。Objects in there periodically。

It's good to just clear all of the objects in your environment so you have an empty environment because as you work。

 as you kind of work through。

![](img/3972f11f7ae9a1b32ed490cf975fc9e2_36.png)

Different examples and work through different stuff。 This is going to get kind of cluttered。

 you know， you create a little vector， you load up， say month names or whatever it might be。

 whatever these different。Fileles and。Folders R and stuff like that。

 they start filling up the environment。

![](img/3972f11f7ae9a1b32ed490cf975fc9e2_38.png)

And。

![](img/3972f11f7ae9a1b32ed490cf975fc9e2_40.png)

You know， you can type out commands， but one of the easiest ways is to just hit the broom and that's going to just kind of sweep away and clear everything out of your environment。

 that's going to be the quickest way to kind of clear the environment okay and clearing the environment is also a good way to debug when you're trying to to knit okay but if you want to type if you're already in the constant and you want to type things out that you can also type an RM list equals LS fronttheess parentheses and that will。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_42.png)

![](img/3972f11f7ae9a1b32ed490cf975fc9e2_43.png)

Clear out the environment。So kind of one of the most common issues。Is my code runs in R。

 but when I try to knit， again an error， okay。One of the most common things。

 this is what I see posted very frequently on campus wire and things like this。What often happens to？



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_45.png)

Produce this problem I that， let's say。Let's say I'm working on some kind of R mark down document。

 okay？And。嗯。And let's say here， I'm going to just create a thing。

 I'm going to do like x1 through3 or something I'm going to just go ahead and delete。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_47.png)

So inside my R markdown document will say like。

![](img/3972f11f7ae9a1b32ed490cf975fc9e2_49.png)

Problem  one， okay。Im going to go ahead and I'm going to click knit。

And we will save this to our desktop under。Homework one， this will just be。

 we'll call this homework one example。Allright， so it's knitting。And。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_51.png)

I think。And getting it successfully， okay， so here here we just created x is one through three。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_53.png)

And。

![](img/3972f11f7ae9a1b32ed490cf975fc9e2_55.png)

And so I have this I have x is  one，2，3， and then let's say I do like x plus4 or something and that runs okay。

 and then let's say。I decide later to kind of change things up I make some changes to this thing and I say you know what I don't want x plus4 I want x plus 10 and I click run and you know sure that looks like it's working okay。

 I've got X in my environment and then I'm going to try saving this okay。And I try to click knit。

And then。I get this error message right， it's not letting me that it says object X not found okay but here I am。

 I'm in my R markdown document and I try to run this and it's running right I can change it x plus 11。

 it runs x plus 10， however runs， but when I try to knit。It's saying object Xs not found okay？

And the reason why it's running here but not knitting is because in my environment。

 I do have an X object。But in when I try to knit this， there's no X object created。

And so when are knits， okay， it always， the whole purpose of our markdown is for reproducibility。

Meaning I could give you this R Markdown file and you could run it on your computer and you will get the same results that I get。

And the way R does this is it always starts off with an empty environment。 So if I clear this out。

And then try to run this code chunk。Then I encounter this error message object X not found because we see in this document。

I never created X， so in order to remedy this。I have to add the line of code where we create x in the first place I create x as one through three or something Okay。

 and so now I can run this。And and this executes and I get 11， 12。

 13 and to just kind of make sure that it runs fine， I start off with an empty environment。

I can play this again and it runs。 And so now if I knit this。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_57.png)

Now it will knit。And now I can open up the thing and indeed I get x is one through three。

So so this is the most kind of thing is that yeah， a student creates an object in R and then you kind of modify or delete the line of code that creates that object。

 but because that object still exists in the environment or again。

 so if I get rid of this line that creates X， I can run this code that uses X。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_59.png)

Okay but I won't be able to knit because I never created X in this thing。

 so if I got rid of that thing it's going to say X not on right and so when it comes time to knit the line to create that object doesn't exist。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_61.png)

Or creates a different version of the object and our is enabled to execute that line。

 so just kind of。

![](img/3972f11f7ae9a1b32ed490cf975fc9e2_63.png)

To kind of debug these things。

![](img/3972f11f7ae9a1b32ed490cf975fc9e2_65.png)

This is how I recommend is to solve this clear out your environment。

you know save your thing and then just run line by line through your thing eventually you will probably encounter some kind of error message。

 see what line causes the error message and that will help you you know learn。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_67.png)

Where where the error is is being created Okay， so if you're able to kind of。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_69.png)

If， however， you are able to clear the environment and then run through every single line of code here。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_71.png)

Then。

![](img/3972f11f7ae9a1b32ed490cf975fc9e2_73.png)

Then your things should be able to knit without any kind of issues。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_75.png)

Okay。Sometimes。You try this and it still doesn't work and so resolving really steverborn issues。

Okay this is a lot more work and so I recommend it only if it's absolutely necessary and you couldn't figure it out before。

 but another kind of way to kind of make sure things will work okay。

 is you create a new blank R markdown document。

![](img/3972f11f7ae9a1b32ed490cf975fc9e2_77.png)

Okay。And and it always starts off with kind of some basic stuff， and then you try knitting it。

So I'm going to kind of just。We'll do this homework one。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_79.png)

New here and then you try knitting that and。

![](img/3972f11f7ae9a1b32ed490cf975fc9e2_81.png)

And it knits and this is kind of always the default thing that gets populated for that and then'll what you'll do is you'll go and you'll kind of delete everything out。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_83.png)

![](img/3972f11f7ae9a1b32ed490cf975fc9e2_84.png)

Okay， and then you'll start like and what you'll do is you'll take the document that isn't working。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_86.png)

And what you'll do is you'll copy one kind of chunk at a time。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_88.png)

Okay， so I say clear environment， creative new RMD。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_90.png)

And then knit that fresh RMD file and because it's brand new it should knit with no problems。

 then you delete anything from it， and what you do is you just copy one paragraph at a time or one code chunk at a time from the problem RMD to the fresh RMD okay after each。

After each kind of paragraph you copy over each kind of code chunk you copy over， then knit。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_92.png)

嗯。Kniit the new RMD file each time， right， so this will be like heading one。Heading one。

 and then paragraph one。So you start off fresh， you knit it and this knits just fine， okay。

 you open it up and you go， yep， that looks good。

![](img/3972f11f7ae9a1b32ed490cf975fc9e2_94.png)

![](img/3972f11f7ae9a1b32ed490cf975fc9e2_95.png)

And you just kind of keep going back and forth， copying new things over， right， paragraph2。

And you might find， okay， now we。Here's a code chunk one， okay？Coachju1。

And then then you try knitting this。And then you encounter an error message right。

 and so now we know the problem arose either in paragraph2 or code chunk one。

 because these are the things。You know， if I。After I put in Code chunk1， I'm not able to knit。

 but if I delete it。I am able to knit okay， so now I know the problem was in code chunk1 okay。

 and this the problem is because this is not valid code right， but oh I comment this out。

Now and it's just fine， Okay， so you kind of。

![](img/3972f11f7ae9a1b32ed490cf975fc9e2_97.png)

Copy something new and after you copy each code chunk after you copy， do this， try knitting again。

 and then eventually you'll probably copy something over and then it no longer knits okay and when that happens。

 you know the problem resides in that。Chunk that you just copied over and you can kind of verify your suspicions by just deleting that chunk。

Deleting that chunk and then knitting it and if it doesn't it。

 then you know for sure 100% the problem is in that one code chunk that you or that one chunk of text or chunk of code that you copied over。

 and then you can kind of look in really closely to try to figure out where something。

 where the problem is and that way you can kind of resolve the issue so that would be the strategy for resolving kind of really stubborn issues。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_99.png)

When you're trying to knit。

![](img/3972f11f7ae9a1b32ed490cf975fc9e2_101.png)

Okay， another important thing is set your language to English okay and I recognize this is very kind of I guess。

 anglocentric by saying this， but you know I require that you knit your homework into PDF with lateEEC and things like that。

 and。A lot of kind of foreign characters are not set up to work with latex， and so in R。

 if you have your language set to a different language。

The error messages will not appear in English but might appear in a foreign language okay and so when you knit your homework。

And if your' homework。And in R you can set your options to still knit the file even when error messages appear。

 however， if that error message contains foreign characters。

 it's going to cause problems during the latete rendering so what you'll want to do is you'll want to set your R language to be English so that the error messages are always in English and then it can kind of knit and so here's a couple links for you know how to set your language to English or you can just go on Google and search how do I set my R language to English and these are there's going to be。

Different kinds of things， but oftentimes if you see something like this Unicode character is not set up for use with latete。

 that might be because your English language is not set to English Okay another time you might see this kind of message is if you ever copy and paste something from a PDF file okay。

 so sometimes when，You。When documents process create PDF files， they put in funny characters， right？

The dash becomes a longer dash or you know the quote marks。

 you get fancy quote marks or things like that。And and those things might not be compatible with with latex or R as well。

 and so sometimes you might get something about Unicode character or something like that and a lot of times you can kind of。

You'll see this little U code and you can search for that on the internet and you can find that particular character。

 the offending character somewhere in your document and delete it and just replace it with something else。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_103.png)

Another thing。Is don't under our global options。

![](img/3972f11f7ae9a1b32ed490cf975fc9e2_105.png)

Okay， oh， I have this set the wrong way。Uncheck this okay。

 restore our data into workspace at startup， uncheck that okay。

 and then save workspace to our data on exit， I always choose never okay。So uncheck this thing。

 restore our data and save workspace to never and。

![](img/3972f11f7ae9a1b32ed490cf975fc9e2_107.png)

![](img/3972f11f7ae9a1b32ed490cf975fc9e2_108.png)

Then I'll click OK and that will just kind of。

![](img/3972f11f7ae9a1b32ed490cf975fc9e2_110.png)

Help avoid issues with a bunch of stuff being in your environment Okay。

 because if you have stuff in your environment every sometimes it loads up options from packages and things like that and that could throw off even just like the way。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_112.png)

Like the sample function works in R， just different kind of things can be affected so so set these settings here okay。

I wrote not saving on exit forces you to have good habits。

 it also prevents issues where your script receives old and incorrect values when it refers to common names such as X or results or something。

 if you don't save your workspace on exit， then those values won't exist when you try to start our studio at the same time okay。

And if you want to save your workspace， you still can， you just have to do it explicitly。

 just click the little save icon for save workspace。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_114.png)

![](img/3972f11f7ae9a1b32ed490cf975fc9e2_115.png)

Okay， a couple shortcuts as you're working， you can toggle comments in your code so this thing。

 you can hit control shift C。

![](img/3972f11f7ae9a1b32ed490cf975fc9e2_117.png)

Or command shift C， and that will toggle that line of code with a comment or not， I mean。

 it's not very hard to hit pound， but you can do it with like。Multiple lines， line line two。

Line three， line four， and you can highlight them all。And you can toggle all of them。

On or off at the same time。 Okay， with command shift C。 So that's that's a handy little function。

 okay。

![](img/3972f11f7ae9a1b32ed490cf975fc9e2_119.png)

With you can create new R scripts。Right here， new R script control shift N。

Or you don't see whatever thing you have there， and then you can always kind of hit command En with each line。

You can highlight a block of text and it'll run that thing。Or if you have the entire script。

 you can hit commander control shift S and it will run the entire script there。Other useful things。

 Commander control L， or you can hit this broom to clear out the console and to knit as commander control shift K。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_121.png)

When you're working on some kind of arm lockdown file。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_123.png)

Okay and then restarting that so those are handy little shortcuts I think the setup and helping you kind of troubleshoot the knitting and whatnot that's going to be the most important part。



![](img/3972f11f7ae9a1b32ed490cf975fc9e2_125.png)

![](img/3972f11f7ae9a1b32ed490cf975fc9e2_126.png)

Alright。