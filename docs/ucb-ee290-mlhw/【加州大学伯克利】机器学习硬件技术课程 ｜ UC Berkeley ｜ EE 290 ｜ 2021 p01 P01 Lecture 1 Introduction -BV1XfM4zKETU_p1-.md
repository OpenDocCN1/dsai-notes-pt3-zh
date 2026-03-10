# 【加州大学伯克利】机器学习硬件技术课程 ｜ UC Berkeley ｜ EE 290 ｜ 2021 p01 P01 Lecture 1 Introduction -BV1XfM4zKETU_p1-

嗯。

![](img/fca11fc3022e0fc4a15a69b45a986428_1.png)

Okay， good afternoon， everyone。 Welcome to EE2902 hardware for machine learning。

 It's great to see you all here。 I'm Sophia Shao， I'm a faculty member here at UC Berkeley will be the instructor of this class so we will meet at 2 to 3。

30 PM Pacific time every Monday and Wednesday， the entire class will be online unfortunately。

 but it's also a good thing that we are able to actually connect with people from all over the world together through this class if you are not aware already our course website is here。

😊，It's here on top of the slides where you can find out the course related information here so it will be using Zoom for the entire semester if you have any questions throughout the lectures both our lecture regular lecture and guest lecture we'll talk a little bit more about the class structure later feel free to just unmute yourself and ask you I'm looking forward to hearing from you and also connect names with faces。

 I think I saw a lot ofbinner names many of them either from 151251A last semester or from the grad students that I have interacted with before but it's still good to hear from you and see your picture at the same time also feel free to use the chat window to talk to your classmates share any thoughts that you may have and if you have any questions also feel free to post that here。

So with that， let's get started。😊，This is a really exciting topic Many of you have reached out to me separately before this semesters say you are really interested on hardware hardware for machine learning。

 either you are from a more machine learning or software engineering background or youre coming from a more hardware oriented background both are actually perfectly fine。

 both are the exact background that we are looking for for this class。

 So in today's lecture talk a little bit more about some of the general background about this course。

 but also the general motivation about hardware for machine learning。

 what we will be covering throughout this semester I will also talk a little bit more about the course structure。

 some of you already reach out to me about prerequisite or different components of the class will also get to that in today's discussion So with that let's get today's lecture started。

😊，So first。See。Okay， so as I mentioned earlier， this is a relatively new class。

 so it was first offered last year and due to the very positive feedback that we received from both students and faculties that are interested in this topic we decide to offer this class again with some modification。

 So this time will be hopefully more polished but also with more structure discussion and also more updates in really thinking about some of the new development around the topic。

😊，So what's this class about as I mentioned there are two different backgrounds or two different types of students that are actually joining this class One is actually more on the hardware side。

 students with a lot of hardware design background but interested in actually getting into machine learning understand what are the implications of machine learning at the same time we also have groups of students also folks with background more on the machine learning side。

 but throughout up their development， they realize the importance of the hardware and also seeing a lot of exciting development on the hardware front。

 so they are also really interested in learning more about the hardware。😊。

So what this class is about is really a bridge between the way we think about hardware and also the way we think about machine learning。

 so we're going to use machine learning as a driving example to think about how we would actually design。

 especially future generation of the hardware， not only thinking about the general progress processing。

 but really thinking about all the emerging applications and with their unique demands to actually drive the hardware development。

😊，So raise this in mind？The particular goal of this more concrete goal of this class。

 what you will get by the end of the semester is really actually to enable you。

 all of you taking this class to be able to actually build efficient hardware so we are this is still a hardware oriented class where very interested in actually thinking about the hardware design and also enable all of you to participate in the hardware design process with this particular goal in mind。

 as I mentioned earlier， well be using machine learning as a driving application and throughout the semester we'll talk about what are the hardware maybe also software optimizations that you need to consider what are the general hardware design principles that you need to be aware when you get to designing hardware for emerging applications like machine learning。

😊，So this is our goal， this is the goal， really the goal or the core objective。

 what we want to achieve by the end of the semester。😊，So how do we get there So as I mentioned。

 this is a very handsz class right we want to help you work with you to actually to be able to that you will be able to build things。

 how do we get there So of course we'll talk about since we're using machine learning as a driving application。

 We'll talk about what are the core characteristics of the machine learning applications This is not a machine learning class so will not go very deep into all the different variations or different algorithm development of the machine learning。

 but we do want to communicate with all of you using the same terminology。

 what are the key behaviors that we especially as hardware designers need to be aware of from the machine learning applications So that's the first part second part。

 again， this is a hardware class right so we are very interested in really thinking about what are the different hardware optimizations that are very important and also necessary。

To achieve our goal of accelerating machine learning applications。 So in that context。

 we'll also be able to will also learn all the core design principles。

 especially on the hardware front to。😊，Acceleerate or to to achieve both high energy efficiency and also high performance for those emerging applications。

 so that's basically our core approaches on both application and also on the hardware front。

Finally will also include actually a series of very interesting guest lectures most of the speakers will be actually from industry。

 this is a very applied topics so we are really talking about some of the actually existing commercial state of art development in our industry so when they will notice a lot of the hardware related topics are very applied we work with industry all the time and were really interested in understanding what are the challenges that they run to especially when they actually deploy these kind different flavors of hardware for machine learning so that will also be very important and we hope to use these guest lectures invite speakers from different companies talking about their practice what they have observed when they actually deploy deep learning applications either as scale in data centers or as extremely lowpower device。

😊，All of those are very important for all of us to actually both understand some of the realistic constraints。

 but also think about how our ideas can be also potentially commercialized in the future。

So that will be the three core approaches that we'll discuss some or more on the machine learning side。

 some more on the hardware side， and again， with a very realistic and also practical approach to understand the industry challenges。

