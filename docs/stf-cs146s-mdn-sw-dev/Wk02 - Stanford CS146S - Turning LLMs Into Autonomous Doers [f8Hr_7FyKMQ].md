# Wk02 - Stanford CS146S - Turning LLMs Into Autonomous Doers [f8Hr_7FyKMQ]

We rely on large language models for just about everything these days， right writing code。

 drafting emails， synthesizing complex research。 Oh， absolutely。

 But here's the fundamental challenge facing these incredibly powerful digital brains。

 How does a system trained exclusively on static data from the past。

 interact meaningfully with the real time dynamic world。 Yeah， things that change by the second。

 exactly like stock prices or， you know data that lives behind a secure API like your company'sjiraboard。

 It's the ultimate scaling bottleneck for modern AI。 I mean， they have truly vast。

 deep world knowledge。 but that knowledge is instantly dated The moment it's trained a moment it's trained。

 it only updates when they undergo another massive multimillion dollar retraining cycle。

 If you ask your LLM right now without any external help。

 What is the current status of my highest priority bug ticket or what's the latest Git commitit on the main branch It would have absolutely no idea。

 It's trapped。 It's in a version of the world。That only existed when its training data was collected right and to build truly autonomous AI agent the doers that can manage our workflows。

 check the weather or run diagnostics we need robust standardized and secure ways to feed in that dynamic realtime information We need reliable tool calling and our capabilities that don't break the bank or introduced a ton of security vulnerabability exactly but historically connecting every single LLm let's call that applications to every external data service API or database well call that end services It meant building an M by mess of custom integrations every one of those connections required unique code for API access you knew it off schemes unique error handlers and unique data format conversions It was a fragmentation and maintenance nightmare I remember dealing with that headache 18 months ago it was truly by misery developers were constantly just writing boilerplate code to shuttle data between the。

In the actual tool the search was on for a single standard to cut through all that complexity and that standard is the solution we are deep diving into today。

 the model context protocol orP It's an open protocol designed specifically to allow systems to provide context and expose tools to AI models in a generalized uniform manner So it replace that custom fragmented and costly by system with something much much simpler and system which brings us to our analogy ofP as the universal adapter for AI agents It's really positioning itself as the usB of the AI world is instead of meeting 50 different proprietary connectors for your LL to talk to Github Spe and Postgres you just need one standardized plug the it just drastically reduces friction across the entire ecosystem So our mission today is to unpack this standard for you're going look at the core architecture and the specific mechanics of the communication and explore the massive and rapidly growing。

System of specialized MCP servers that have popped up and fundamentally understand how this protocol tackles the nonnegotiable enterprise requirements of security and true interoperability Okay let's jump into the core mechanics What exactly is an MCP server and how does it execute these digital tasks so at its heartP is an open standard that emerged just before the end of 2024。

Its stability comes from its foundation。 It's built on J RRPC 2。0 Jason RC 2。0。

 That might sound a little old school to some developers。 Why that Well， it was a strategic choice。

 It's all about reliability and simplicity。 Jason RC ensures the communications are purely request response。

 High predictable and easy to parse， which is absolutely critical when the ultimate recipient is a language model that just thrives on structure。

 right makes sense。 But what's fascinating here is that it takes successful concepts from the software dev world specifically the language server protocol or LSP。

 and extends them。 but unlike LSP， which is usually reactive right。

 it waits for you to type code exactlyly MCP is designed for proactive agent workflows。

 This means the tools can actually drive the conversation forward based on what the agent's goal is。

 to understand how this conversation happens。 We need to nail down the terminology。

 There's kind of a cast of characters in this handshake。 There is First， you have the host。

 This is the application where you， the user are actually interact。

So think of sophisticated AI code editors like cursor or maybe desktop app for Claude and inside the host。

 there's the MCP client right， which is the library embedded locally This client is important because it maintains a stateful session for each connection it opens with a server Okay next up is the MCP server This is the crucial intermediary the wrapper It's a lightweight piece of software built right in front of the actual tool or data source or API。

