# Wk09 - Stanford CS146S - Agents Post-Deployment [zbWWTUM0O2E]

Welcome back to the deep dive。 You know， if you've ever had an app just freeze on you or a website go down。

 you've seen what happens when a complex system fails。

 We tend to forget that these huge computing systems， the ones running， I don't know， banking。

 all our communications。They don't actually run themselves。 Not at all。

 And as the old operations folks used to say， probably a three in the morning。

 hope is not a strategy。 precisely。 and hope is a really。

 really poor strategy when a crisis is costing your company millions of dollars a minute。

 So our mission today is to really dig into the evolution of how we manage these massive systems。

 We're tracing this this huge philosophical shift from the old way of doing things all the way to what's coming next。

 we'll start with that traditionalssadmin model， then move into site reliability engineering or Sre。

 which Google pioneered。 and then look ahead to this emerging world of AI native engineering。

 All right， let's unpack that。 So we're starting way back where the traditional systemsmin model。

 This is where you had system administrators and their job was basically what to care for and feed the software。

 That's a great way to put it。 they deployed the code that developers wrote。

 and then they were completely on the hook for keeping it running。 and that just。It couldn't last。

 No， it was fundamentally unsustainable。 It had this huge direct cost problem as the service got more complex or as traffic grew。

 the number of alerts， manual fixes all of that。 It just scaled up right along with it。

 So more complexity meant， you had to hire more people。

 exactlyact the size of your ops team had to grow at the same rate just to you know keep the lights on。

 It was a guaranteed costs spiral。 But the sources we looked at。

 They really emphasize that the direct costs， that wasn't even the worst part。

 It was the cultural damage。 They call it trench warfare。 That phrase is perfect。

 it just perfectly captures the conflict。 because you have developers who are rewarded for one thing。

 launching features fast。 They want velocity。 They want velocity。

 and then you have the ops teams who are rewarded for stability。

 Their goal is making sure the pager never ever goes off。 And since most outages come from a change。

 their goals are in direct opposition。 completely， and you can just picture the tension， right。

 The ops team， they've been burned before。They create these incredibly rigid launch gates they're checking for every single problem that ever caused an outage in the past which makes the checklist impossibly long and slow and so the developers。

 what do they do they learned to get around it they start pushing updates through back channels instead of a big launch it's a subtle flag flip or an incremental update something that can fly under the radar exactlyact something that bypasses that whole painful review process So now you have everyone gaming the system stability is at risk and nobody trusts each other So something had to give and that's something was site reliability engineering what was the core idea from bejamin Traer slotlo at Google The premise was actually incredibly simple but it reframed the entire conversation it was just。

What happens if you ask a software engineer to design operations team you immediately start seeing operational problems not as manual work。

 but as software problems that can be solved with code and you can see that reflected in who they hired for these SreE teams right they weren't just networking experts they were coders first absolutelyutely the sources say in SreE team is 50 to 60% actual software engineers。

 the rest are you know people with deep technical skills like UNIX internals or networking。

 but who also have to have a really strong aptitude for coding So the philosophy is don't just do the task right software to do the task for you。

 Yes， and the goal is to build systems that are automatic not just automated。

 it's a subtle but really important distinction。 that distinction is key because it leads us right into the core SreE principles that stop that trench warfare and it all starts with this rule about manual labor。

The toil threshold This is， I think， maybe the most impactful reform in modern operations。

 Google puts a hard nonnegotiable 50% cap on what they call ops work for all Ss and ops work is tickets onca stuff It's what they call toil's manual's repetitive its tactical it's work that doesn't require creative engineering thought So yes tickets manual run books on call duties which means the other 50% of their time has to be spent on durable engineering work building automation improving the architecture essentially engineering their own jobs away but the rule is one thing the enforcement is what sounds like pure genius is because if that operational load that toil goes over the 50% mark the excess work gets shifted right back to the development team that wrote the unstable code So suddenly the developers of the ones holding the pager suddenly they're the ones getting woken up at 3 aow so you're telling the list。

That if they build a system that's flaky。While they get to deal with the consequences themselves。

 It creates this incredibly powerful immediate feedback mechanism。

 It forces developers to think about stability from day one because they are now the primary consumers of their own systems instability。

 The pain goes right back to the source。 Okay， so that's the first pillar。

 The second one and maybe the most famous is the error budget。

This seems to be the thing that directly solves that dev versus ops conflict。 It does。

 because it introduces a shared currency for risk。 And it starts with this really profound idea。

100% availability is the wrong reliability target for basically everything。

 except maybe like a pacemaker or something。 Exly pacemakers， Antilock breaks。 Sure。

 but for a web service， striving for 100% is a waste。

 the users' experience is already limited by their wfi， their cell provider， the global DN S。

 So the tiny gain from， say 99。99% to 99。999， and is invisible to the user。

 but incredibly expensive for the company。 extremely expensive。

 So the availability target becomes a product question， not a technical one。

 what level of reliability makes our users happy， right， And once you have that target， say 99。99%。

 The error budget is just the leftover part。 It's just a reminder that  point01% is your budget for downtime for failures。

 and the cultural shift is huge， the goal isn't 0。Outages anymore。

 The goal is to strategically spend that budget。 you spend it on taking risks on launching features faster。

 Yes outages become an expected part of innovation。

 and both teams are managing risk against that shared budget So shifting gears a bit to when things do break S also really formalized incident response I noticed a heavy focus on to repair why so much focus on repair because in any complex system failure is just it's inevitable can't engineer away all risk。

 So your ability to recover quickly is the one factor you can reably control that makes sense I mean a system that fails a but recovers in a second is actually more available than one that fails once a year but takes five hours to fix and the sources gave us a really clear metric on how you lower that it's all about preparation100% The data shows that having prewritten playbooks the step by step guides gives you about a three times improvement in repair time compared to engineers just winging it under。

