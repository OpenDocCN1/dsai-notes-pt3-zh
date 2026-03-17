# 【英伟达GTC人工智能大会 • 中英】NVIDIA GTC 2024 p02 P02 Generally Capable Agents in Open-Ended Worlds, Jim Fan, NVIDIA Lead of Embod -BV1yHAeeqECP_p2-

![](img/89f9160294a59b33a21df3a57207850f_0.png)

Okay they go。Testing， alright， everyone， hellello， welcome to GTC this morning。 How's everyone doing。

Good， we're nice and awake， excited。Well， today I'm happy my name is Nathan Hocks。

 I work for NviDdia。 I get a kind of dabble in gym stuff sometimes。 So very excited to be here。

 I'm just gonna dive right into it。 Jim F is research manager and colea of embodied AI here at NviDdia。

 his primary focus is developing generally capable autonomous agents to tackle this grand challenge。

 his research spans foundation models， policy learning， robotics。

 multi multimodal learning and large scale systems。

 he obtained his PhD and computer science from Stanford。

 He wanted to keep a short so he can get just right into it。 So without further ado。

 please welcome Jim F。😊，Yeah， thanks， everyone， for coming so early in the morning。

 I know it's a bit too early for Bay Area time。 So thanks， everybody。😊。



![](img/89f9160294a59b33a21df3a57207850f_2.png)

嗯，So。I want to tell you guys a story about。The spring of 2016。

When I was taking a class at Columbia University， but I wasn't actually paying attention to the lecture。

And instead， I was watching a board game tournament on my laptop。And it wasn't just any tournament。

 but a very， very special one。So the match was between。Deep mind， Alphago and liido。

 And the AI just won three out of five games and became the first ever to beat a human champion at the game of Go。

So I still remember the adrenaline of seeing history unfold。

 the moment of glory when AI agents finally enter the mainstream。😊，But when the excitement fades。

I realized that as mighty as Alphago was， it can only do one thing and one thing alone。

It is not able to play any other games like Super Super Mariio or Minecraft。

 And it certainly cannot do your dirty laundry or dishes。

But what we truly want are AI agents as versatile as Walli。



![](img/89f9160294a59b33a21df3a57207850f_4.png)

As diverse as all the robot forms or embodiments in Star Wars。And works across infinite world。

Virtual or physical， as in ready player 1。So how do we get there in possibly the near future。

So this is your Hchhiker's guide。To General purpose AI agents。

Most of the ongoing research efforts can be laid out across these three axes。

The number of skills an agent can do。 the embodiments it can control。And the real is， it can master。

And this is where ourphago is。 But the upper right corner is where we all want to go。

So I've been thinking for most of my career about how to travel across this galaxy of challenges towards this upper right corner。



![](img/89f9160294a59b33a21df3a57207850f_6.png)

And earlier this year， I had a great fortune to establish G Lab with Jensens support and blessing。😊。



![](img/89f9160294a59b33a21df3a57207850f_8.png)

And I'm very proud of the name。 G G E A R stands for journalist embodied Asian Research。😊。



![](img/89f9160294a59b33a21df3a57207850f_10.png)

I'm co this initiative with Yuke Zhu。 And this is a picture that we took seven years ago at Stanford。

 where Yuca and I were both still PhD students at Fee Fe Li's group。

And we did robotics hack songs all the time， because， you know， especially before deadlines。

 we the most productive。

![](img/89f9160294a59b33a21df3a57207850f_12.png)

And here， Jay on the left is from a Di group also at Nvida Research， working very closely with gear。

 and all three of us basically move from Stanford to NviDdia。And man， we were so young at that time。

 Look at what PhD did to us。 You know， the quest for AGI is a lot of pain and suffering。So。

Let's go back to the first principles。 What essential features does a journalist agent need。



![](img/89f9160294a59b33a21df3a57207850f_14.png)

And I would argue， three things。First， it should be able to survive。

 navigate and exploring an open ended world。

![](img/89f9160294a59b33a21df3a57207850f_16.png)

And alphaphago has a singular goal， and it's simply not open ended。And second were knowledge。

 The agent should have a large amount of pretrain knowledge instead of knowing only a few concepts in the environment。

And third， as a journalists agent， the name implies。

 it must be able to perform more than a few tasks， ideally， infinitely multitask。

 You prompt it with any reasonable language， and the agent should be able to complete that mission for you。



![](img/89f9160294a59b33a21df3a57207850f_18.png)

So what does it take。

![](img/89f9160294a59b33a21df3a57207850f_20.png)

Correspondingly。The environment needs to be open ended enough because the agent's complexity is upper bounded by the environment complexity。

And planet earth that we live on is actually a perfect example because the earth is so open ended that it enables an algorithm called natural evolution to produce all the diverse behaviors of life on this planet。

😊。

![](img/89f9160294a59b33a21df3a57207850f_22.png)

So can we have a simulator that is essentially a low fire earth。

 but we can still run on lab computers。And second， we need to provide the agent with massive pre training data。

 because exploration from scratch in such an open ended world is simply intractable。



![](img/89f9160294a59b33a21df3a57207850f_24.png)

And this data will be a reference manual on how to do things。 And more importantly。

 what are the interesting things worth doing。And finally。

 we need a foundation model that's scalable enough to convert this large scale data into actionable insight。



![](img/89f9160294a59b33a21df3a57207850f_26.png)

And this trend of salt lends us in Minecraft。 The best selling video game of all time。