So with that， as a course overview revealed， as I mentioned earlier。

 I'll talk a little bit more about some of the general challenges or general exciting development on both application and also on the hardware front before we also get to some of the course organization and how we like to structure the course this semester。

😊，Um。Again， if you have any questions feel free to use a chat window or just unmute yourself。

 So for the next part I'm going to talk about just a general topic about machine learning。

 not getting into the specific algorithms or different behaviors。

 but really talking about some of the excitement on the application side and how that has actually shape the industry。

😊，So in particular， when we talk about machine learning a lot of time we are really talking about deep learning。

 we'll talk a bit more of the differences between machine learning and deep learning in our next lecture。

 but so far let' just mostly focus on the deep learning slide and whenever people talk about deep learning development。

 there are always three very important components associated with deep learning development。😊。

The first part is what we call bigger data。 What we mean by that。

 But data is actually really important whenever we get to any deep learning development。

 no matter we're talking about startups， how they actually accumulate a large amount of data over years to develop efficient algorithms。

 Also all the different big enterprises and how they actually use the data that they either already have or they collect based on the user interactions to actually get bigger or better model trained to do better production。

 So data is always very important， whenever we talk about deep learning application。

 just in particular， just in if you think about the development of deep learning our machine learning in general。

 right， so a very important event for the entire machine learning or deep learning field is really the construction of the imagenet data。

And if we think about one of the earlier successes of deep learning is really how a simple network what trained on we'll talk about later on GPU is was able to outperform a lot of other more traditional machine learning model on the imagenet context there。

 so having a large data set， having a standard benchmark suite is very important both standardize the field so that we can actually compare either our algorithm or even hardware。

 we'll talk about some of more recent development on the benchmark in front。

 but also in a realistic development setting， whether you have enough user data。

 whether you' are able to actually accumulated enough user data or behaviors data over time。

 is very important to the success of either your organization working on the deep learning front or your startup some when we approach your。

Valuate a particular idea if that's actually， they call them a deep learninging。

Start up they have some new algorithm Of course algorithm is important。

 but another very important thing component is what kind of data that you have to train your algorithm So whenever we talk about deep learning data is always very important angle。

The second part we'll briefly talk about today is basically the algorithm。

 this is probably what you will interact most when you like take a machine learning class either here at Berkeley or there are like a lot of like machine learning tutorials available these days which will cover all the different machine learning algorithms or deep learning algorithms either convolution in neural net graph neural net or like OSTM or you learn all the different。

😊，Neural network architectures there。 So those are basically what we call algorithms。

 This is also a very important and also exciting field。

 If you look at today's like machine learning or neural network or deep learning。😊，Conferences。

 a lot of papers recently published is basically about algorithm development right。

 what are the new network architectures， what are the new operators that can be actually used to better extract the data behaviors to actually better learn the data statistics that we mentioned earlier so that's also a very active field of both research and also deployment these days in really thinking about the algorithm development。

Finally， and at least in my mind depends on who you talk to。

 another very important component for especially today's success of deep learning and the wide adoption of deep learning applications is' really the compute power right。

 so we mentioned earlier， one of the earlier success was Alexnet which was one of the earlier networks that were trained using the imagenet data we just talk about the benchmark later but also using GPU so Alex was able to actually use GPU to actually train his network。

😊，And back then like now we know GPU actually designed a lot more features to support deep learning。

 but back then GPU was actually it was a general purpose relatively general purpose platform for a range of different applications and it happen to be without without actually designed for deep learning。

 but it happened to be actually really good fit for a lot of deep learning algorithms that we discussed earlier So with that with the more powerful GPU coming up and also all the different other kind of hardware。

 so this is also a very active field in really thinking about how we can design either better hardware or new types of hardware to support the computational demand of deep learning So for this class and for a lot of topics that will touch on throughout the semester。

 we are really interested。In this interface， basically how the compute hardware。

 which is very important to enable these kind wide adapts and to make deep learning actually feasible using today's hardware。

 how we actually interact with data， how we can actually orchestrate data movement。

 how we can actually understand data different data behaviors and also interact with different algorithm what kind of algorithm would actually work fairly well on what kind of hardware platform and what would be the limitation of some hardware platform to interact with other algorithm。

 So all those are very important our three components are very important for deep learning for this class for our discussion in particular。

 we like to really understand。What's inside so we talk about GPU is that the only solution。

 what are the other types of hardware available here and how would our hardware。

 especially the new generation of hardware interact with the data and the algorithm in the deep learning field and finally what are some of the newer generations or emerging generations of hardware development that can be also potentially used for machine learning application in the future All of those are very important questions and will be able to navigate all of them throughout the semester。

😊，So with that。Whenever we talk about deep learning。

 I like to use this kind of really thinking about this scale。 What do I mean by that deep learning。

 of course， it is very interesting from its algorithm as a very unique or a domain of algorithms but what's really impressive is how this particular domain of applications or domain of algorithm that we discussed earlier。

 we're able to reach so many different corners of our daily life。

 not only just for all the different applications that I mentioned how it's actually being applied。

 like all the different fields are actually related with machine learning。

 whenever even we're talking about medical area， like media entertainment and security。

 autonomous machines， whenever we talk about this very exciting topics which is actually very complex on its own and theres always discussion about how deep learning could potentially enable it or have already。

😊，End some of the very exciting recent development。 So it's not only let's say。

 an interesting application to itself very limited to what we we used to say that computer vision type of application。

 Now， it actually has touch on all the different application domains。

 And whenever you talk to all the different developers， even hardware developers these days。

 Some of the hardware developer they are also using。

 They actually users of machine learning algorithm to actually apply machine learning in their unique application domains。

 So all those will be very important and one interesting and also very important。😊。

