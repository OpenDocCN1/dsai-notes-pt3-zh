# 密歇根大学《给所有人的Python课》课程4：《使用数据库进行Python编程》｜python-databases｜ - P30：30_04_02_附加访谈：Andrew Tannenbaum谈Minix系统.zh_en - GPT中英字幕课程资源 - BV1PP411W7H1

🎼你。🎼Yeah。🎼宝宝。We were an early adopter of version 6 Unix here and we had a Vax and PDicle11s and all that stuff。

 and so we were happy to run UNix and I was teaching a course in operating systems using version 6 UNix and John Lyons of Australia wrote a little book sort of。

😊，Describing it line by line， and it was very popular universities and the bean counters at AT and T decided this was a bad idea that you know having。

Every student in the world learn about their product which which they owned they thought was a horrible idea。

 so with version 7 came with a license saying thou shalt not teach okay so the version 7 license that you couldn't teach version 7 Uniix anymore which is it's got to be up there ranking up there or something Xerox did as you know the dumbest mistake in all of history but they did that so we couldn't teach Uniix anymore。

 I said maybe I'll write my own operating system which is compatible with V7 and then I can teach it。

 I sat down and I began writing and it sort of worked。

 I got it almost to the point where it worked and it was crashing at random it was e the functionality was there and it would run for 15 minutes and then it would crash and you know I was like about to give up I just couldn't know so I said you know I'll write a simulator。

For the PC and I'll run on the simulator because that's entirely deterministic and reproducible。

 And then after it crashes I can go run it again and print out the last hundred000 instructions。

 find out what happened。 so I wrote the simulator。 it took me a little while， but I got it running。

 so I had a complete simulator for the PC if I had been smart。

 I would have invented VMware in the 80s because I already I'd done basically with work I could have done translation instead of interpretation。

 but I didn't so I wrote a PC simulator， anybody could do that so I didn't care so it worked perfectly on the simulator It would run forever never it wouldn't run the hardware It only ran the simulator and I'm kind of crashed in my head from G。

How come one of my students， Robert from Vanessa mentioned me sort of I explain this prompt。

 mention me offhand。 you know， when the Intel chip gets hot。 it gives interrupt 15。

 And I said no does he said， yeah， I heard that somewhere。

 I said the manual doesn't mention anything about that。 And so I said， well。

 I don't know I can put in a test。 I wasn't catching interrupt 15， of course。

 because the manual didn't mention it existed。 So I put in a little piece of code which caught interrupt 15。

 And sure enough， an hour of running it， I get this message high。 I'm interrupt 15。

 This is impossible， you'll never see this message。 So I was saying all these very unpleasant things。

 which I cannot repeat about you know the Internet about Intel。

 if they want to put a thermal sensor great， please put it in the manual， though， you mention it。

 So I put it in and all of a sudden， Linux worked okay。If Robert hadn't made that comment。

 there would have been no Linux if there were no Linux。

 there'd be no Linux because Lenus went out and bought a PC specifically for the purpose of running Linux。

 he was in the Linux news group， he had a big news group using news groups he spent a lot of time developing Linux based on Linux he changed this he changed that and eventually it changed almost everything and so it sort of launched those its own system so if Robert hadn't made that comment would have been no Linux。

 there have been no Linux if there had been no Linux there would have been no Android because the Android is Linux and if there had been no Android。

 the relative stock prices of Samsung and Apple would have been quite different because the Apple was based on iOS。

 which is freeBSD， which came from a whole different strain of Uni so that wouldn't have been affected by the presence or absence of Linux but Robert's remark ultimately changed billions of dollars of valuation in the Samsung versus Apple stock prices and if he hadn't made that the world would be quite different there probably wouldn't have been an Android and heaven knows all the other things that depend on Linux。

And Android I mean server bits of all of that I mean all the server parts mean they might have been using free BSD or something instead who knows but you know the world that one little off-hand remark you know had all these consequences downstream then anyway I wrote Min and then I wanted to document it because I wanted something like Lion's book which explained in a course so the book most of the chapters have three sections one is sort of the general principles of file systems or process managers and whatever the second part is how these general principles apply to Min what is the memory management algorithm and how is the file system organized and what are the key data structures and so on the third part of every chapters now we're going to look at the code here on 10720 we see the main headers for the file system and here we're declaring these headers and now online 14000 we're starting with the actual main loop with the file system and it goes and gets a request and it takes it apart it's a switch them and it figures out what to do and it goes through the code bit by bit so it was like lion's code。

