# Wk04 - Stanford CS146S - Coding Agent Patterns -NRBLfDOL_vg-

Programming is at a dramatic inflection point。 I mean。

 if you look back at the history of software development。

 we went from those heroic solo developers to large specialized teams。

 You have driven by projects like those at NASA and then around 2023。

 we hit the era of AI assisted coding。 We learned how to code with AI。

 And we are now entering the next even more radical phase。 This is Crca 2025。

The core role of the developer， it just shifts entirely。

 How so it's no longer about a single human writing code or you know collaborating line by line with a tool like copilot。

 It's about a single developer managing the output of many highly autonomous AI agents So you're not a coder anymore。

 Youre transitioning from being a coder to being an agent manager。 exactlyact。

 and the sources we pulled for this deep dive。 they really focus on the tools making this happen right now。

 specifically a tool called Clade code。 It's presented as a lowlel kind of unopionated command line tool for this agent coding。

 It's flexible。 which is great。 but to turn it into a high productivity platform。

 you really need a system。 and that's our mission today。 This is for you。

 the future agent manager to understand the new meta skill that's required to succeed here。

 and that skill is context engineering。 We're looking at how developers who master this are seeing objective and subjective productivity gains of up to two and a half times compared to traditional development。

 That's a huge。It is And the core insight from AI nativeative places like stock app is that the whole metric for success has changed Good code is now just a side effect of good context that 2。

5 x leap is mean it's almost unbelievable but the data seems to back it up It does stock app for instance reported their developers were pushing something like 10。

6 successful pull request per person per week the industry average is closer to one and subjectively they reported those productivity gains at around 2。

5 times better than manual coding and crucially about two times better than companies that just bolted AI tools onto their old processes so why to understand why that leap is possible you have to get this paradigm shift do we've all been so focused on prompt engineering writing that one perfect instruction but that completely fails when you have an autonomous agent trying to execute a multistep plan So what's the new challenge。

The core challenge becomes context engineering It's about defining the system's entire knowledge base。

 setting behavioral constraints and you know establishing guardrails so the agent can run on its own without causing a lot of damage exactlyact without causing collateral damage the sources really emphasize treating your code repository your Monrepo as this shared workspace for both humans and agents which means that natural language artifacts。

 things like design docs， project plans， architectural guides they're suddenly just as critical as the code itself you're soing the pantry for the agents they need something to feed on right so if we look at how this actually changes the development lifecycl。

 it creates this progressive hierarchical workflow a top-down workflow that builds context continuously it starts with the human as the architect the human defines the high level business requirements the goals Yes and from there the human delegates The first delegation is typically to say a design agent。

hi then drafts the detailed design document based on those requirements。

 So what's the human's role after that Are you just hands off until the code is done Oh。

 absolutely not， the human must review that design document for correctness for feasibility only after a human signs off does the agent moved to the next step。

 converting that design into a series of tasks， the implementation plan and that review gate is essential It is because fixing a flawed design is vastly cheaper than fixing flawed code way down the line。

 So after the plan is approved， the agent implements it writes the code。

But the sources stressed this crucial step they called the backstop The backstop is it's non negotiable in agenic development。

 Asians tend to solve problems locally， but they can break unrelated systems because they have limited contextual vision so the tests of the guardrails tests and safeguards have to be created extensive。

 committed， failing tests。 they act as the critical objective constraint。

If the agent can't pass the existing test suite， it simply cannot commit its code and then the loop closes with review and update This is where the agent manager audits the feature。

 but also make sure the agent update all the surrounding documents The living design docs， the Sude。

Md files， the schemas so that the next agent to work on the project inherits a perfect accurate context It's a continuous self-improving system and that continuous flow is what unlocks that 2。

5x gain Okay so let's unpack this if context is the currency how do we actually create and manage that within a tool like La code The central mechanism is this special file called Kiawde。