Scaating behavior of deep learning is how it has been adopted or potentially can be adopted。

 adopted in all the different application domains。 So that's the first scalingkating dimension。

The second skating dimension is really related right so in so many different domains。

 so many different algorithm designers， software designers。

 even hardware designers need to actually apply deep learning or understand deep learning in their day today jobs we just look at the job posting。

 this is actually a piece of data I find found a little bit older already like two or three years ago so just looking at this like exponential growth right that we have been observing in the past three or four years that is thinking about all the job posting that mentioned deep learning skills and this can be actually potentially deep learning developers or algorithm developers who will be actually developing deep learning algorithms。

 but this could also be all the different fields that we mentioned earlier it just become a very useful skill set for any hardware or software designers or engineers that they want to。

😊，Be able to use that as a user in their future job responsibility。

 so we're not only talking about deep learningning as an individual application these days we're talking about all the different this large user bases and continuing growing in the at least in the near future and all of them will be actually using deep learning in different aspect of their job。

So this is in the， I guess more on the development and on the apply side and another part of your grad student you probably really hear a lot about paper publications and also you read a lot of papers and one thing some you may already notice that the types of papers that you read every day right not only like papers that very specific to your field but you start also seeing a lot of other papers especially related to to machine learning and that's another exponential growth that we're observing these days just the number of papers published machine learning related specifically deep learning related topic that's basically also growing very significantly I also subscribe the machine learning archive paper but at this point it's just very hard to keep track of all the machine learning paper that publish。

😊，Not only every day， like every hour， every minute。

 just like so many new ideas and so many new talents。

 like all the job posting that we mentioned earlier。

 a lot of talents are actually in this in this field that actually produce also a lot of new ideas and also research papers。

😊，So that's also maybe more on the research side， there is also this is also a very active research field。

😊，So with all the different， both like we talk about the application。

 more domains we'll be using machine learning， more engineers we'll be using machine learning。

 more researchers are talking about machine learning in their research world。

 all of this eventually will basically translate to this huge increase in computational demand when we actually get to the hardware part。

😊，What do I mean by that？ So this is actually a very interesting。

Data that shared by by open AI a couple years ago。 I think they actually keep updating this data figured。

 So if you're interested， you can go to their website to get even more updated。 So this is last year。

So what they did is basically they plot over the past。

 I guess six or seven years over the past few years。

 they plot the computational requirement that's actually required to train all the different models。

 with model like we mentioned earlier， different network architectures or different algorithms and different terminology can be applied here。

 but to train all the different models， what the computational throughput requirement and how that has actually changed。

Over years。So in particular， the particular metric here that we're using is petafflps per day for training。

 What do we mean by that。 So petaf fls is basically floating point operation right so petafflps。

 So giga is 10 to the 9 Ter is 10 to the 12 and petta is 10 to the 15 right so this is basically a huge amount of operations。

 floating point operation that actually need to be be done in parallel and every day to actually to train those models and and this is actually in log scale for the one axis here。

 So what we see here。So from the initial development of Alexnet from 6，7 years ago。

 and then all the way to this kind of more recent development。

 with especially with reinforcement learning and all the different neural machine translation。

 like all the more recent networks， we are observing。😊，More than。

3000 x increase in the computational demand。This seems very scary， right， So all of a sudden。

 we're not all the models are actually not equal。 right， Some models are easier to train。

 Some models are actually a lot more expensive。 require here as it indicated 300000 X increase in a compute throughput at this time at the same time。

 this is actually very good news for hardware designer。 You know， the bad news， whenever we here。

 there is a problem。 there is a demand for compute throughput。 That means good news。

 It means that we still have a job， right， we are we are in desperate needed need to actually produce better hardware to support this demand。

 that's actually very important。 So this is actually good news for hardware designers。

 whenever there is a problem。😊，That means hardware designer need to actually go there to understand what's the problems and also try to provide a solution。

 So here there' is a clear demand right for all the increase in computer computer throughput with all the different networks actually being developed and ways this kind of even more adoption of deep learning into all the different areas those like all the different researchers。

 the very smart， very talented researchers， they will be actually using more data available to them and the more complex models that they can actually device to think to actually get to better even better performance at the same time there is a hardware cost right it also required more hardware to train even to compare different models and all those specific peoples a very unique demand for hardware designers how to handle this large scale。

 how to handle such a high demand。😊，For computing input。

So those are some of the skating challenges and as a natural question to ask。

 like with all the important skating questions and wide adoptions of deep learning。

 we also see this unique challenges on the compute side how we actually can support those compute throughput So next we're going to transition to okay。

 so here is a problem with said hardware designers are looking for for new problem for new challenges。

 right so there is a problem， There is a new challenge what are the current solutions。

 How do we actually try to address this kind of problem。

 So that will be the second part and that will also briefly discuss today。

 what are some of the existing hardware solutions for machine learning。So before I move on。

 any questions or comments or any observation that you see in your own field that you'd like to share with everyone or with a class。

Okay， or feel free to unmute directly or just use a chat window to post any comments。Okay， so。

So those are some of the challenges that we discussed really exciting development right so whenever there is a strong demand for more resources。

 I think a lot of pressure is basically put on the supply side and a lot of what we'll be discussing throughout the semester is what can the suppliers do right what are the tricks the supplier typically play。

 are those tricks still applicable when we get to the hardware for machine learning if not。

 what are some of the alternatives there so that will be we'll some high level some of the discussion there but will also cover a lot more throughout the semester to see what are the principles when we get to the hardware for machine learning front。

😊，So as I mentioned earlier。There is an increase in demand for more computing throughput throughout all the different。

