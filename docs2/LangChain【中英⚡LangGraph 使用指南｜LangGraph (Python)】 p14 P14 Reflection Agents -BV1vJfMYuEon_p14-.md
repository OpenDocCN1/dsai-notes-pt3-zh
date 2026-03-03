# LangChain【中英⚡LangGraph 使用指南｜LangGraph (Python)】 p14 P14 Reflection Agents -BV1vJfMYuEon_p14-

Hi all， this is Will from Langchin。 Today I'm going to be talking about reflection if you've ever been building an agent and found that it gets caught repeating itself or isn't making strategic decisions then this video is for you。

Reflectction is a common technique used to improve the quality and success rate of agents in similar AI systems It involves prompting an LLM to critique and improve its past actions sometimes based on additional external information such as tool observations or other observations from the environment while it typically adds a bit of additional execution time it can boost overall performance so if your application permits I would recommend you use it。

😊，If your application does not permit， you can use this technique to generate additional fine tuning data and shift the computation left to improve your performance without impacting the inference all right so for our first example。

 we'll do a super simple reflection graph here we basically will prompt an LLM to generate an output and we'll take that output and then prompt another LLM to roleplay as a teacher and provide reflections and criticisms so that the model can improve the output it repeats at a fixed number of times and then returns the final result to the user。

😊。

![](img/f072338922859166405c22985cba8c16_1.png)

![](img/f072338922859166405c22985cba8c16_2.png)

![](img/f072338922859166405c22985cba8c16_3.png)

Hopefully， based on this series of improvements， it will actually generate a better artifact at the end than the original shot there。

 So we first will set up our connection to the LLM with these API keys and we'll set up tracing so that we can reproduce a number of these results later if we want to be improving the prompt。

 we can see exact sequence of steps that were made in Lsmith。 and then without further ado。

 we'll define our generators。 The generator here， we just take a simple prompt template。

 and then we have this LLM。 in this case it's an open source mixtureal model developed by myal We'll create that。

 and then we'll ask it to generate an essay about the little prints。

 So we can see it generates a number of paragraphs here。 It follows this style。

 and it seems pretty good as at first sight I'm not going to read into it too closely because we don't have time。

😊。

![](img/f072338922859166405c22985cba8c16_5.png)

![](img/f072338922859166405c22985cba8c16_6.png)

![](img/f072338922859166405c22985cba8c16_7.png)

![](img/f072338922859166405c22985cba8c16_8.png)

![](img/f072338922859166405c22985cba8c16_9.png)

![](img/f072338922859166405c22985cba8c16_10.png)

![](img/f072338922859166405c22985cba8c16_11.png)

So then we take that output here and we can see that we have the original request and we have the critique。

 which we're going to format as a human message because again。

 we're asking this reflection step to be role playing as a teacher and so it generates a new one and so then it says we have the。

😊。

![](img/f072338922859166405c22985cba8c16_13.png)

Or it takes it out and then it says we're going to have an approved essay outline here。



![](img/f072338922859166405c22985cba8c16_15.png)

And then you can repeat so this basic step is pretty simple。



![](img/f072338922859166405c22985cba8c16_17.png)

The next bit shows how to wire this up in La graph。



![](img/f072338922859166405c22985cba8c16_19.png)

We're going to use our basic message graph， which is line graphra primitive that stores state across nodes as a list of chat messages。



![](img/f072338922859166405c22985cba8c16_21.png)

![](img/f072338922859166405c22985cba8c16_22.png)

We'll wrap each of our functions above in these nodes that willll put them in as the message is key。

 so whenever it's called in the prompt template is formatted correctly。

 and then here we include a little bit of a translation from the AI messages to human messages and back so that the role playing model doesn't get too confused about who's saying what。



![](img/f072338922859166405c22985cba8c16_24.png)

The overall graph is simple。 We have two nodes， generate and reflect。

 and we continue to loop around based on this conditional edge here。

 If once it's reached a certain point， it's going to end。 So we create that。

 and then we'll see how it does。

![](img/f072338922859166405c22985cba8c16_26.png)

So you'll see over time it'll start to generate Reflex this is the first pass。

 you can see it has an output there， this one。

![](img/f072338922859166405c22985cba8c16_28.png)

It says you have demonstrated a strong understanding。

 but maybe you include some more quotes and citations， we can see over here。😊。