And then finally， you have the tool itself， which is just the underlying function like the actual Git pull command or a complex SQL query。

 exactlyactly the thing the AI model can ultimately invoke。 Now。

 let's walk through that core interaction using your example of running a Git command。

 How does that flow work， So it begins when the client calls a method usually tools list to the MCP server。

 It's basically asking， hey， I'm running a Git agent， what can you do for me right now。

 And the server responds， I'm guessing with some kind of structured data， a structured Json payload。

 Yeah， it describes every tool it offers， It'll have the tool name say， Gitbra status。

 a quick summary and the full Json schema defining all the inputs and parameters。

 The host then takes this list and injects that tool definition into the LLM's context。

 probably in the system prompt。 Almost always， So when you ask the query。

 what is the status of my current branch。 That prompt triggers the LLM。

 It realizes it can't answer from memory。 And so it ams a structured tool call， right。😊，LOM says。

 I need to call the get branch status tool。Maybe with some arguments。

 that structured call goes back to the MCP client， which translates it into a precise MCP request for the server。

 And here's where the abstraction really pays off theP server executes the underlying gift function。

 it handles the API keys or credentials runs the operation and then returns the structured result in a Json response back to the client and the LM agent never has to handle or even know about the secrets。

 That security layer is completely abstracted away by that server client relationship It's a beautifully clean secure and repeatable loop。

 and that modularity makes deployment incredibly flexible developers can build these servers in pretty much any programming language they want right Python typescript go Java whatever as long as it can talk Json R the requirement is minimal So how does that communication actually happen。

 what are the transport layers The most common one is studio standard input output that's usually for local processes running side by side。

 But for true remote communication which you need for cloud。

AI agents MCP supports servercent events or SSE SSE Why not just you know standard HTTP polling because SSE allows the server to continuously push updates and maintain that stateful session without the client having to constantly check in so for long-run processes like a database migration exactlyact the server can proactively send updates back to the client using that SSE channel maintaining that crucial continuous context rich interaction that flexibility and standardization coupled with being language agnostic has clearly created a massive surge and tools it is exploded which brings us right to the ecosystem the reference implementations from the MCP steering grve alone show the incredible range you've got servers for general data access like everything and fetch for web contentEssential utilities like time right and def functional servers for file system access get operations and even memory servers that act like knowledge graphs and when you look at thirdpart offerings。

Especially in the enterprise space， the scale becomes immense Off integrations exist for major developer tools We're talking at Lassian for Jra and confluence Github Cloudflare payment platforms like major data platforms like Postgreql Mongodb databricks or even highly specialized servers that wrap AWS and Azure services beyond the official enterprise tools the community servers really show the breadth of what this protocol unlocks the barrier entry is so low that people have quickly up servers for domains you might not have expected to be AI enabled this fast what I mean servers for blockchain platforms like finance and salla gaming integrations fores browser automation with playwright and even specialized data sources from governmenting is like NASA or servers focused on niche fields like Brazilian law ones wild So that explosion of tools is great but if anyone can build a server in any language how does an agent or developer find the right one it sounds like a new kind。

Fgmentation a discovery nightmare and that's the exact problem the model context protocol registry solved when it launched in September 2025 the registry It whole purpose is to be the official centralize and open catalog and API for all publicly available MCP servers it standardizes discoverability moving beyond just simple keyword searches So this registry acts as the primary source of truth and other public marketplaces may be integrated into ID or even private enterprise subregistries can build on top of it precisely it ensures everyone is looking at the same trusted list and crucially this centralization allows for community drivenn moderation so they can as bad actors the registry has a clear mechanism to denial servers that violate guidelines if a server has malicious code or tries to spam or violates licensing it can be retroactively removed from public view it enforces a baseline of trust so let's look at a practical application the Cloudflare deployment。

Guide excerpt in our sources is a great example of how simple this is for developers。

 It is The guide highlights the practical reality of deploymentDevelop usually have two main paths on these serverless platforms。

 They can deploy a server without authentication， which is fine for public。😊，General tasks。

 or more commonly， they deploy it with authentication and authorization。

 Meaning the user has to sign in and permissions control exactly which tools an agent can call。 Yep。

 which is key for enterprise security。 The streamlining is massive。

 You get a live server often at a workers dot dev a subdomain that any MCP client can connect to immediately。

 That reduction in friction is the core driver of adoption here。

 That brings us to the most critical layer of all security。

 because while the functionality is robust， The sources highlight a pretty significant early limitation of the protocol that need it to be fixed。

 It did。 Let's talk about that early security hurdle。Their early MCP implementation。

 so up until late 2024， early 2025。They just lacked a truly standardized， robust off mechanism。

 So it was this genius protocol， but it was hampered by a single point of failure credential management。

 What did that look like in practice In practice， it meant that for secure operation。