Application domains and also throughout all the different research developers。

 research engineers or developers in their own areas of expertise so this is what we this is on the demand side or the huge demand from all the applications What are the tricks what are the what are the skill set hardware designers or hardware the semiconductor industry typically exploit to actually meet the computing and demand。

At this point， many of you should already be familiar with what typically people call Moore's law it's very hard to actually get to a hardware related talk without actually even mentioning Moore's law so we'll not get into Moore's law in today's class。

 but the reason we bring up Moore's law here is that it is a very important trick you can call it trick or important hardware optimization or just important principle that the semiconductor industry has been。

😊，Has been exploitding for the past like five or six decades。

What is trying to what they can do by leveraging more as well is basically every roughly two or three years。

 you'll get more transistors and hopefully better transistors so that your performance can basically improve hopefully significantly。

A bifactorual tool or also your energy efficiency could also improve because the transistors shrink significantly。

 Well， that's a hope it was the case actually for a long while。

 So that's why people like talking about Moore's law because we have been following that very faithfully You can also call this self fulfilling prophecy and we have been actually following the law pretty closely and for many decades that we the semiconductor industry has been consistently developing basically every two or three years getting a new generation product that is actually significantly better。

Than the previous generation。However， when we get to actually the more recent development in the recent like5 to65 to 10 years。

 of course it depends on who you tap to， some people say the end of the Moores law some say people still say okay Moore lies live and well people have different views on the Moores law front。

 but what we are observing is that first we are not observing doub in the performance。

 that's just big too good to be true。 We see some performance improvement every generation but not that significant。

 We are also not seeing a lot of efficiency improvement in the past few years Of course the area is slightly better。

 but not really like two x better。 the transistor is not actually getting shrinked half of its original side。

 So get some like density benefit but not really2 x and by the power the energy efficiency benefit has been。

Either very flat and sometimes it actually even get worse。

So that's really on the more like hardcore metric side， but even on the economic side。

 it's actually getting a lot more expensive， the semiconductor industry is pouring a lot of money into actually the fabrication process trying to advance different fund is trying to advance to the next more advanced technology node。

 but it's always been a very expensive， especially more recently it has been even more expensive。

 so won't talk about that in today's lecture， but I mentioned that in some of our earlier discussion in either like general tax or like 151251A。

 just like the number of Fs that the number of companies that actually involved in the fabrication process also shrink significantly because they cannot afford the cost。

 the R&D cost that need to be put into to actually develop the next generation of the semiconductor node。

😊，So in fact， put whether Moore's law is alive or not aside。

 it's definitely harder to actually rely on Moore's law to get better performance and efficiency。

 especially in recent generation。😊，So whenever I talk about this。

 I always feel like it does this feel like very appropriate for our industry and for our especially for our field。

 it's the best of time it is really the best of time we see this emerging this huge amount of demand for computing throughput from of course machine learning but also a lot of other applications。

 they all require more processing power， more computing power to actually support their software。

 their algorithm development to handle this large amount of data this at the same time。

 it is also very challenging， we have some tricks that we were relying on for a long time that we think it will work it will always work but it turn out to be not the case anymore and we actually really need to think about new solutions。

😊，To make sure that we can actually meet the demand。

 provide better hardware to actually really satisfy the the user' request。

 the the increasing demand for the for more computing power。

So with that one of the what are those existing solutions so one of the more promising solutions that are actually being widely adopted in today's industry is what we what people call domain specific accelerators ESAs you may also hear people select like specialized accelerators those are all the roughly the same thing so in general specifically means customized accelerator hardware that are actually being designed specifically for either one application or a domain of applications。

😊，So in general， whenever we talk about specialized accelerator。

 I typically point people to actually a mobile processor， which is basically in general。

 one of the frontiers， one of the early adopters of domainspecific accelerators like this year is actually even better like we also in different context we also talk about apples and one chip that actually being used in MacBook Pro and air and also mini in their desktop in their laptop line which is also an SOC or system on chip that has different domainspecific accelerator。

 so it's not only in the mobile market market anymore。

 we see actually wider adoptions of domainspecific accelerators in all the different hardware devices that we're having these days so still using a mobile SOC as the example because it actually works fairly well to represent some of the state of art。

where that we're observing these days so this is one of the Apple SOC I guess at this point two years two years old like was out like 2018。

 but it's a fairly representative design when we actually see SOC was basically what we always see like CPUU general purpose processing unit and also graphic GPU graphic processing unit。

What's really interesting is we see a lot of adoptions and this is the first generation of Apple SOC actually start building what they call neural engine is' basically a specialized processor for deep learning and they have been actually doing that for their future for their later generations as well and even the M1 their MacBook Air and Pro SOC also have a dedicated deep learning accelerator there so those are basically a very representative example of domain what we call domain specific accelerator that hope we are actually designed for specific application。

 so instead of thinking about CPUU GPU where we design general purpose pipelines to actually execute any type any any categories of instructions those are actually custom design to get rid of all the all the inefficiency of general purpose processing。

For this domain of applications so that we can achieve both high performance and also high energy efficiency。

So， this is。Just one of the examples of the adoptions the domain specific accelerators。

 one more thing to highlight here is that it's not only just I say one generation we see。

Accellerators over the past decade， right， we actually categors just as a number of different IP blocks or domain specific accelerators that are not CPU。

 not GP that but exist across generations， Apple S O Cs。

 We also see this kind of very consistent improvement or our increase by basically having more on chip accelerators actually in our S O。

 which kind of makes sense。 We talk about all this kind of computational demand， right。

 from across different domains of applications and all of them require more computational power if like CPU cannot actually support those those computational demand or at least on on itself。

 there need to be more customized designed hardware。