And for those who are not familiar， Minecraft is this procedurally generated world of 3D voxels。

 And in this game， you can do whatever your heart desires。

So what's special about the game is that Minecraft defines no particular score to maximize and no objective to follow。

And that makes it very well suited as a truly open ended empower。And as a result。

 we see some very impressive creations， like someone built the Howars Castle block by block in Minecraft。

And someone else， apparently with nothing better to do， built a functional neural network。

Because Minecraft has logical gates and is apparently touringcomplete。

I want to highlight the number here。 Minecraft has1 hundred 40 million active players。

 And just to put this number in perspective， this is more than twice the population of UK。

And it just so happens that gamers are generally happier than PhDs。

 So they love to play and share their journey on online。😊，So this huge， you know。

 human mass of gamers produce a lot of data every day。 And the question is。

 how can we tap into this treasure trove of data。So we introduce Min Dojo。

 a new open framework to help the community develop general general purpose agents using Minecraft as a kind of primordial soup。

So mind audio has three parts， a simulator， a database and a model。



![](img/89f9160294a59b33a21df3a57207850f_28.png)

So the simulate API we built unlocks the full potential of the game for AI research。

 and we support observation space like RGB and Voxso and GPS and two levels of action space。



![](img/89f9160294a59b33a21df3a57207850f_30.png)

And mind dojo can be customized at every detail， such as terrains， weathers and monsters spawning。

And it also supports creative tasks that are free form and open ended。So， for example。

 let's say we want the agent to build a house。 But what makes a house， a house。Right。

 it's very difficult to implement this kind of success criterion in simple Python code。

And the only way is to use foundation models， train our Internet skill knowledge so that the abstract concept of a house can be captured。

And next， we collected an Internet skill knowledge base of Minecraft to help the agent lift off the ground because it's really hard to explore from scratch。

And this database got three parts。 The first is video。

 We find that Minecraft is among the most streamed game online。

 and gamers just like to talk about what they're doing。

 So we collected more than 300000 hours of videos with more than 2 billion words in transcript。

And the second is Mincraft Wiiki with 7000 multimod pages of images， tables and diagrams。

And the third is the Minecraft subredit。Which we found that people use as a kind of stack overflow when they need some help on Mincraft。



![](img/89f9160294a59b33a21df3a57207850f_32.png)

So here's a peek at our mind Dojo Wiki data set。 And can you believe that someone listed all the crafting recipes。

 thousandshou of them。

![](img/89f9160294a59b33a21df3a57207850f_34.png)

And explains all the monsters。 And basically every possible game mechanics you'll ever see in every version of Minecraft。



![](img/89f9160294a59b33a21df3a57207850f_36.png)

So one thing I learned is that gamers just got a lot of time to killal。Well， but。

 I'm not complaining， right， because thanks for the data。 Please do more。 Thanks for the data。



![](img/89f9160294a59b33a21df3a57207850f_38.png)

Now， what to do with the data。

![](img/89f9160294a59b33a21df3a57207850f_40.png)

It's time to train a foundation model。Here， the idea is very simple For our YouTube database。

 we have time aligned video clips and transcripts。 And these are actually real tutorial videos。

 like here in text prompt 3， as I raise my a in front of this pig。

 there's only one thing you know is gonna happen。 This is actually from a YouTube tutorial。

We then can train a pair of encoders to map the video and transcript to a vector embedding。

And then embeddings can be trained by a process called contrastive learning。

 which essentially pulls together a video and the text that match and pushes apart those that don't match。



![](img/89f9160294a59b33a21df3a57207850f_42.png)

And this pair of encoders is called the mine clip model。



![](img/89f9160294a59b33a21df3a57207850f_44.png)

And intuitively， Minecl learns the association between the video and the transcript that describes the action in the video。

It outputs a score between 0 and one， and one means perfect description。

 and 0 means that the text has nothing to do with the video。



![](img/89f9160294a59b33a21df3a57207850f_46.png)

So this effectively becomes a language conditioned foundation reward model that understands the nuances of forests。

 animal behaviors， Archects。 you name it in Minecraft， all the abstract concepts。



![](img/89f9160294a59b33a21df3a57207850f_48.png)

![](img/89f9160294a59b33a21df3a57207850f_49.png)

Now， how do we use Min clip in action。

![](img/89f9160294a59b33a21df3a57207850f_51.png)

Here， an agent interacts with our minddo simulator。 and the task is in English。

 she sheep to obtain war。So as the agent explores， it generates a video snippet。

 which can be encoded and fed to minecl。And then it computes the association。

 The higher the score is， the more the agent's behavior is aligned with the tax prompt。

And that becomes the reward function to any reinforced me learningia algorithm that you like。



![](img/89f9160294a59b33a21df3a57207850f_53.png)

So this looks very familiar， right， because it's essentially reinforcement learning from human feedback or R I。

And R O HF is the cornerstone that powers tryGBT。 And I believe it's going to play a critical role in embodied agents。

 as well。And here are some demos of our learned agent behavior on various tasks。



![](img/89f9160294a59b33a21df3a57207850f_55.png)

So let's put my clip on this Hchhiger guide。It's able to do a lot more tasks。Then alpha go。

 But the limitation is that you have to manually decide a task prompt and run training for each skill。

And the agent isn't really able to discover new things by itself。



![](img/89f9160294a59b33a21df3a57207850f_57.png)

But this all changed in 2023， where a model called GP4 came。

That's a language model so powerful at coding and planning。And so， we built for。