It gives them a path to follow when everything is on fire。 Exactly acknowledge the alert。

 Check the usual suspects like databases or recent changes contain the blast radius and so on。

 And they also put limits on the alerts themselves to stop people from burning out。 Yes。

 this is huge。 an SR on call should get a maximum of just two actionable events in an 8 to 12 hour shift That's it。

 That's it any more than that and you get alert fatigue。

 people just start ignoring the pages because it's all noise。

 you need your alerts to mean a human must intervene right now。 then after the incident。

 the learning is critical。 That's a postmortem。 And this is non negotiable。

 It has to be a blamefree culture。 The second you start pointing fingers。

 people stop reporting the near misses。 they hide information and the learning stops cold。

 The focus has to be on fixing the system not blaming the person。

 So SR was this massive leap forward。 But now we're in the cloud native world。

And the sources suggest that even Sres are hitting a new kind of complexity wall。

 This is what we're calling the modern Sre burden。 We said earlier that coding is maybe 30% of an engineer's time。

The really hard part， the other 70% is running that code in production。

 because today's systems aren't just one big block of code。 Not even close。

 Their microservices spread across multiple clouds managed by Kubernetes talking through service meshes。

 The amount of knowledge you need to debug one single user request has just exploded。

 You could have 10 different teams's code involved in one transaction easily。

 and resolving an incident means trying to piece together fragmented clues from， you know， logs。

 metrics， traces run books Slack chats。 and all this tribal knowledge that losing people's heads。

 The sheer volume is just too much for a human under pressure。

 And this is where modern observability becomes the absolute bedrock for whatever comes next。 Yes。

 for any system， human or AI to manage this complexity。 It needs good data。

 And that starts with traces and spans。 Let's define those。 A trace is。The whole story。

 a trace is the whole story， a user clicks by and the trace follows that single request through every microservice。

 every database every cache it hits from start to finish and the spans are the individual chapters in that story。

 Perfect analogy。 Each span is one unit of work。 the database query， the call to the payment gateway。

 and it has timing data and other context like which user ID or deployment version was involved。

 So you can see instantly where the bottle I is， which service took 800 milliseconds。

But you still have this context problem。 The human still has to connect all the dots。

 and that's the killer。 an investigation requires you to do all these things at once。

 Look at the trace timing。 Correlate that with a metrics graph over here check the database connections scan the off logs and compare all of that against recent deployments no one person can be an expert in all those things and do it in under a minute which sets the stage perfectly for the final shift for talking about from human centric Sre to this AI native era and we need to be clear this isn't just about fancier dashboard No this is a fundamental paradigm shift。

 It's the difference between AI assisted and AI native in the AI assisted model the engineer is still in charge they use the same old tools but maybe an LLM helps them write a log query faster the workflow is still human centric but in the AI native model that flips the engineer talks to AI agents exactly they use natural language instead of digging through data you just say resolve this checkout failure and the agents take over the whole multi。

Investation and this has to be a multiagent system right a single AI can't do it all right single As fail here because of what academics call irreducible interdependence。

 you can't build one model that's an expert in 50 microservices and database deadlocks and infrastructure logs it's just too broad So instead of one brain doing everything one step at a time you have a team of specialist agents working in parallel。

 a database agent， an intraag， a trace agent， an alert fires and they all test their own hypotheses at the same time converging on the root cause way faster than any human could The sources call this new thing an AI production engineer。

 It's not just a tool it's a proactive system it is it starts by building its own understanding of the system a dynamic knowledge graph mapping code infr tools everything that graph is its brain and when an alert fires It doesn't wait for a human It responds autonomously it creates what you could call just in time run books tailored to that。

Spific incident it analyzes all the data metrics logs recent code changes in under a minute and comes back with a high confidence theory about the root cause it learns it captures that tribal knowledge this is crucial it watches how humans solve new problems and updates its own knowledge so run books never get stale it's designed to take on that 70% of operational grunt work the log queries the evidence gathering so humans can finally focus on creative work on system design and architecture it's an incredible arc when you lay it all out from manual fist to rule-based Ss with their 50% caps and error budgets and now to autonomous knowledge-dven AI agents and the promise for you the listener is getting that 70% of your engineering time back it's about having systems that give you consistent evidence backed and fast investigations which massively reduces the stress of being onca we get to move from being firefighters to architects but this can't be a silver bullet despite all these advances。

What are the limitations we should be thinking about as we move into this AI native world There are two big ones First。

 the AI is only as good as the data it gets if you're underlying monitoring your logs， your metrics。

 your traces is incomplete the AI can't magically find the answer Good monitoring gardening is still absolutely essential garbage and garbage out that makes sense and the second one The second is that by giving AI agents this much power and control over production。

 you're opening up an entirely new security attack vector absolutely when these agents can execute changes and make decisions on their own。

 we have to think very， very carefully about the security。

 the auditability and the safety controls around them that is quickly becoming the next great challenge of the AI native era it's a tradeoff I power for a fundamental shift in control。