To actually meet the demand as we are actually marching to get more efficient hardware。

 get more higher performance hardware for all the different applications that we care about at the same time。

 we also need to design a lot more different applications to support all the different computational demand right。

 so that's also something we are observing these days。So before I move on any questions， comments。

Okay。Great， again， feel free to post your questions in the chat or just unmute yourself。

So so far we talk about some of the hardware， like what are the like。

Approaches that's not really working anymore what are the some of the promising approaches and we mention the deep learning specialized hardware design can be a very promising solution to support all the different compute computational requirement right so this is also very exciting for both hardware and also deep learning front because there is。

 as we mentioned earlier， very clear demand and also a very promising hardware solution and whenever this pair actually come together it basically means a new business idea so this is one of the New York Times post that we saw like two years ago。

 two or three years ago actually。Counting the number of startups working on not actually on deep learning startups。

 This is actually just counting the number of hardware startups actually working on hardware for machine learning。

 basically the topic that we want to cover throughout the semester So back then there were roughly 45 there this is from Professor Viie ready from Harvard in one of his MPf discussion。

 I think he has a more recent versions saying this is not only 45。

 this is actually roughly 100 different startups available at this point and also maybe actually some of the 45 startups either failed or have actually been successfully So to other companies。

 So a lot of dynamics going on definitely here。 but one thing for sure this is a huge business opportunities that attract a lot of not only just deep learning developers but also hardware developers to really。

Thinking about what are the unique opportunities that they can do。

 they can leverage to get get a stronger control of this big market， this huge market。

 actually from both deep learning side and also the hardware side。As I mentioned earlier。

 some of the startup has pretty good exit strategies and some either well some of them failed。

 some of them good access strategies already been bought by bigger companies so this is one of the companies Havana that was sold to Intel like one year ago exactly one year ago so there are more other like startups also being either acquired by larger companies or like bigger companies start building their own hardware components so this is really exciting in the sense that a lot of discussion when we talk about hardware companies it's always very limited right so every time we're talking about a small group of companies like Intel EMV and then media Qcomm and maybe but now it's not only just a semiconductor companies a lot of software companies and also the startup companies are participating in this game so。

It's actually an interesting playfield that you're observing in both hardware in general。

 but especially in deep learning hardware。Bigger companies do have their advantages。

 They have generations of hardware development， but smaller companies really have they really have a good idea either more on the application side or more on the hardware side。

 they can actually explain the very niche market and also thrive in their market and similarly for software companies we mentioned like both data and algorithm are also very important for deep learning development in general and those software companies have a lot of data and has a lot of understanding on the algorithm front。

 even they were not doing hardware before， but now hardware is also a lot easier to do。

 especially with the fabulous model So now a lot of software companies like Google。

 Facebook Microsoft are also getting into the game So it's a very exciting and also very competitive field when we get to the hardware for machine learning front how what's the dynamics these days how does those like how do those。

😊，an big semiconductor companies either interact with the software companies。

 which could be both their clients， but also their competitors and how do people actually interact with the startups which could have a very interesting ideas and potentially being acquired by other big players in the field。

So this is a very interesting area， a lot of very interesting dynamics。

 if will follow some of the news here and we do hope to by bringing both having some discussions in our lectures but also bringing our industry collaborators to also share some of their practical perspectives。

😊，So we talk about the different hardware here and we already hinted some of the major players we'll list some of them this is not supposed to be exhausted is not supposed to be exhaustive list there are a lot of players if you're following the news you will also see a lot of startups coming up not maybe not every day but let's say every month or every year so keep eye an eye on this the field but we will talk about some of the major player here so the first one is Nvi we already mention that one of the early successes of deep learning is really using NVs GPU even back then it was not designed for deep learning but it was designed for parallel computation and deep learning turned out to be a great fit following exactly the principle of parallel computation so GPU is actually a great fit for deep。

😊，Turningearning， which is very interesting， started as a very general well not very but relatively general purpose platform and then being adopted for this particular application domain that become one of the major revenues。

 actually for the entire graphic art business。😊，So GPU is actually being widely used in today's data centers。

 high performance computings， and it also has a lot more actually custom like we mentioned earlier。

 very very beginning， it was actually not designed for deep learning。

 but over the years they actually added a lot more specialization or customization as we mentioned earlier for deep learning。

So one thing you may heard people call especially Nvi NVDdiaA hardware is this Tensor core unit we' also talk a little bit more about Tensor core later。

 but it's basically you can at a high level you can think about matrix matrix matrix multiplication unit doing basically multiply and accumulate over time but very efficiently with dedicated hardware so the V100 was the first generation that has the Tensor core unit last year NV release a100 the MP generation it also have actually some of the sparsity support and all the different precision support to actually better both leverage the behaviors of deep learning and also data very better efficiency So NVDdia is a very important player in this field and they are also doing a lot of very interesting customizations for the。

Deep learning applications。Another one， some of you probably already seen that we also mentioned that in in like 151 to51 day last semester like I mentioned like a lot of very interesting development in the startup space right So one of the I would say at least high impact most high impact startup that got a lot of attention especially in the past two years is ceus。

 which is actually have very unique like selling point of the way they do hardware。

 they instead building what's the traditional chip being packaged being fabricated and package into a package。

 what they have is what they call like wafer scale computing， they basically get the entire wafer。

 they don't need to actually dice it up into individual chips they just have the entire wafer which can be huge and then that's basically one single chip in their in their product so。

Is basically their first generation Sarahbras chip that's basically as big as your mouse pad here right that's really cool and it's really hard to imagine this is actually done from a startup we always say like semiconductor industry has very high entry point but this amazing very challenging technology is actually coming from a startup and that actually is willing to take the risk and I believe this this the picture was their first generation and they have a second generation and they already have customers so far mostly national lives but they already have their customers actually being adapted being used so this is an example of this very interesting development on hardware for machine learning not from the traditional players but also but actually from the startups here。