An agent that massively scales on the number of skills。



![](img/89f9160294a59b33a21df3a57207850f_59.png)

And when we set Voyager loose in Minecraft， it is able to play the game for hours on end。

 without any human intervention。😊。

![](img/89f9160294a59b33a21df3a57207850f_61.png)

And the video I show here are snippets from a single episode。Where  Voyager just keeps going。

 it explores the terrains， mine all kinds of materials， fight monsters。

 craft hundreds of recipes and unlocks and ever expanding tree of skills。



![](img/89f9160294a59b33a21df3a57207850f_63.png)

So what's the magic behind it， The key insight is coding as action。

We convert the studio world into a textual representation。

 thanks to an open source Minecraft mod called Minfler and Voyager invoke G 4 to generate code snippets in jascript。

And each snippet becomes an executable skill in the game。And just like human engineers。

 the program thatvo write wouldn't always be correct on the first try。

 So we have a self reflection mechanism to help it improve。



![](img/89f9160294a59b33a21df3a57207850f_65.png)

And the self reflection relies on three sources。 The Javascript execution era。

 the agent's current state， like hunger and house and the world state。

 like the landscape or the monsters nearby。

![](img/89f9160294a59b33a21df3a57207850f_67.png)

![](img/89f9160294a59b33a21df3a57207850f_68.png)

And the agent takes an action， observes the consequence of its action on the world and itself。

 reflects on how it could do better。 try out more actions and ringse and repeat。



![](img/89f9160294a59b33a21df3a57207850f_70.png)

And once the skill becomes mature， Voyager stores the program into a skill library。

You can think of it as a co library， authored entirely by trial and error， by GB4。

And then the agent can retrieve the skills from the library when it sees a similar situation in the future。

And in this way， Voyager bootst traps its own capabilities recursively。

 as it explores and experiments in Mincraft。

![](img/89f9160294a59b33a21df3a57207850f_72.png)

So let's quickly go through an example together。

![](img/89f9160294a59b33a21df3a57207850f_74.png)

Here， the agent H bar has dropped very low， so it needs to find food。

And it senses four entities nearby， a cat， a villager， a pig， and some wheat seeds。

So it starts and in a monologue， right， Do I kill the cat or the villager for food？

 That sounds like a bad idea。How about the seeds。 I can grow a farm， but it's gonna take too long。

 So really sorry， Pggy， you are the chosen one。

![](img/89f9160294a59b33a21df3a57207850f_76.png)

And then it checks the inventory and retrieves an old skill from the library to craft and iron sort and then learns starts to learn a new skill called Hunt pig。

And now we also know that Voyager unfortunately， isn't vegetarian。



![](img/89f9160294a59b33a21df3a57207850f_78.png)

So question still remains。How does Voyager keep exploring indefinitely。

We gave Voyager a high level directive。That is to obtain as many novel items as possible。

And Voyager implements a curriculum to find progressively harder and novel challenges to solve。



![](img/89f9160294a59b33a21df3a57207850f_80.png)

And putting all these together， Voyager is able to master and also discover new skills along the way。

 And we didn't preprogram any of this。 What you see here is called lifelong learning。

 where an agent is forever curious and forever pursuing new adventures。

And these are two birds eye views of the Minecraft map。

 The biggest orange circles are the distances that voyager travels。

The agent explores so much because it has to move around to obtain as many novel items as possible。



![](img/89f9160294a59b33a21df3a57207850f_82.png)

And because it loves traveling。 So that's why we call it Voyager。



![](img/89f9160294a59b33a21df3a57207850f_84.png)

Now， compared to mine clip， Voyager is able to pick up a lot more skills by itself。

 but it still knows only one。 it still knows how to control only one body in Minecraft。



![](img/89f9160294a59b33a21df3a57207850f_86.png)

But can we have a single model that works across different body forms。



![](img/89f9160294a59b33a21df3a57207850f_88.png)

Enters metatamorph。

![](img/89f9160294a59b33a21df3a57207850f_90.png)

It is a project that I co developed with Stanford researchers。

We created a foundation model that works on not just one。

 but thousands of robots with different arm and leg configurations。

And metamorph has no problem adapting to extremely varied kinematic characteristics of different bodies。

So， here's the intuition。We develop a vocabulary to describe robot parts。

 And then each body is basically a sentence written in the language of this vocabulary。

And more specifically， each robot can be expressed as a graph of joints or kinematic tree。



![](img/89f9160294a59b33a21df3a57207850f_92.png)

![](img/89f9160294a59b33a21df3a57207850f_93.png)

And you can convert the body to a sequence of tokens by traversing this kinematic tree。

By depth for search。And each token here represents some physical properties of the joint。

 and the sequence describes the morphology of the robot。



![](img/89f9160294a59b33a21df3a57207850f_95.png)

And different robots may have different numbers of joints and configurations。

 But the tokenizer doesn't care， right， It's all converted to sequences of different lengths。

 just like text strings。

![](img/89f9160294a59b33a21df3a57207850f_97.png)

And what do we do with sequences as AI researchers， our knee jerk reaction is to apply a transformer。

 And that's exactly what we did。So instead of writing out text。

 Metamorphph writes out motor controls for each joint。

And because we want to learn a universal policy that works across morphologies。

 we batch together all the robot sentences。And train a big multitask neural network。

 just like tryGPT。

![](img/89f9160294a59b33a21df3a57207850f_99.png)