It continues to chugle along。It includes some improvements to different paragraphs。

 we're going to print it out at the end， you can see these are starting to get quite long and then we'll generate this one out here。

 So the last result here we can include some references。

 of course this looks like it was probably hallucinated but you can see it responding to the overall criticism of the reflection step by incorporating that later so it's trying to be doing citations and everything and appear more informative and etc。

Before we move on to the next one， I'll note that this is extremely simple， it is a single cycle。

 but since we're not grounding the reflection step in anything。

 it isn't guaranteed to actually improve performance。 This often still does improve because you。

Teaching the LLM to role play and you're encouraging it to incrementally improve。

 sometimes it commits to a specific path in the token generation trajectory that isn't ideal and so then you give it a chance to use the more compute improve。

 but again overall doing this without grounding at anything can see some limited but not extremely wonderful game。



![](img/f072338922859166405c22985cba8c16_30.png)

![](img/f072338922859166405c22985cba8c16_31.png)

![](img/f072338922859166405c22985cba8c16_32.png)

The next design we'll be going over is Reflexion by Shiin Aal。

 It's an architecture designed to learn through verbal feedback and self reflection。

It extends the reflection example we have below。Before， by incorporating both tool observations。

 as well as more explicit prompting around how to ground or how to project the reflections。

 So as you can see in this graph。

![](img/f072338922859166405c22985cba8c16_34.png)

The user request is first fed to a responder which generates the initial response。

 so it tries to answer， it tries to generate its own self critique and then generate some search terms that it could use to extend its answer and improve it there all of the tools are executed and it's fed into the revision step which then re-answers so it does an improvement based on the critique and search and other observations there as well as adding some citations that seeks to address the original critique based on the retrieved outputs it repeats this a number of times so continuing to reflect and then search for things in order to improve based on that criticism until it reaches desired state and then returns the final response that user。



![](img/f072338922859166405c22985cba8c16_36.png)

![](img/f072338922859166405c22985cba8c16_37.png)

![](img/f072338922859166405c22985cba8c16_38.png)

As in last time we have some initial prerequisites to set up I already installed these beforehand。

 but it depends on Lng chain and then we're using a search engine called Tvioli in order to treat this as a research agent we're connecting to open AI this time as will need that API key and then we'll also set up linksmith tracing just so we can reproduce and see the exact trajectory of this agent as it gets a little bit more complex than the last one we'll start by defining the tools again。

 these tools ground the agent a lot so we have a little bit of boilerplate here just to execute them in parallel and do some nice cities there and then we'll get into the meat of it so here we have the original actor prompt template so this is again the respondpoer and we just call it an expert researcher and we give it an instructions and then say they reflect and criticize and recommend search queries in order to improve your answer based on what it already knows and again this lets it and use its parametric knowledge so what the model has already been trained on to give an initial guess but then we'll use external。



![](img/f072338922859166405c22985cba8c16_40.png)

![](img/f072338922859166405c22985cba8c16_41.png)

![](img/f072338922859166405c22985cba8c16_42.png)

![](img/f072338922859166405c22985cba8c16_43.png)

![](img/f072338922859166405c22985cba8c16_44.png)

![](img/f072338922859166405c22985cba8c16_45.png)

![](img/f072338922859166405c22985cba8c16_46.png)

![](img/f072338922859166405c22985cba8c16_47.png)

And selfreflection in order to improve that through a series of loops we're using function calling just so that it's easy to parse out。

 we'll see that we explicitly prompt the criticism to generate both missing and superfluous aspects of its response again so it has that balance in the response type and then we also generate these search queries that it will be passed on to the search engine afterwards these can be executed in parallel so it's not too long and the answer we're telling it should be around a 250 word detailed answer again。

 you can control all of this stuff from to prompt itself will be doing some retries in case it doesn't validate well and here is an example。



![](img/f072338922859166405c22985cba8c16_49.png)

![](img/f072338922859166405c22985cba8c16_50.png)

![](img/f072338922859166405c22985cba8c16_51.png)

![](img/f072338922859166405c22985cba8c16_52.png)

![](img/f072338922859166405c22985cba8c16_53.png)

So I'll see the answer。We're asking about reflection so it talks about， oh。

 it refers to our systems and ability to analyze and improve so it seems pretty good it says that it's quite focused but and there is not super information。

 it's actually pretty good there it could expand on some specific techniques or algorithms so then it's looking for techniques for this we'll world examples and pattern reflection maybe in the future be able to find this video itself So once that comes out。

 we'll set up the revised one。 this prompt is very pretty much similar the only difference being we're going to inject these revised instructions back here in the template here is a first step and these specifically we' instruct it on how to use numeric citations for that output here so we're going to be adding references and this is again a technique both as useful so that it can be citing the search results that it's being used and then it also can help steer the LLM to generate more grounded output we'll go through that again and then to the point where we。