😊，Another example， I will not get too much into this but just thinking about the players。

 we talk about startup， it's hard to call Tesla startup at this point。

 but at least not a traditional semiconductor player， but in one of their offering。

 they actually also did deep learning accelerator or what they neural network engine here for their self-driving car and this hardware。

 this piece of hardware is actually developed inside Tesla。

 which I guess it's a car manufacturer but then also getting into the semiconductor business。

 just thinking about all the different things that can we see actually being developed here。😊。

So Sina is asking question on their major yield issue when chip this big for the cebra example。 Yes。

 that's a really good question。 That was one of the challenges for this kind of。Wafer scale right。

 so we always say like oh there's yield issues， you cannot guarantee every every chips if we actually do have a wafer。

 we cut it into individual chips， we cannot actually guarantee all of them working and typically not all of them are working right and also especially with more advanced technology that has been actually been a very major issue so they do have that issue even when they get a full wafer is's not guarantee actually all the individual let's don't call it the chips so let's don't call it the individual components of the wafer is working。

It's not the case What they do at least mention， of course。

 there's a lot of details in their hardware， but what they do say is that there is a thought tolerance mechanism built into the hardware design where if there iss for example。

 some yield issue and one those components there is actually not working anymore。

 they can actually bypass those components but still connect other other chips or other components I say on the wafer together。

 so with the entire wafer they still have this big wafer。

 but not all the components on this wafer are working that's not the case。

 they do have the thought they do need to have and of course they they do need to have and I believe they actually also mention that in there in both they are a software flow。

 they need to understand different wafer actually they will have different yield issues and different patterns of whether a particular components has。

Is failing or not and also software workaround and mechanism to work around to bypass those failed chips。

Faiild components so that the rest of the wafer is still working。Right。

 so that's actually you look at some of their very good question。

 very important when we actually get to this kind of large scale。

 way first skill discussion is basically the yield and how we have have built in fault tolerance into the discussion。

😊，So the last one I'll just briefly mention you may also hear already a lot of noise is this is like we talk about players right traditional semiconductor companies。

 startups now the software companies are also getting into the hardware and very good example is Google and in particular the generations of TU Tensor processing units that has been built and also deployed in their data center to support deep learning inference and training。

 so we'll see more of Google TU design。😊，Later， but this is another example how software companies start approaching this field。

So one final thing like we already talk about benchmarking the early imagenet effort that actually have a major impact in to actually compare different algorithm one thing we do want to communicate not only just a hardware front。

 but also we also need to compare different hardware。

 especially we talk about all the different hardware from all the different players in this field right how do we actually compare this so this is one of the major community effort that has started recently which has very big impact has a lot of very interesting if you go to the MPf。

org website has a lot of data you can actually see different submissions from different company for different applications and for different types of hardware that's they manufacturing。

 how they are compared against each other for the same application for either inference or training。

And how they are able to actually scale up to actually get better performance。

 So benchmarking is very important。 Even we're talking about hardware。

 we need to understand when you design your own hardware。

 you need to understand what hard applications to use and how how is your hardware compared against with others。

 right， So one of a very important effort and also we all of us benefited tremendously It is M perf effort to add some standardization in our area。

 we also talk a little bit more。 also have a guest speaker on this topic later in the semester。😊。

So we talk about this really excitement， all the different players in this field， right。

 but so we still need to get to you right， you are the focus of this class right with all the different buzz all the excitement。

 What do we actually want to do throughout this semester。

 What do we want to enable all of you to do here。😊，So in particular， what as I mentioned earlier。

 one of the major goals of this class is to really enable you as a builder so that understand those excitement。

 understand how the very complicated interactions of different components but think about from your perspective how you can actually potentially built better algorithm or better management or software infrastructures and also better hardware。

 all of those are connected like seen' question earlier on wafer scale right so it's a hardware problem we get to the scale。

 but there is also very important software software component to understand the fault tolerance and also manage the different components of the wafer so all of those algorithm runtime management and hardware are very important what we are really interested throughout this semester to really working with all of you。

how they are interacting with each other so that we can attribute better and more efficient system。

So by the end of this semester， what do we want to you all of you do really not only just as a machine learning user。

 not just as a machine learning developer， we like to enable all of you to actually of course。

 getting the different machine learning queries， different machine learning problems but really build either your optimizations。

 your management software management system and also very important in thinking about your potential hardware optimizations to get actually very interesting competitive performance。

 competitive energy efficiency， but also very good accuracy right all of those are very important but the centerpiece is is really you what you will be able to do on both algorithm front software front and hardware front so with that of course we like to introduce a lot of excitement and also general discussion about this。

😊，dutryBut as I mentioned earlier， theres lot opportunity that a small team and even just individual it's more like the earlier software development。

 a small team of engineers are able to actually achieve a lot。

 especially with some of the more recent tooling support and we hope all of you are able to leverage those support and to build your own system so that will be what we want to achieve and we want to enable all of you to do by the end of the semester。

😊，Any questions， comments before we get to the course information part。

 we'll talk about the general course structure， different components and different components of the course and the grading and the rubrics the general part。

Any questions and comments？But either the hardware front or the software front。Okay， well again。

 feel free to just unmute yourself and use the chat window to or just use emoji if that's your thing to give us some feedback so with that let's see we're going to talk about the course information。

 how this course work right， we talk about this ambitious goals， general directions。

 how does this course work。😊，So first on the staff front， I mentioned， I'm Sophia Shaw。

 I'm a faculty here and I'll be the course instructor for the throughout the semester。

 We have an it's amazing GSI this year， I'm very happy to have Abe on board to help us to navigate this semester。

 Ape， do you want to do quick just a brief introduction of yourself or your research and what you are looking forward for this semester？

 Sure， hopefully everybody can hear me So my names Abe or Abraham， whatever you prefer to call me。

 I am now a thirdy graduate student working in Kla Soovitch's lab， which is the De lab。😊。