And no matter what a robot looks like， it's all the same。

 It's all just sentences to the eye of metamorph。

![](img/89f9160294a59b33a21df3a57207850f_101.png)

And we can scale it up by training all the embodiments in parallel with reinforcement learning。

And in our experiments， we show that metamorph is able to control thousands of robots with extremely varied kinematic properties to walk upstairs across irregular terrains or avoid obstacles。

😊。

![](img/89f9160294a59b33a21df3a57207850f_103.png)

And we also made a fascinating discovery。We found that metamorph can even generalize zero shot to a morphology that has never seen before。

Which means that transformers。Are able to transfer across embodiments as long as they speak the right language。

And let's extrapolate a bit into the future。If we expand the robot body vocabulary even further。

I envision that one day， Memorph of 2。0 can journalistize to robot arms， dogs。

 different types of humanoids and even beyond。

![](img/89f9160294a59b33a21df3a57207850f_105.png)

So compared to Voyager。Metamorph takes a big stride towards multi body control。



![](img/89f9160294a59b33a21df3a57207850f_107.png)

And it's now time to take things to the next level。



![](img/89f9160294a59b33a21df3a57207850f_109.png)

And transfer skills and bodies across realities。Enterers。



![](img/89f9160294a59b33a21df3a57207850f_111.png)

Isaac。And video simulation initiative。

![](img/89f9160294a59b33a21df3a57207850f_113.png)

So Isaac Sim's greatest strength is to run physics simulation at1 thousand times faster than real time。

For example， this character learned impressive martial skills by going through 10 years worth of virtual training in only three days of simulation time on GPU。



![](img/89f9160294a59b33a21df3a57207850f_115.png)

So it's very much like the virtual sparring dojo in the movie matrix。

And this race car scene is where simulation has crossed thecani Valley。

Thanks to how to accelerate rate tracing。We can render very complex walls with breathtaking levels of details。

And the photo realism here can help us train computer vision models that will become the eyes of embodied agents。



![](img/89f9160294a59b33a21df3a57207850f_117.png)

And was more。In Isaac Sam。We can procedurally generate infinite worlds。

 and no two will look the same。So here is an interesting idea。

If the agent is trained on 10000 different simulations。They may as well， just generalize to。

Our physical world， our box。Which simply the 10000 first reality。So let us thinking。

So what new capabilities can Isaac S unlock。This is Eureka。

An agent that achieves robot dexterity at a superhuman level。



![](img/89f9160294a59b33a21df3a57207850f_119.png)

Well， maybe not all humans， at least better than myself。

Because I have given up our pen spinning a long time ago since childhood。 And finally。

 I can have my AI avenge my poor skills。

![](img/89f9160294a59b33a21df3a57207850f_121.png)

So， here's the idea。Isac Sim has a Python API to construct training environments。

 such as creating a five finger hand to interact with a pen in the simulation。

We also assume that the human written code specifies a success criteria。



![](img/89f9160294a59b33a21df3a57207850f_123.png)

For example， if the pen reaches certain 3D orientations consistently。

And this success criterion only tells you what to do， but not how to do it with the finger joints。



![](img/89f9160294a59b33a21df3a57207850f_125.png)

So the first step of Eureka is to pass the environment code and task description as context to G4。

And task here is to make the shadow hands spin a pen to a target orientation。

And then Eureka samples a reward function。And it is a very fine grainined signal that shapes the behavior of the neural network controller towards a good solution。

And normally， expert human engineers will hand tune this reward function。

 which is often a very tedious and difficult process。

 It takes a lot of iterations and also a lot of expertise。

 Not every engineer can do it if you're not familiar enough with the physics simulation。



![](img/89f9160294a59b33a21df3a57207850f_127.png)

So， let's automate it。Once we have a reward function。

 we can run reinforcement learning to maximize it through lots of trial and error。

It only takes about 20 minutes to train a full run for Eureka for one of the reward functions instead of days。

 thanks to the massively parallel simulation in Iac。



![](img/89f9160294a59b33a21df3a57207850f_129.png)

![](img/89f9160294a59b33a21df3a57207850f_130.png)

And when the training loop finishes， it returns an automated feedback report that tells you Rayka how well that it does。

And it also breaks it down to details like different components in the reward function。

 such as the velocity reward and the posture reward。And putting it together。

 G 4 generates a bunch of reward function candidates and each perform a full reinforcement learning training run。

Eureka would pass on the automated feedback and ask the language model to do a self reflection on the results。

And then the language model were reason about where to improve and propose the next generation of reward function candidates and ringinse and repeat。



![](img/89f9160294a59b33a21df3a57207850f_132.png)

So it's kind of like an in context， evolutionary search。And compared to expert humans。

 Eureka is able to find much better reward functions for each task。

 like spinning the pen along different axes。They actually require different reward functions for each configuration to work well。



![](img/89f9160294a59b33a21df3a57207850f_134.png)

And that would be a nightmare for robotices to just tune it one by one by hand。 And trust me。

 I have tried it before。 I wanted to pull my hair out。

 Judy4 just has a lot more patience than any of us。



![](img/89f9160294a59b33a21df3a57207850f_136.png)

![](img/89f9160294a59b33a21df3a57207850f_137.png)

![](img/89f9160294a59b33a21df3a57207850f_138.png)

![](img/89f9160294a59b33a21df3a57207850f_139.png)

So it's worth noting that Eureka is a general purpose method that bridges the gap between high level reasoning and low level motor control。