m。You should think of this as the agent's personalized instruction manual for that specific repository Clade code automatically pulls this file into context at the very start of any session so the agent's first thought is shaped by those constraints So it's the perfect place for project specific rules not just what to build but how to build it Ex things like core utility functions build processes how to run the test suite precisely you can document common bash commands。

 specific repository etiquette or any you know non-standard behaviors you want Claude to know about and it seems pretty flexible。

 it is you can place this file in the root or in parent or child directories which is critical for managing context in these huge monorepoos you can even generate a starter file really quickly using the init command So if this file is this constantly refined piece of engineering how often do teams actually dedicate time to maintaining it what happens when it drifts out of sync with the code。

That is the primary challenge for the agent manager。 It has to be treated as a first class citizen。

 just like your infrastructure as code。 So what do you do Teams often automate the maintenance。

 or they designate specific agents to audit the documentation periodically。 when it drifts。

 the agent relies on outdated assumptions。 and that leads to incorrect tool usage or you know。

 code that gets rejected。 and you can enforce it。 Yeah， to enforce adherence。

 teamss often run these cloud EMD files through a prompt improver， or more simply， they add emphasis。

 Things like important or you must to ensure the agent gives those instructions maximum weight。 Now。

 let's pivot to control and safety。 This tool is operating directly in your terminal。

 It can write files， it can execute bash commands。 That's a little scary。 It can be。

 and this is where the inherent conservatism of Clade code comes in。

 It requires explicit permission for any system modifying actions。 That's its gatekeeper functions。

 will ask for approval By default， yes。It will ask before writing a file or executing a command。

 So as the agent manager， how do you manage that friction when you want to delegate a large but safe task。

 you manage permissions， you can use the permissions command or edit the settings files directly to preapprove certain actions what for example。

 allowing edit lets the agent modify files on its own。

 or you can get really granular with something like bash get commit Oh， that's interesting。

 It allows the agent to commit code without constant supervision， but restricts it from accessing。

 say sensitive production tools， that granularity is just critical for safety。 and speaking of tools。

 it inherits your bash environment， but if you have custom Ci tools。

 say a proprietary deployment script。 The agent won't know it exists right unless you explicitly tell it about them or ask it to run the help command on that tool。

 That's right。 The agent needs documentation for your local infrastructure。

 you can also extend its capabilities using something called the model context protocol or MCP to。

Integrate external systems like specialized testing frameworks。 Okay。

 let's move into the actual daily work。 The successful workflows that are defining this new era。

 The first one is explore， plan， code， commit。 This is especially for nontrivial problems And this workflow is all about managing computational resources strategically。

 So you tell it to read all the files。 But you explicitly tell it not to start coding yet。

 Then you ask it to form a plan。 This prevents the agent from rushing into some shallow suboptimal solution。

 and this is where those trigger phrases come in。 Yes， think， think hard or even ultrathink。😊。

These phrases signal the model to allocate a progressively higher computational budget for planning and evaluation so you are literally paying compute for more thorough internal deliberation exactlyact it's a great way to force the system to analyze implications before it starts writing code you might just have to throw away Another powerful pattern is test driven agent development or TDD。

 This is highly effective。 Claude performs best when it has a clear objective constraint to solve against It's so interesting that we're instructing this this noncensient system to fail first Is that the secret giving it a clear objective to solve for It is the goal is certainty。

 The workflow dictates instructing Clade to first write comprehensive tests。

 you confirm these tests fail， you commit the tests。

 then you instruct Clade to write code only to make those committed tests pass It just iterates until the suite is green。

And that gives the agent manager total confidence。 To confidence in the output。

 And for front end or visual work， there's the code screenshot result， Iterate workflow。 right。

 You give Clade visual targets。 Maybe you drag and drop a mock up image into the terminal。

 Then using tools like the Paeteer MCP。 Claude can take screenshots of its live implementation and iterate the code until the visual result matches the mock。

 and that iterative refinement is so critical for quality。

 The output often improves significantly with just two or three cycles。

It mirrors how a human designer polishes their work， but at machine speed。

 this brings us to where the truly revolutionary gains are happening， specialization and ensembles。