And what was soda before cod I mainly work on hardware infrastructure as of right now。

 So this is the chipyard project if you've ever heard that term。

 but now i'm working on a chip so we have a chip that came back in lab and I'm working on that so my main research interests are in。

Designing for。Designing interesting chips that are low power and efficient。

I guess for general workloads。Yeah， and feel free to come by and talk to me。

 I'm available on email as well as on Piazza and during my office hours so you can always chat with me about you know Berkeley stuff or stuff related to the class。

Great， thanks Abe， also good luck to your trip Well Abe is busy testing his trip。

 he is also busy preparing the course material， so we are very grateful for Apes help Yeah although I list my office there I haven't been to my office for almost nine months at this point so my office hour will also be online So all the Zoom information you will find the lecture Zoom you'll see all the office hour Zoom information also on the course website so course website and PSA will be the place to look for any course related information。

😊，Oh。See。RightSo this is a website， we haven't seen that already。

 so this is a website E290-2 this is a spring 21 version you'll find and lectures and labs and project information we'll talk a bit more later and Piazza and we'll also use Griscopes for lab and project reports and we also do paper reviews I'll talk a little bit more that in a minute。

So in general， course organization will have two lectures per week。

 so 22330 Pacific every Monday and one thing I'm looking forward to interacting with all of you during that slot。

 I typically will be there at least two maybe even a little bit earlier。

If we just want to have a general discussion， we have a pretty fun discussion today about maybe forming a music band by the end of semester so but if you have anything youd like to either us just interact either with me or A or the rest of the class feel free to show up a two or or maybe even 150 I will start the zoom at 150 so so that we have a little bit more time to interact with each other I also mention we'll have guest lecture so far we are planning to do eight we already have quite a few already confirmed well also share more details when we actually sort out when and which week they should show up very soon。

😊，And we'll also have a paper reveal part， it's actually a little bit lighter。

 especially compared to last year， but I think having some paper reading。

 but having some paper reading experience is very important for both grad students and also undergrad students to get to see more。

 not only just what covered in the lecture， but also get to see a little bit more on the research front。

 some of the papers are more historical papers that actually on the major major breakthroughs in either the hardware or machine learning。

 some of the papers are more recent like just sharing some more recent technology or research development。

We'll have two office hours and we're also doing a pre semester survey we'll talk about that later if needed。

 we may also add more office hours to accommodate students from a different time zone we also have three labs typically two weeks per lab those are labs I will talk about the structure of the labs in a minute but those are actually very important I mentioned that students have different background some of more on the hardware front on the algorithm front both are fine you are the exact audience for this class but we do want to use the labs to actually both bring everyone on the same page but also get to see both the machine learning infrastructures and also some of the state of art hardware development part。

So that will be the three labs for the first half of the semester and then for the second half of the semester it will be more project oriented。

 the teaching staff will work with every individual student and also teams of students to come up with a research project that could be a good fit for this class and also get fit for things that you and your partners are interested there will be no midterms and and finals for this class or no exams。

 just labs projects， lectures and under ratings。The course topics will cover a pretty diverse set of topics from the basic of neural networks we will not cover go deep too deep into the machine learning especially on the algorithm front but we'll more discover like general principles what are the things that you should be aware so that you can actually as a user you can navigate the different machine learning infrastructures and and build your own model and also deploy your model onto the hardware we'll talk a lot of optimization。

 both hardware optimization and software optimization ranging from quantization， data flows。

 different ways of doing accelerators， mapping and also sparsity。

 we'll briefly talk about some of the more emerging， like remember the three components。

 data hardware and algorithm we'll be mostly focusing on the deep neural networks。

 but we'll also talking about some of the other more emerging network components。

We're also talking about like more advanced technologies。

 which is also very important and there is also very increasing commercial development in actually not using the traditional digital hardware。

 but actually using analog hardware for neural network processing so that will also be of interest for this class we'll cover a diverse set of topics ranging from both hardware and software with a core focus of understanding the principles of machine learning algorithms and also hardware for machine learning。

😊，I mentioned there will be readings so we typically have one required paper to read every week。

 it will be actually even fewer than that if there we have guest lectures will actually will loosen that requirement I think's we do have a very good mix of both undergraduate students and grad students and even grad students not not many grad students are actually exactly in the hardware or architecture field we have also grad students with all the different background right so it's great to have you all here Im looking for working with all of you at the same time reading papers navigating papers and it's very important skill for both undergrads and graduate students for undergrad it will be very different from the way you write it or navigate either a lecture or notes where you're。

Lb report， it's really trying to understand how they propose。

 how they figure out solve a research problem。 What are the available solution。

 What were the available solution before they started working on that。

 What's their unique insight to actually understand the challenges and how they actually work around。

 how they actually improve the state of the art So we'll also have some review questions to help you actually navigate the reading process。

 but for students， if we don't have a lot of paper reading experience， that is fine。

 that that's part of the class is' also trying to give you get you actually comfortable with both reading papers and predicting papers also very important for your longer term career。

 So that will also be part of the class。Second part is the lab and the project I mentioned earlier there will be three labs every lab will be like two weeks soll have two week to work on the lab but always start early so willll be three lab the first one is actually more focusing on the machine learning structure so getting you actually comfortable with playing with a machine learning framework the one we are using will be Pytor it's very easy to do if you have some Python experience it should be very easy to pick up and to help you navigate the space we design the quantization experiment that's also very important in a lot of hardware for machine learning discussion to also talk about that in our lecture and then you will be able to actually apply that in your first lab the first lab will be out next week so youll see the lab see the structure you have plenty of time to get yourself comfortable with the infrastructure and then it will be due in two weeks。