Eureka uses a new paradigm that I call hybrid gradient architecture。

 where a black box influence only large language model instructs a white box learnable neural network。



![](img/89f9160294a59b33a21df3a57207850f_141.png)

![](img/89f9160294a59b33a21df3a57207850f_142.png)

So the auto loop is great and free and runs G4 to refine the reward function in a coding space。

And the inner loop is grade and based and trains a reinforcement learning controller to achieve the。

 the skill that you want to do。

![](img/89f9160294a59b33a21df3a57207850f_144.png)

![](img/89f9160294a59b33a21df3a57207850f_145.png)

And you must have both loops to succeed。

![](img/89f9160294a59b33a21df3a57207850f_147.png)

But the question is， why stop I just a reward function。If you stare hard enough。



![](img/89f9160294a59b33a21df3a57207850f_149.png)

Everything in the robotic stack looks like code。Right， like the tasks spec， robot。

 hardware spec and simulation environments themselves all can be implemented by code。 Is that right。

So， for example， right， instead of metamorph's special language to describe the body。

 How about just using something off the shelf like U R DF。

 which people typically use in simulation stacks And U R D F is nothing but an X M L。

 which can describe the body morphology for the robots。



![](img/89f9160294a59b33a21df3a57207850f_151.png)

![](img/89f9160294a59b33a21df3a57207850f_152.png)

So in the future， I envision that Eureka plus plus can be a fully automated robotics developer。



![](img/89f9160294a59b33a21df3a57207850f_154.png)

Riding the infrastructure to train better agents and doing so iteratively。

 So my dream is that one day I can take a very long vacation。

 and Eureka will just keep reporting progress to me while I'm on the beach。 So let's see。

 how far away is that。

![](img/89f9160294a59b33a21df3a57207850f_156.png)

And and don't let， don't let Johnson know。

![](img/89f9160294a59b33a21df3a57207850f_158.png)

So in this sense， eureka isn't really a point on a map。

 but rather a force factor that can push the frontier along any axis。

And as we progress through the map， we will eventually reach a single model that generalizes across all three axes。

And that upper right corner is the foundation agent。



![](img/89f9160294a59b33a21df3a57207850f_160.png)

So I believe training foundation agents will be very similar to Cha GPT。



![](img/89f9160294a59b33a21df3a57207850f_162.png)

All language tasks， right， can be expressed as texting and text out。

 be it writing poetry or doing translation or doing math。 It's all the same。



![](img/89f9160294a59b33a21df3a57207850f_164.png)

![](img/89f9160294a59b33a21df3a57207850f_165.png)

And training child GBT is simply scaling this up across lots and lots of text data。very similar。

The foundation agent will take as input an embodiment prompt and instruction prompt and output。

And we simply scale it up massively across lots and lots of realities。

So the foundation agent is the next chapter for G Lab。



![](img/89f9160294a59b33a21df3a57207850f_167.png)

And yesterday， Jenen announced the project group。

![](img/89f9160294a59b33a21df3a57207850f_169.png)

In his keynote， a cornerstone initiative on our road map。



![](img/89f9160294a59b33a21df3a57207850f_171.png)

The mission is to create a foundation model for humanoid robots。And why humanoid。

 Because it is the most general form factor， because the world that we live in is customized for humans and human habits。

And everything that we can do in our daily lives can， in principle。

 be implemented on an advance enough humanoid hardware。

So I'm very excited to work with multiple leading humanoid companies around the world so that group may transfer even a crossingbodiments。

😊，And this is one of my favorite pictures from our GTC preparation taking in front of Nvis Headquarter。

 Actually， the building behind that is called Voyager。😊，And here we see electronic Fourier。

 agility and unry。 And just look at how happy they are at the NviA headquarters。



![](img/89f9160294a59b33a21df3a57207850f_173.png)

So on the high level， Gro takes multimod instructions， such as language。

 video and demonstration and develop skills in simulation， as well as the real world。



![](img/89f9160294a59b33a21df3a57207850f_175.png)

So here's an example of a video instruction。The GR1 robot here from foreign intelligence。

Lears to mimic human dance moves from a video。And group can also learn from human tele operated demonstrations。

Such as Apollo's cold press juic skills。So for this demo。

 we actually bought a lot of fruit at your lab。Go a more reburst。Thanks， Johnsonen。



![](img/89f9160294a59b33a21df3a57207850f_177.png)

And then the， the， the next one is from G1 also playing the drum by following a human teacher's motion。



![](img/89f9160294a59b33a21df3a57207850f_179.png)

So Gro is born on O， a new compute orchestration system to scale up models on DG X and simulation on O V。

 X。

![](img/89f9160294a59b33a21df3a57207850f_181.png)

And we use Isac La to run lots of different environments for humanoids。

 hoping that the model will generalize to a variety of skills and embodiments。

And transfer  zero shot across the same to real gap so that we can scale up the training massively on fast simulation powered by GPUus。

And now zoom me out。I believe in a future where everything that moves will eventually be autonomous。

And Project root and humanoid robots are only the first chapter。One day。

 well realize that the Asians across Walley， Star Wars already play a one。

 no matter if they are in the virtual or in the physical world。

Will just be different prompts to the same foundation agent。 And that my friends， is North Star。

Our request for AGI。

![](img/89f9160294a59b33a21df3a57207850f_183.png)

And please join us on our journey to the move， thanks。



![](img/89f9160294a59b33a21df3a57207850f_185.png)