Develop were often forced to run their servers locally alongside the client。

 which kind of defeats the purpose of cloud agents。

 it totally does or they had rely on manual out of band provisioning of sensitive credentials like API keys directly to the remote server。

 So if you wanted a cloud agent to securely access your Github repo。

 you had to manually upload your Github token to that server instance。 Yes。

 which simply does not scale for secure remote multiuser access in a sauce environment。

 If you have 10000 users who want to connect their individual credentials to a single shared agent。

 manualual key handling becomes impossible and incredibly dangerous。 right。

 So that problem was severely hindering MCP from reaching its internet based multi tenant potential precisely。

The solution， which was adopted really rapidly by the community， was integrating O youthuth 2。

0 as the secure scalable standard for authorization and the adoption of Outh 2。

0 just changes the game entirely。 It provides features we take for granted in modern web dev like dynamic client registration and automatic endpoint discovery。

 which cuts down on configuration overhead。 but most importantly。

 it ensures secure authorization and token management。 That's the key。 It means you。

 the user authorize the agent once via Ooouth， and the system guarantees that the MCP client can only access the specific resources you explicitly permitted within a defined scope using shortli tokens。

 This finally brings proper modern security and compliance to cloudhosed MCT agents It does。

And this standardization is really the aha moment when you compare MCP to older approaches。

 like comparing it to building custom integrations from scratch。The benefit is obvious。

 MP replaces all that manually written brittle code with a single reliable plug play protocol。

 And what about compared to the much hyped chat G plugins that we saw earlier in the AI wave。

 Well pluginins were proprietary。 They were tied to a single platform。

 and often they functioned as singleshot calls。 You called the API got an answer and the interaction ended。

 There was no deep session context。 whereas MCP conversely is an open standard。

 It fully supports those continuous context rich two way interactions through that stateful session。

 and it now has that unified， secure O youth standard。

 It's a fundamental architectural upgrade from those early proprietary plug models。

 so final comparison， let's address existing LLM tool frameworks like Lang chain。

 We know these frameworks let developers implement tools。

 What's the clear demarcation line between a framework and a protocol。

 That's the most important distinction for our technical listeners。

 Lang chain and similar frameworks provide a developer facing standard for tool implementation。

 You define your tool logic and Python using their wrappers。😊。

MCP is a model facing protocol that enables dynamic tool discovery at runtime。

 So if I'm running an agent， that agent doesn't even need a compile time dependency on。

 say the specific Postgres driver or the Github Not at all it just needs to know the location of a reliable mP server that wraps those tools So an agent using MCP can literally discover and use a completely new tool like that one for Brazilian law data without the agent's core code needing to explicitly include it beforehand exactlyactly it decouples the agent's logic dependencies from the tools availability and implementation that is the definition of true scalable interoperability So what does this all mean for someone looking to build AI applications or just understand where the industries go It means the model context protocol is the standard that successfully transitions AI assistance from being these siloed geniuses restricted by static knowledge to becoming well equippedqui integrated engineers that can securely access and act upon the entire。

world data and external services by standardizing that communication layer。

 it just reduces integration friction so dramatically it makes AI systems inherently more scalable across every single industry It sounds like the plumbing problem is largely solved。

But the sources do hint at a potential roadblock still ahead， centered not on the tool communication。

 but on the LLM itself。 They do， despite the massive success of MCP in standardizing the delivery of information。

 certain LLM limitations still exist。 Today's models。

 they don't handle a huge number of available tools very well。

 Their reasoning can degrade when they're presented with too many options。 and critically。

 the results return from Apis， even beautifully standardized JsonN results can still quickly overload the LLM's context window if they are too verbose。

 That's huge one。 This raise an important and I think provocative question for you， the developer。

 the entrepreneur or the curious learner listening，  moving forward。

 must developers design apis themselves to be truly AI native meaning simplified summarized or highly curated datas。

 exactlyact， rather than simply exporting rigid legacy interfaces in order to maximize the full long term potential of standardized protocols like MCP。

 they transition from legacy interfaces to。AI optimize data endpoints。

 I think that's what the next era of innovation is likely to be found。