![](img/f072338922859166405c22985cba8c16_55.png)

![](img/f072338922859166405c22985cba8c16_56.png)

![](img/f072338922859166405c22985cba8c16_57.png)

![](img/f072338922859166405c22985cba8c16_58.png)

ai looking can get constructing the graph。We'll be using the message graph again。

 which treats the state as just a list of chat messages， we'll have three nodes， the original draft。

 we have a tool executor node and the revised node。Every time that it hits the draft。

 it'll go to execute tools and any time the execute tools node completes， it goes through a size。

 the looping logic is defined here。 So we have the conditional edges here。

 and then once it reaches the maximum of iterations， it'll end。 So we're doing an explicit loop。



![](img/f072338922859166405c22985cba8c16_60.png)

![](img/f072338922859166405c22985cba8c16_61.png)

![](img/f072338922859166405c22985cba8c16_62.png)

So let's see a very easy question， how should we handle the climate crisis and so you can see I ran this before。

😊。

![](img/f072338922859166405c22985cba8c16_64.png)

So it looks like the execution is completed and we can print out all of the examples here。

 you can see that it both has a number of points here and then a lot of references that try to cite each of these examples and it's done this over a series of steps you can look at the whole trajectory by going to Langsmith。



![](img/f072338922859166405c22985cba8c16_66.png)

![](img/f072338922859166405c22985cba8c16_67.png)

![](img/f072338922859166405c22985cba8c16_68.png)

![](img/f072338922859166405c22985cba8c16_69.png)

So you can go in this reflection one and you can see the series of steps so you can see that it generates。

 it decides the original answer， executes the tools， revises。

 and then does that a number of times so you can actually see the final output and then for each of these you could try and go in and rerun some of these outputs just to see how it perform if you want to be making any changes to the prompt template。



![](img/f072338922859166405c22985cba8c16_71.png)

![](img/f072338922859166405c22985cba8c16_72.png)

![](img/f072338922859166405c22985cba8c16_73.png)

So our final example is a little bit more complicated。

 It's called language agent Tsearch by Jo et all。 It combines reflection and other reward modeling in an overall tree search process to give you the best possible trajectory at the outcome the technique looks like the graph below basically you first will generate a candidate and then you will reflect based on the outputs of the candidate and the tool actions the reflection assigns a score and then in this step you can also perform additional external checks so if you're generating code you might be running unit tests and using that to update the score based on that score you then pick a node in this case it's just the first one to generate a number of new candidates and then you repeat the process so you reflect on them possibly run some additional checks outside use that to create a score and that score is backproagate up to the parent node so that it reflects the overall how promising this particular branch is in the search and then you repeat again。



![](img/f072338922859166405c22985cba8c16_75.png)

You pick this one。 in this case， it's this branch and then generate candidates from that。

 And then you go and reflect and update and continue to go until you've solved the problem or until you've reached the maximum tree depth。

 So this。

![](img/f072338922859166405c22985cba8c16_77.png)

![](img/f072338922859166405c22985cba8c16_78.png)

Is interesting because it uses both a metric from reflection and from external observations。

 it can help balance the search process and hopefully improve over some naive depth first search or other search algorithms and。

😊。

![](img/f072338922859166405c22985cba8c16_80.png)

![](img/f072338922859166405c22985cba8c16_81.png)

![](img/f072338922859166405c22985cba8c16_82.png)

![](img/f072338922859166405c22985cba8c16_83.png)

It's overall a pretty fun one to implement。We'll get more in detail about each component below。

 I apologize it's a lot of code， but hopefully you get the sense of how this operates based on the diagram here。

 So again， we have some prerequisites， we'll set this up here and then we'll define the graph state so I think this is the most interesting part to be honest its a node that stores the messages in that node that are meant to be appendage to the trajectory the parent and its children and then it has some values。

 again， basically every time you unroll the tree， you're searching for some candidates and then you score the candidates and then you use this to be updating the overall branch you might have some questions like how do you pick the best candidate so you could do the naive way of just picking whichever one has the highest value this Monte Carlo tree search wants to be balancing that with the ability to explore other branches that hasn't explored as much yet and so it does this by using upper confidence bound or specific upper confidence bound applied to trees So you seeT。