Alright， thanks， Jim， for that。 We're gonna open up for Q And A here in the， in the session。

 So there's I'm over in the over here。 if anyone that has a question。

 they can please line up behind this mic and we will just let them have it。Alright。

 I really appreciate this talk here， Jim， I'm excited about this stuff to come。 Now。

 when I look at saying something like Minecraft， you have your Voyager。

 which is using G 4 to get all this stuff。 And then the opposite way of using say。

 dream every3 to do this stuff where it's learning completely from scratch。

 using reinforcement learning for this foundation agent。

 which of those two kind of task you think is gonna be or maybe some combination of I think that's a great question。

 And I believe it has to be a kind of combination。 because。😊。



![](img/89f9160294a59b33a21df3a57207850f_187.png)

You all have this separation between like system 1 and system 2 reasoning。 and even humans have that。

 So system 2 reasoning is like this slow， deliberate and high level reasoning。

 and system 1 is more like fast， instantaneous and like motor control。

 And I think eureka is one example， right， You have kind of a slow part of the brain that writes a reward function or someday write kind of the just the full simulation or environments。

 And then you have a fast part of it using reinforce learning。

That controls something like a Dxrous hand， which is almost impossible to control directly by something like GB4。

 right Like how can you control that hand using tax only output。 And it's also very slow。

 You have to do it at hundreds of hertz。 So I think there's gonna be this separation。

 And there will also do inference at different frequencies。 right。

 like the system 2 will do inference at a lower frequency and system 1， much higher frequency。

 And I feel that's also how humans work as well。 We think about certain things you kind of plan on global level。

 And then that planning。Propaates to your limbs。 And you don't really think when I pick up right this bottle。

 you， you' are not really thinking about exactly how you orient each finger and how you're feeling the tactile feedback。

 You don't， you don't think about it。 And that is like another kind of low level neural network doing the job。

Okay， thank you very much， thanks。

![](img/89f9160294a59b33a21df3a57207850f_189.png)

Hi， James， thank you so much。 This is mind blowing。 I'm Le you。

 vice president of data science AI at expression。 I have a question on the first part when you had this。

😊，My link as the feedback right in that framework， you call this reinforce learning。

 I have a doubt about whether this is anything related to the。

The G framework where you use the mind link as direct feedback， good or bad， right。

 as the discriminator。 And then your generator generated the the actions。 Could you please clarify。

 Yes， I think there are definitely connections here so。



![](img/89f9160294a59b33a21df3a57207850f_191.png)

I think the kind of a closer analogy would be to R O H F。

 where you're doing kind of reinforcement learning from human feedback and the human feedback part is learned by human preferences。

 And here it's actually the same。 except that the human preference is not labeled by us hiring contractors to do the job。

 but by， you know， learning from lots and lots of videos because the gamers online。

 They're already narrating what they're doing。 So you have this kind of match between the text and the video for free。

And you can use this as a kind of signal to make sure that whatever the agent is doing。

 the video that it generates matches the text prompt。 you know。

 by optimizing for this reward function。 So I do think this functions a little bit like a discriminator。

 but the difference is now it is language conditioned。

 So it's a much more powerful kind of reward model， a much more powerful discriminator。



![](img/89f9160294a59b33a21df3a57207850f_193.png)

也。So can you say that your discriminator is a language condition， a discriminator。 I think so。

 It's kind of a language condition， you know， ranking， right。

 ranking if the video is or your actions are good or good or not。 So it is a kind of discriminator。



![](img/89f9160294a59b33a21df3a57207850f_195.png)

![](img/89f9160294a59b33a21df3a57207850f_196.png)

Thanks。Hi， jam， nice's talk I'm。Oh I'm a researcher from UC Berkeley。 and I think this is great work。

 We do need GPU accelerator out from simulation to interrupt this process。 So my question is。

 what's Nvidias long term take on the gear lab， Do you guys want to do research and provide a a infrastructure for researchers and industry to accelerate this embodied A S or you guys aim to。

Produce a high level solution to like humanoid robots in general。

 That is a great question because I thought about this a lot at the founding of gear。

 So the way I position gear is three words。 mission driven research。



![](img/89f9160294a59b33a21df3a57207850f_198.png)

So I think gear fundamentally is still a research lab because unlike O O Ms。

 which do have a mature recipe now， robotics does not have a mature recipe。

And no one in the world really knows what's the best way to scale up robotics and actually have it generalized across system 1 and system 2。

 No one has figured that out yet。 And by that， it's by definition like a research project but at the same time。

 right like Jenen announced not just group this time。 but a few things along with Gro，1 is Osmo。

 which I also mentioned in my size here， So it is this compute orchestration system as like a heterogeneous know compute framework to schedule DG X and O V X 1 for training large models。

 one for s， right Osmo comes with Gro because Gro requires this kind of very special infrastructure to do。

 and for L， you don't have this problem， you don't have a simulator， But once you have a simulator。

 the computation graph becomes very complicated。 and you will need something like Osmo。

 which can be offered as cloud service。 and then Jeson Thor， which one day will。



![](img/89f9160294a59b33a21df3a57207850f_200.png)

![](img/89f9160294a59b33a21df3a57207850f_201.png)