The multi agent workflows。Why do single agents underperform if they have all the context single agents。

 they sort of struggle to separate context effectively for different roles a single agent trying to be the coder。

 the reviewer and the tester all at once will get confused so you need a verification loop that's why the verification loop is so crucial you run two parallel instances one Claude writes the code and a second Cla or even a different LLm via an MCP server like Gemini is designated solely to review or test that output separation of duties and we have real worldor proof of this we do Stockap found that when they ran this loop the second model Gemini in this case was significantly better at preemptively finding security issues and subtle bugs then the Cla instance that wrote the code and if you have truly independent task on the same repo developers are using tools like Git work trees which to put it simply allows the agent to check out isolated workspaces of the code at the same time without interfering with the main branch it enable。

True parallel execution the complexity of managing all that manually must be huge It's prohibitive and that's why we're seeing the rapid rise of these metaprogramming frameworks that automate the orchestration superC it provides a configuration layer with dozens of commands and specialized agents like a PM agent for ticketing or a deep research or look at the awesome sets up an entire orchestrated AI development2 tech lead orchestrator a code archaeologist The framework automatically detects the reos and configure the optimal mapping right into your claw It's abstracting away the management complexity So the agent manager can focus on the highleve goals What stands out to me most though is how this is flowing through the entire organization not just course software teams that's where the aha moments are happening absolutely Let's look at the data infrastructure team's experience。

 This is a complex systems task。Kubernetes cluster started failing。 It was a crisis。

 They didn't have time to wade through logs or wait for the networking specialist Instead they fed screenshots of the dashboard and error logs directly into cloud code。

The visual context， combined with the agent's ability to analyze system configuration。

 allowed it to diagnose the problem instantly， which is what a subtle I P address exhaustion issue on a specific pod。

 More importantly， it provided the exact bash commands to fix it completely bypassing the need for a specialized human。

 That's phenomenal。 So infrastructure issues with a screenshot。 It really is。

 And on the other end of the spectrum， you have growth marketing。 a traditionally nontechnical team。

 A single team member there built an agent workflow using two subagents， one for headlines。

 one for descriptions。 They generated hundreds of varied Google ads variations in minutes。

10 times the creative output， which enabled exponentially faster A B testing and iteration。

 and the story from legal team is just remarkable。A nondeveloper built a functional。

 predictive text accessibility app in one hour for a family member with speaking difficulties。

 It just validates the potential for nondevelopers to achieve really meaningful results by being an effective agent manager。

 We're also seeing it in highly technical areas， like security engineering。

 they reduced incident resolution time from what 10 or 15 minutes down to 5 down to about five minutes。

 Yeah， just by instructing Clade to trace control flow through stack traces。

 and for product designers， implementing large state changes or turning a mock up into a prototype is now two to three times faster。

 So what does this all mean for you， the developer who is now the agent manager。 The key。

 it seems is iteration and specificity。 You need to treat Claude as an iterative partner and course correct early and often。

 The success rate drastically improves with specific instructions， not just vague intent。

 And you have to manage the process actively。 You mentioned course correction tools。 right。

 you always enforce a plan before coding。But if the agent starts going rogue during a tool call or a file edit。

 you can hit the escape key to interrupt it immediately and redirect its plan so you have direct control you can even double tap escape to jump back in history and edit the prompt you just provided that level of managerial control is what defines your success the ultimate takeaway here is that the developer's core skill has shifted from coding syntax to managing complexity。

The job is defining context， managing agents and auditing their work。 It is。

 We've seen how AI increases productivity exponentially。

 But given the immense power and the potential blast radius of agent mistakes。

 The deepest expertise you hold your domain knowledge。

 the business rules is now required to define the rules set and audit the work。 So you。

 the agent manager need to be thinking six months out。

 your building systems for a model is going to be exponentially more capable to mor。

 what context and what definitive safeguards， what specific K L A E D M D files and robust T DD patterns where you put in place today day to ensure quality When the agent you manage becomes that much faster and more autonomous。

 That's the work that requires your deepest human expertise。

