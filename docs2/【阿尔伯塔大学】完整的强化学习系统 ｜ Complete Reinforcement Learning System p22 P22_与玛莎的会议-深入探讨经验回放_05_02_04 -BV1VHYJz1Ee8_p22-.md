# 【阿尔伯塔大学】完整的强化学习系统 ｜ Complete Reinforcement Learning System p22 P22_与玛莎的会议-深入探讨经验回放_05_02_04 -BV1VHYJz1Ee8_p22-

嗯。In Cose3， the agents you implemented update the value function or policy only once with each sample。

 but this is likely not the most sample efficient way to use our data you have actually seen a smarter approach in course2 where we talked about Dynina as a way to be more sample efficient。

But we only talked about Dah for the tabular setting。

In this video we will talk about how to make your agent more sample efficient when using function approximation。

 we will discuss a simple method called experience replay and how it relates to Dynina。

To get some intuition for experience replay， let's first remember a method that we know well。

 Dine a Q。The idea is to learn a model using sampled experience。

 then simulated experience can be obtained from this model to update the values。

This procedure of using simulated experience to improve the value estimates is called planning。

To focus on the key ideas in DynA， we made a few simplifying assumptions， namely。

 DanneQ assumes deterministic transitions for a relatively small state space。For this setting。

 learning the model was simple； for every visit is date actionction pair。

 we record the observed reward in next date。This only works in the tabular setting where the number of state action pairs is small enough to fit into computer memory。

If we were to attempt this in a continuous state domain。

 we would have an infinite amount of state action pairs to store； worse than that。

 we will not see the same state twice if the world is stochastic。

One option is to learn a model using all your new knowledge about function approximation。

 for example， you can learn a parameterized function that inputs states and actions and outputs next states and rewards。

Unfortunately， even small errors in such a learn dynamics model seem to cause serious issues。

 it remains an open research question how to effectively use learn models in an R agent。Fortunately。

 there is a simpler option for your capstone。Experience replay is a simple method for trying to get the advantages of Dina。

The basic idea is to save a buffer of experience and let the data be the model。

We sample experience from this buffer and update the value function with those samples。

 similarly to how we sample from the model and update the values in Dynina。

The key choices for experience replay are the size of the buffer， what experience to store。

 and how many updates to execute per step。Let's first take a look at how we store the experiences for simplicity。

 let's go back to the tabular grid world。As we interact with the world， we observe a state action。

 reward， next state tuple。We add these experiences to a buffer that we'll call the experience Re buffer。

As we continue interacting with the world， we add more samples to this buffer until we eventually fill it up。

When this happens， we can pick an older experience to delete and replace with a new experience。

We also need to consider the size of our buffer。By allowing the buffer to be really large。

 we can remember potentially useful transitions from many time steps ago。However。

 the agent does have practical limitations， we will need to consider the amount of memory used by large buffers and any computational impacts from storing and accessing large buffers。

Once we have decided to store a buffer， a natural idea is to use mini batches using a single sample from the experienced replay buffer can produce a noisy update。

 instead we can use several samples from the buffer to create an average update to reduce that noise。

The small collection of samples from the larger buffer is called a mini batch。

The mini batchch updates simply involves averaging the updates across the K random samples in the mini batch Here's an example Comp this average update for Q learning。

We store the average update in a variable， let's call it Ubar。

Then we grab several samples from the buffer and compute the Q learning update for each sample finally。

 we average those updates to get the mini batch update。Putting it all together。

 we get the following pseudocode for experience replay。

As in DynA we can think of the planning steps occurring in the background the agent can perform several of these planning updates。

 which are the replay updates per each real step in the environment more updates means we extract more from the data we have observed。

Each of these replay updates consists of a mini batch update to reduce the noise of that update。

And that's it experienceience replay allows the agent to make better use of its data and so be more sample efficient Further it makes sure that the agent is updating in many parts of the environment just like in Dina this week you will see how to use experience replay within your agent。