Power group on edge computing devices or on every humanoids ever deployed。

 So it's really an ecosystem that we're doing here。

 And I see group as kind of playing a fundamental role in this ecosystem where you need a foundation model that's actually working to make the humanoid robots useful right like right now。

 humanoid robots。 theyre more of a curiosity。 They're not useful。

 like no one really has at their home， a humanoid that can do all their dirty housework for them。

 which is， by the way， my dream。 but still I'm trying I'm very lazy and I'm trying to make sure I will stay lazy right。

 So that's what I've been researching on But no humanoids work on that level yet。

 So we first need to make sure that these robots work。And then we can deploy them。

 and then we can deploy them massively， and we can ship， you know， Comp with these models。

 We can ship compute infrastructure with these models。

 We can even open up APIs for people to deploy to customize group on their own robots。

 But it's not there yet。 So it's more like mission driven research。



![](img/89f9160294a59b33a21df3a57207850f_203.png)

Okay， thank you。 one more quick question。 Yeah， As Janen mentioned。

 you guys partner with some of the big robot company， right human。

 what about like startup companies or research groups。

 Do you guys foresee having some collaboration with them？ Yeah。

 so many of the human companies are startups by themselves。 And， of course。

 we welcome researchers and students like yourself to join。 You have the link here。



![](img/89f9160294a59b33a21df3a57207850f_205.png)

Ill do a little bit hiring。 You have the link here。 Please feel free to apply， and I would love。



![](img/89f9160294a59b33a21df3a57207850f_207.png)

All the best talents in the world to join and gear and work with us on this moonshot。 sorry， I mean。

 just clarify my question， like for a research lab to embrace this infrastructure。

 do you think that's something you guys looking for。



![](img/89f9160294a59b33a21df3a57207850f_209.png)

You mean like kind of partnering with like we like we used infrastructure to accelerate robotics research。

 Yeah， I I think that is more case by case because for the humanoid robots themselves。

 like the hardware isn't super widely available yet。 So， but I'm open to talks。 I see。 Thank you。

 thanks。

![](img/89f9160294a59b33a21df3a57207850f_211.png)

![](img/89f9160294a59b33a21df3a57207850f_212.png)

Hi， Jim， first of all， even I'm waiting for the robot that come and clean the house。

 So looking forward to it and I'm going to ask you a very different question。

 I work a lot with the school district and high school students as one of my passion projects and I see continuously the divide between what students are taught and what the workforce is really needing and with this whole AI and robotics。

 the divide is increasing like leapfrogging So what recommendation do you have for the collaboration of the tech industry with the schools and how can what schools can do to prepare the students and I'm not talking even at the college level I'm more talking about specifically the four years of high school students and I can see a lots and lots of confusion and I bring a lot of sessions and conferences to them as well and love to invite you as well。



![](img/89f9160294a59b33a21df3a57207850f_214.png)

Yeah， so I， I think for。Kind of like high school students or like education in general。

 I feel that one thing good about AI right now is that the barrier of entry has been lower significantly right like any student middle school student whoever can just register for an L M account and then start using this API and build agents right。

 They can actually reproduce Voyager without using much funding。 we have the code open sourced。

 you can connect toviDSM API you can connect to open API it's all very accessible and doesn't cost too much。

 So I think like the barrier of entry is lowered to an unprecedented skill。

 When when I was a high school student， I did not even have access to computer science classes。

 I wrote my first line of code when I was a college student。And I feel that， you know， these days。

 things have changed。 and I would love to be young again and， you know。

 start kind of building from middle school using L O M APIs。 That's just the coolest time。



![](img/89f9160294a59b33a21df3a57207850f_216.png)

Yeah， thanks。 thanks。 Thanks a lot。 and love to have you over and with the students to learn from you。

 Thank you so much。😊，Hi Jim， thank you for the presentation。

 My questions about the physics in the beginning of your presentation。

 you mentioned that one of the future of the agent is to the knowledge of the world。

 could you elaborate that how how would you going to learn the physics from from this training because essentially you explain to us that the tax planning action can be emed into something like a G。

 but but the physics is very different。 So if you could elaborate that。 Thank you。 Yeah。

 so I think that is a very deep question I don't think we have we have a very clear answer to it。

 but this my take So I think training on lots and lots of videos。



![](img/89f9160294a59b33a21df3a57207850f_218.png)

And if you do a very good job at scaling up and doing it right。

 the model will be able to learn some kind of physics。 And we call that intuitive physics。

 And and that's what humans do as well， right， Like when we are going about our daily lives。

 we don't compute differential equations and accurate physics in our mind。

 So if I spell this water right now， I have no idea right。

 how each water molecule is gonna move right， I'm not computing that。

 But I I will know that I will make a mess。 And then Nathan over there will be very mad at me， right。

 that is intuitive physics。 I know roughly what the consequences will be given my actions。

 So I think models train on lots and lots of videos。 let's say a prediction model like so。

If you're predicting the future and if you're doing a good job at doing that。

 that means you you have to implement some kind of implicit intuitive physics engine in order to generalize。

 right you need to understand that when you drop a glass of water is gonna it's gonna break right like these kind of abstractions And I think like if you' are using these models for accurate physics。

 I don't think theyre gonna work。 But if you're using these models for robotics。

 I think it might be just the right data， because for the robots。

 they don't need to compute exactly all the water molecules， they just need to operate like humans。

 having intuitive understanding of how the world works and also learning kind of cause and effect from it。

 physics is also kind of causal reasoning。 So that's how I see kind of videos and these types of models will help robotics。



![](img/89f9160294a59b33a21df3a57207850f_220.png)