The book came with a bunch of floppy disks， which was the only transport medium in those days where you actually had the source code and so the book came out it was an enormous success and at the same time it was already BSD。

 which was a mature stable working system which had 20 years of background。

 the VX and the PDP11 and the guys who formed it MiKsik and so on they formed a company BSD incorporated and they were trying to sell it commercially and their phone number was 1-800 its UniX and so what does AT&T do again in one of the more brilliant commercial moves in all of history。

 they sued BSDI。To get rid of them and they had no knowledge of all how to sell unix。

 if anybody there had an IQ of above about you know， say two digit numbers。

 they would have gone to the BSDI guys and say we want to buy your company how much and given your AT& T。

 the biggest corporation the world no matter what number they had mentioned we would have said good sign here and they would have had the BSDI guys sell Uniix would have would have been no MSs dos。

 there have been no windows， it would been all unix you know and they try to stop these guys。

 So BSD was blocked from going commercial I knew about this。

 And so I didn't want to make Linux like big commercial thing。

 So if the BSD guys eventually they were going to go out there and that's a stable mature system with many programmers and many users。

 all software that would take over the commercial aspect of this free softwareer world but it didn't because of the stupid lawsuit from AT and T And so that was the interval that Linux got a chance to grow。

 So again one of those freaky。You know I said the bean coed AT&T who sued these guys instead of buying the company and saying。

 you're a marketing division， go sell it。あ。But at the same time， if you think about Min。

 it let Min the Linux。Movement let mimic stay for teaching and education for a while。

 yeah we we've changed that recently you know I got an one of these the European Union they decided to set up a couple of new programs where basically they would。

You know， give a large chunk of money， about two and a half million euro， which is I don't know。

3 and a half or$4 million dollars to one specific。Investigator there's two categories。

 young investigators who just sort getting started and senior ones who have a track record and basically let them go do their thing and I applied for this and I got one of them and with this ERRC advanced grant we're trying to go commercial with Linux we're pushing it in the area of embedded systems and high reliability because it's got a kernel and all these servers that run separately in user space is user mode processes and in particular if one of them crashes is's a reasonable chance we can repair it on the fly without disturbing running programs know and' if the disk driver fails we can detect that we can start up another disk driver and there's a glitch of a couple hundred milliseconds while we're restarting things but things go on the this driver and Linux crashes。

 that's the end of Linux you have to reboot all computer So we think there might be a little niche there。

 I think there's a significant niche actually I think the problem with modern operating systems is they're getting too large too complex and this breaks into little。

Yeah this breaks out into little pieces and another thing which we can do now and you before we started one of my PhD students came in。

 he's working on live update so we can update almost all of the operating system on the fly from version 3。

3 to version 3。4 which might have thousands of changes including data structure one on the fly while the system is running while application programs are running without changing or stopping or interfering with the running programs and this is tricky the model of course is that the person who wrote version 3。

4 was keenly aware of all the details of 3。3 so if there was some internal table。

 let's say the mount table which was simply a linear list in 3。

3 and he decided to make it a hash table in 3。4 because you could have a lot of things mounted then he'd have to write the code for converting one data structure to the other so basically you say I want to do an update and there a manager which handles that and the manager goes to the old one and says okay finish off what you're doing now。

 don't take on any more work。So cue it and then when you're all done。

 let me know when it's done then the manager starts up the new one and the new one then goes to the old one and says okay I need all your data structures and the LLVM compiler allows us to record inmemory。

 all the data structures very nicely their types and locations so it says to give me your first data structure and it gets the first data structure sees it's identical the old one if so just copies it if not it's got to run a routine to do a conversion from say a linear table to a hash table or a list of whatever the new one is and runs that it's all done the whole thing is converted it doesn't take very long computers are good at that and then when it's all finished it tells the manager okay I'm ready to go live the manager then changes all the internal connections the point to the new one makes the new one go live。

 kills off the old one and there you go and there's a slight glitch of a couple hundred milliseconds but the application when there was no file service but they don't know that unless you're doing hard real time everything works and we think that might be interesting for applications that never want to go down and they know that softwareers changed all time。

Security fixes and we're focusing this on the embedded world where I think there's a lot of interest in keeping the thing running all the time if you're running some realtime system。

 whether it's a radio telescope or electric power plant or some other realtime thing。

 you may not want to go down for reboots once in a while and so a system which could update itself which can repair itself which can try and to have a fairly high availability。

Might have a niche there we've got it working in the lab now for the Beale board for the Beale bone。

 we're bound to release it for the bele Black also， which is a really。

 it's like like the raspberry pie but even better。 So we're sort of trying to see if we can find a niche there。

🎼あ。