The second one is getting a little bit more closer to the hardware front。

 really designing we already give you a skeleton and then you will be designing a piece of the entire hardware specifically thinking about a particular processing element for machine learning excccelator you you have to use a verlock so that's part of the prerequisite。

 we'll also talk about that later if you also some of the students may also want to use Tsel if you Verlock is strongly recommended it is a lot easier but if you are comfortable with Chisel if you plan to use chisel feel free to reach out to the teaching staff so that we are aware that you're planning to use chisel but in this that the verylock is basically the language that we'll be using to design our hardware。

And the third one will get to actually using large scale FPGA based simulation to actually do some mapping experiment to actually we talk about the software and runtime。

 what's the im there， how can we actually improve the performance by understanding the hardware structures and also getting a better runtime performance。

So those are three labs covering very different topics and we hope this will actually set a solid foundation for all of you so that you are comfortable navigating the hardware for machine learning area and all the labs will be done solo so every individual student will be able to work on those labs feel free to reach out to both your classmates post questions on Piazza and also reach out to the teaching staff if we need any help so those are roughly the structure or the three labs。

😊，So after the lab will be done， we'll get to that's basically around around spring break around that time。

 So we'll get to the project phase。 So this is a great way to actually get involved in research。

 Some of you already reach out to us。 you're interested。

 especially using this class to get involved in research。 So this is a great way。

 And if youre graduate。 And this is also a perfect way to actually combine your own research topic to some of the topic that we discuss here to actually to extend it or adding another interesting dimensions to your research problem。

 So we'll provide hardware platforms for you to evaluate。😊，Research， your hardware。

 and this part we typically recommend to be done with a partner so looking for。

A partner for your class for for the project so that you can do a little bit more ambitious project it's also okay to do individual project if you feel like it's challenging to find a partner but if possible its still early on in the semester we' also try to organize some activities so that you get to know each other and the lecture is actually a great way to actually see each other so we recommend this project to be done with a partner。

😊，And we'll have a demo session during the reading week and the report will be due after the reading week。

Any questions？Okay so Ave already mentioned if you have any questions， feel free to post on PiA。

 this is a link， you can also find a link on the course website hopefully I don't need to talk too much about this basically this is a very open endeded class right all of you are you don't have to take this class right you are here because you're interested in learning more trying more things right so theres really no need to violate our guidelines here and there's no need to cheat in any way in any form so just really explore things right build your own things there's a brief grading breakdown so well have paper reviews roughly 10% labs will be 40% and project will be 50% so project and labs are very important We hope project can be a great way to actually get all of you。

involved in research we do encourage course participation either through lectures with Q and As either chat or just unmute yourself directly post questions on PiazA participating discussions answer your fellow students question right on PiA and we be using Geermini and tripyard to research infrastructure that we developed here you are interested and also want to contribute to the project all of those will also come towards actual credit in general this is just our encouragement to get all of you involved in research。

There will be seven late days we do want to be pretty flexible in general。

 you can see the details of late days on the course website。

 but basically you can use late days for any part of the of the class and for each assignment the maximum dateday you can use for each assignment is three and then you will exhaust all your late days。

 you will get a 10% points deduction for every actual days just like in case you have some emergencies you cannot finish on time。

 we understand this is a challenging time and you need any more help let us know we are happy to help in any form。

So prerequisite some of you already reach out to us just asking our prerequisite。

 The reason we have Xs151251A or CS152 there is because this is still a fairly hardware oriented class we need to have a basic understanding of computer architecture and digital logic design so that you can understand different tradeoff in the hardware space and very log experience is required that we mentioned like one of the labs will be using Milo and even in your project。

 you also be using very log if you have trail experience that's also good。

 but you need to be comfortable like designing hardware so that's why there is a 151 a 151 to51 a or 152 to52 a requirement if you have specific questions feel free to post on PSA or send us an email we are also happy to address individually。

So with that some things to get started we'll have paper reading will start next week lab one will also start next week every lab will be lab will release lab on Monday and you have had two day。

 two weeks to work on it and we be due the next Friday so two weeks or Monday Friday cycle if you're not on Piazza sign up on Piazza now we post most of our communication to the entire class will be on Piazza and if you have any questions also feel free to post your questions on Piazza。

I don't think you need the instructional server account right now you will need that for your lab too so keep eye on on that and if you can get that started that's also useful and the final thing like Abe already posted onPSaz and also post a link here we're doing a pre semester survey it's really just our way to see more of you understand what you're looking for and like what time zone you are what you want to get from this class what kind of information that you want both me and Abe know so that we can actually provide you it's a better experience so yeah just let us know it's fairly open endeded if you have anything in mind anything that you feel super passionate about or super excited about also share that with us in the pre semester survey。

So with that， this is the end of the first lecture great to see you all here。

 we have I guess one or two many if you have any questions feel free to post on the chat or Piazza or just onmute yourself。

😊，Any questions， comments for the topics that we discussed so far？Everythings a clear。😊。

So in that case， don't get back to us if you are unclear with some course policy。😊，Okay， it's okay。

 if you something come to your mind， feel free to reach out to us again。

 It's great to see you all here。 I'm looking forward to working with all of you in this fun semester。

 and I also hope all of you have a safe and healthy semester。 Great to see you here。 Stay Stay safe。

 Stay healthy and take care。 I'll see you next week。😊，By right， perfect， thanks。No problem。



![](img/fca11fc3022e0fc4a15a69b45a986428_3.png)