![](img/f072338922859166405c22985cba8c16_85.png)

![](img/f072338922859166405c22985cba8c16_86.png)

![](img/f072338922859166405c22985cba8c16_87.png)

![](img/f072338922859166405c22985cba8c16_88.png)

And it's defined right here basically。Has this like an average reward term and an expir term that it combines here。

With a specific waiting term to balance exploration exploitation， again。

 this is all a hyperparameter of the system that lets you balance the ability to pick the best path with the inevit ability that sometimes it'll get caught in a local optimus。

 you want it to be able to search other ones and get itself out。😊。



![](img/f072338922859166405c22985cba8c16_90.png)

嗯。I'll skip over some of the other specifics there。

 but if you check out the code you can try to reim it yourself， the tree state itself。

 well I to run this first， the tree state itself then just has this tree represented by the root and then the original input。



![](img/f072338922859166405c22985cba8c16_92.png)

![](img/f072338922859166405c22985cba8c16_93.png)

![](img/f072338922859166405c22985cba8c16_94.png)

Now that we have the tree state， we can define the language agent。

 which is a little bit less complicated to us， honestly。

 we're just going to use chatTBT Trbo and we'll be using again a search engine here。



![](img/f072338922859166405c22985cba8c16_96.png)

![](img/f072338922859166405c22985cba8c16_97.png)

Most of the thing that I've implemented uses function calling as well so reflection。

 you generate a string based on the reflections on whether the output is sufficient more superfluous and those types of things we'll assign a score in this case on a scale from  zero to 10 on the equality of the output and then we'll use this to determine whether it's found a solution so we can do this。



![](img/f072338922859166405c22985cba8c16_99.png)

![](img/f072338922859166405c22985cba8c16_100.png)

And then the next step will be generating the initial response。



![](img/f072338922859166405c22985cba8c16_102.png)

Whenever。This is a very simple prompt producing your assistant we give it a couple tools and then it can pick a path there。



![](img/f072338922859166405c22985cba8c16_104.png)

So an example here， if we're asking to write a research report on lithium pollution。

 it'll decide to query the search engine。

![](img/f072338922859166405c22985cba8c16_106.png)

With the I pollutionution Research report， not the most creative， I'll admit。

 but it gets the job done， we wrap this in a node itself， so all this does is it takes the generator。

 it executes the tools if they are there， it calls the reflection agent and then uses that to create a new node in the tree and this root is then added here。

 since it's the first step and added to the graph state。



![](img/f072338922859166405c22985cba8c16_108.png)

![](img/f072338922859166405c22985cba8c16_109.png)

![](img/f072338922859166405c22985cba8c16_110.png)

![](img/f072338922859166405c22985cba8c16_111.png)

The next step is Ken of generation。It's the same as the previous step， but unroll a little bit more。

 So here we're going to be using the LM generate button method on the length chain LLMs just to generate and candidates。

 This is all configurable and each of these candidates will be treated independently as a new node in the tree。

 we do some de duplication later。

![](img/f072338922859166405c22985cba8c16_113.png)

So here's an example， we're asking at the same question。

 it generates five outputs that are all pretty much the same， but with different query terms。



![](img/f072338922859166405c22985cba8c16_115.png)

![](img/f072338922859166405c22985cba8c16_116.png)

![](img/f072338922859166405c22985cba8c16_117.png)

Once you do that， we will put this in this big， scar looking node here。

 which again does the same as above。 But since we're doing a bunch of candidate generations and I wanted to do it all in parallel is a little execute or a little additional code here so we get the best candidate here with this get trajectory or we get the best child method here from the room we generate。

 then we get the messages from it。 we expand to generate five new candidates We'll then parse these and it like。



![](img/f072338922859166405c22985cba8c16_119.png)

![](img/f072338922859166405c22985cba8c16_120.png)

Tool implicationss。 we run all of the search queries in parallel， and then well be。



![](img/f072338922859166405c22985cba8c16_122.png)

Prompting the reflection change and then score all those outputs。

 and then we'll take all those outputs， so the original selection of tools or final response and the reflection messages and putting them in the new nodes and adding them all back into the tree as children of the best candidate。



![](img/f072338922859166405c22985cba8c16_124.png)