Thank you。 Yeah， thanks。Hi， Jim thank you for the presentation。

 Just a couple of question on your work that is inspiring us。

 The question is more related to your hybrid gradient。

 let's say framework is more for me like seamless to the reward free framework that is in the lecture how we can ensure that e will let's say discover skills that are different between the others。

 how Eric can help in finding new skills，  different skills between them in order to explore better to find new possibility find new possibilities。

 So I think the capability of eureka will also in some be determined by the foundation itself So eureka was built on G4。



![](img/89f9160294a59b33a21df3a57207850f_222.png)

And it was quite a while back。 I think G4 itself has been improved。

 and there's also like geri models and also cloud models。

 So which travel model is more kind of creative and more diverse。

 Eureka will just inherit that from the underlying model。

 So if the model itself doesn't have a lot of diversity。

 then it might just get stuck in some local minimum and not be able to propose new solutions。

 but at least in our know particular experiments in the paper where we do likex manipulation tasks for those tasks。

 I think eureka is doing a really good job in kind of searching in the function space。

 And actually we have a chart in the paper where we show that the reward functions that engineers is actually better than what human engineers can come up with。

 And as I said， like know human engineers have to do a trial and error and it's kind of a nightmare to do。

 So eureka automates that and does a better job。 But it doesn't necessarily mean it can excel in every domain。

 So it really depends on the。

![](img/89f9160294a59b33a21df3a57207850f_224.png)

Thank you。 Thank you， Jim， thanks。Hi， James， thank you for sharing about your mission driven research。

 I'm Da Wei from Columbialo Business School。 May I know what do you think about your biggest challenge for your research from the JE AR lab to the real world。

 Thank you。

![](img/89f9160294a59b33a21df3a57207850f_226.png)

So your question is about transferring kind of the research。 Yeah。

 what do you think will be the biggest challenge and what do you think will be the next step your focus on。

 Thank you。 The challenges， I think seem to real is really hard。

 So I do believe that if you train in 10000 simulations and if you do work in all of them。

 you will have a very good chance to transfer to real world。But in reality isn't always that simple。

 right it depends on many things。 One is the fidelity of the simulation。

 You still want the simulation to be as accurate as possible。

 or at least not make systematic mistakes in some critical areas and also the robot hardware itself can fail and the S to real the software can have box。

 there are many places that could go wrong。 But so far we have and also in the past works from research。

 we have a lot of success in S to real where we do something called domain randomization like you instantiate 10000 simulations and each one has slightly different physics coefficients like different gravity。

 different frictions And if your model is robust to all of these variations then it just generalizes all of box through real world。

 because the real world's gravity and coefficient， even though you don't know them exactly。

 they could be off by a little bit。 but your model is robust to a distribution of them So the real world is actually in distribution of your simulation。

And you can generalize。 But that would be the I ideal case。 And it doesn't always happen。

 So I do see seem to real as a critical challenge here。 That's one thing。

 And the second thing is no one has figured out how to solve robotics yet。

 If someone told you they they have solved robotics， you know， take it with a grain of salt。

 I don't believe that as as of this moment， anyone has figured that out。 So one critical problem。

Of robotics and why is it difficult is the data， right？ So for chargeGBT， as I said。

 like you can scrape lots and lots of internet text and you just scale up on them。

 But how do you scrape robot control data from the Internet。It does not exist。

 And that's just one simple reason why robotics is so much harder than something like G 4。Right。

How do you collect the data in this way。 So from our kind of gear labs roadmap。

 we're thinking about a combination of data， right， you need internet data。

 You need simulation data and you for sure also also need real robot data and each different sources of data have complementary strengths and weaknesses right So it's so much more complicated than just training like language models because you only have internet data。

 you don't have the other two sources of data to worry about。 But for robotics。

 you need to care about kind of the whole system。 So the data problem is a second critical challenge in addition to symmetry that I am seeing。

And the third is how to scale up。 And that's still tied to data problem， right， But like。

 even if you have all the videos on the Internet， what do you learn from it。

 Do you predict the next frame。And after you， so let's say even if you have a so model。

 how do you apply so model to a robotic stack， It's actually not clear at all。Why。

 because So model doesn't have action。 It doesn't come with actions。 It's text to video。

 but you want the actions out of it。 and actions are really hard。

Especially if you have dexterous hands in a humanoid。 The actions are really hard。

 So even if you have all the computing in the world， you have all the data in the world。

 How do you extract the signals of embodied agents from it is an unsolved problem。

So that's why I said gear is a mission driven research because there are so many things。

 but it is a critical mission that we cannot delay。



![](img/89f9160294a59b33a21df3a57207850f_228.png)

Thank you。 Thank you for sharing。Thanks。Sorry about that。 that was our last question。

 Could we give everyone here。 can give Jim a round of applause for that。 Thanks everyone。



![](img/89f9160294a59b33a21df3a57207850f_230.png)

![](img/89f9160294a59b33a21df3a57207850f_231.png)

Just a quick reminder that this session will be on demand post GTC if you wantan to review it。

 And the next session will be far as I talk with Bill Alley and Fe Fee。 Thank you。



![](img/89f9160294a59b33a21df3a57207850f_233.png)

Thank you for joining this session。Please remember to fill out the session survey in the GTC app for a chance to win a $50 gift card。

 If you are staying in the room for the next session。

 please remain in your seat and have your badge ready to be scanned by our team。😊。



![](img/89f9160294a59b33a21df3a57207850f_235.png)

了我是吧，还是。

![](img/89f9160294a59b33a21df3a57207850f_237.png)