So we can read this。Finally， the moment you've been waiting for the actual graph is quite simple here。

 we have two nodes， start and expand， start in the start node。

 and then at each of these points well check whether we should load so we can finish if the root is solved if the reflection step says。

 hey you've answered the question directly and we also finish if the root's height is greater than five so we want to make sure that the tree doesn't get too big。



![](img/f072338922859166405c22985cba8c16_126.png)

And then you can try calling it， well， we need to run this first。



![](img/f072338922859166405c22985cba8c16_128.png)

You can see I ran a couple of these before。

![](img/f072338922859166405c22985cba8c16_130.png)

Was pretty good at these outputs。 We'll see how well it does this time。



![](img/f072338922859166405c22985cba8c16_132.png)

So I'm printing out the steps here。 You can also use some other extreme events methods to get in more incremental information。

 I think this is enough for me while it's。

![](img/f072338922859166405c22985cba8c16_134.png)

Proreceeding， we can actually go check out Lng in that。



![](img/f072338922859166405c22985cba8c16_136.png)

And。See， I'm going to a new project here。And you can see it streaming here so you can see there's a lot of calls right now since we're doing a lot of parallel execution。

 we generate the initial candidate and says we're going to talk about so we're asking it to generate the table of average size and weight and so it needs these parallel processes again。

 all this is all considered a single node and then reflect the reflection method。Output a score of 9。

 So pretty good。 It says， again， if this were a co generation task or another task where you have external。

Feedback on it， you can get a little bit more of a nuanced score here than just the self reflection。



![](img/f072338922859166405c22985cba8c16_138.png)

Next you go into this expand step so you generate five more candidates and then you generate all these tool calls from all of the different candidates we do some de duplication in between。

 but there's probably a lot of repetitiveness here。And then。

The agents still going so so you can see it goes out and then there's some reflection。

 and then it looks like it found the solution here in a number of the branches。



![](img/f072338922859166405c22985cba8c16_140.png)

![](img/f072338922859166405c22985cba8c16_141.png)

And it's good。So， I'll go back。

![](img/f072338922859166405c22985cba8c16_143.png)

To this output。

![](img/f072338922859166405c22985cba8c16_145.png)

So it seems that it it is asking for additional information。

 We could probably go back up a step and and generate a summary of the outputs there based on it。

 And then here we're asking it to generate a series of moves based on。



![](img/f072338922859166405c22985cba8c16_147.png)

![](img/f072338922859166405c22985cba8c16_148.png)

![](img/f072338922859166405c22985cba8c16_149.png)

The Magnus Carlson's chess game against A Theosa， I'm sorry for betraychering the name and it's saying。



![](img/f072338922859166405c22985cba8c16_151.png)

![](img/f072338922859166405c22985cba8c16_152.png)

So it's lookinging at some of the outputs here based on the research there。

 So these outputs weren't the best here， I think that it would probably be a better example if we included some code execution if for the reflection steps of the scores are more useful。

 but overall I think it's a promising technique。

![](img/f072338922859166405c22985cba8c16_154.png)

![](img/f072338922859166405c22985cba8c16_155.png)

![](img/f072338922859166405c22985cba8c16_156.png)

Again， the。

![](img/f072338922859166405c22985cba8c16_158.png)

Overall approach is that you have some tree roll out， you score each step。

You then pick the best node based on those scores， and then you continue to update and refine them。

This isn't super feasible if you want an immediate snappy application experience for your chatbot。

 it is good if you want to have more complicated reasoning type tasks and if it's embedded in the overall system。

 and this is also a great way to generate better fine tuning data since if you just automatically generating from a single pass the quality won't be as good。

 typicallyyp when you want to be having fine tuning data。

 quality is way more important than quantity there。 so。😊。



![](img/f072338922859166405c22985cba8c16_160.png)

I guess with that I'll sign off here thanks again for listening this is another fun video hope that you enjoyed we talked about reflection in this video and specifically reflection as a means of improving agent performance we went over a couple of videos examples one was a basic reflection example one was reflectionion which adds additional tool observations and specific prompting into the loop there to improve the overall output and then the finals language agent tree search which incorporates reflection as well as another other external feedback components in a tree search which can hopefully get the best trajectory overall by doing a bunch of parallel operations。

😊。

![](img/f072338922859166405c22985cba8c16_162.png)

So anyways， thanks for watching if you want to sign up for Langsmith， you can do so for free atsmith。

Lngchain。com and check out some of other videos here on YouTube so thanks again。



![](img/f072338922859166405c22985cba8c16_164.png)