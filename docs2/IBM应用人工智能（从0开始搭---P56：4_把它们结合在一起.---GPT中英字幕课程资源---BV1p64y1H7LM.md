# IBM应用人工智能（从0开始搭建AI机器人）｜IBM Applied AI （中英字幕） - P56：4_把它们结合在一起.zh_en - GPT中英字幕课程资源 - BV1p64y1H7LM

![](img/facb8d14b0867d751d8ff2f9fa820d03_0.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_1.png)

Welcome to the fourth module of How toBuild chatbots。



![](img/facb8d14b0867d751d8ff2f9fa820d03_3.png)

In this module， we'll finally address the third component of our dialogue skill。

 namely the dialogue itself。

![](img/facb8d14b0867d751d8ff2f9fa820d03_5.png)

The dialog component allows us to issue a response to the user based on the basis of their intent and the specifics of their request which we captured through entities we define It's great that our chatbot can detect and classify the user input。



![](img/facb8d14b0867d751d8ff2f9fa820d03_7.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_8.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_9.png)

However， so far， we haven't really replied to the user at all。

 we must be able to act on that correct classification by issuing an appropriate response。



![](img/facb8d14b0867d751d8ff2f9fa820d03_11.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_12.png)

When a user greets us， for example， we may want to reply back with，"H there， how can I help you？



![](img/facb8d14b0867d751d8ff2f9fa820d03_14.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_15.png)

The same is true for more complex queries， we must be able to use the fine tuneund classification that intents and entities enable us to do to provide an appropriate and accurate response to the user in this case they inquired about our Toronto store hours。

 and the response would reflect that and contain the information the user is looking for。



![](img/facb8d14b0867d751d8ff2f9fa820d03_17.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_18.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_19.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_20.png)

A dialogue is simply a tree of nodes， and each node will typically handle one particular scenario。



![](img/facb8d14b0867d751d8ff2f9fa820d03_22.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_23.png)

For example， here we have three nodes， the first one is welcomelcome。

 which handles the chatbot prompt， in other words， our greeting when the first user arrives。



![](img/facb8d14b0867d751d8ff2f9fa820d03_25.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_26.png)

Then we have a greetings node to respond to the user greeting U。



![](img/facb8d14b0867d751d8ff2f9fa820d03_28.png)

And finally， we have a special fallback node that will notify the user that the chat bot wasn't quite sure about what the user was asking。



![](img/facb8d14b0867d751d8ff2f9fa820d03_30.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_31.png)

Welcome and anything else are two default nodes created for you when you first create the dialogueog for your chatbot。

 Any node youll define will sit in between these two。



![](img/facb8d14b0867d751d8ff2f9fa820d03_33.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_34.png)

But let's take a quick look at what a node might look like。 You'll want to give each node a name。

 Watson doesn't really care about the node name， but it's useful to us。

 the chatbot designers so that we can more easily organize and work with our nodes Next we'll have a condition that determines when the node should be executed。

 In this case， the node will be executed if the greeting's intent is detected in the user input The condition can be as simple as this or complex logical expression In most cases it will test against an intent entity or a combination of them。



![](img/facb8d14b0867d751d8ff2f9fa820d03_36.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_37.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_38.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_39.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_40.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_41.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_42.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_43.png)

Then we have the response block， where we finally get to decide what to reply back to the user。



![](img/facb8d14b0867d751d8ff2f9fa820d03_45.png)

In this case， a simple， high there， how can I help you will suffice？



![](img/facb8d14b0867d751d8ff2f9fa820d03_47.png)

This response block has many， many options， in fact the response doesn't even have to be text。

 it could be an image or some options for the user to choose from we can provide multiple response variations and then decide if they should be issued in the order they appear every time this note is executed or randomly from the list we provide。



![](img/facb8d14b0867d751d8ff2f9fa820d03_49.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_50.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_51.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_52.png)

We can even have multiple responses where we attach a condition to each individual response within the same node。



![](img/facb8d14b0867d751d8ff2f9fa820d03_54.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_55.png)

This is a great feature and will definitely take advantage of it in the labs of this course。



![](img/facb8d14b0867d751d8ff2f9fa820d03_57.png)

Finally， we get to specify what happens after we issued a response。



![](img/facb8d14b0867d751d8ff2f9fa820d03_59.png)

Typically we just wait for the user to say something else， and that's why that's the default action。

 however， other options are available， including the ability to jump to other nodes within the dialogueog。



![](img/facb8d14b0867d751d8ff2f9fa820d03_61.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_62.png)

This is a feature that will be useful in more complex chatbots。

 but can lead to chatbots that are difficult to reason about if you abuse it。



![](img/facb8d14b0867d751d8ff2f9fa820d03_64.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_65.png)

The execution is evaluated from the top to the bottom of the dialog。

 so when the user submits their utterance， the first node will be evaluated for execution。



![](img/facb8d14b0867d751d8ff2f9fa820d03_67.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_68.png)

If the condition is not met， we'll move down to the second node。



![](img/facb8d14b0867d751d8ff2f9fa820d03_70.png)

If this one doesn't meet the criteria either， we'll consider the third node and so on。



![](img/facb8d14b0867d751d8ff2f9fa820d03_72.png)

Essentially we continue to evaluate nodes in the order they appear。

 while the conditions of these nodes are false。

![](img/facb8d14b0867d751d8ff2f9fa820d03_74.png)

We stop at the first node whose condition matches the user input。

This is why it's important to have that anything else fallback node at the very bottom。



![](img/facb8d14b0867d751d8ff2f9fa820d03_76.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_77.png)

That node has a special condition that is always true whenever all the nodes above it fail to execute。



![](img/facb8d14b0867d751d8ff2f9fa820d03_79.png)

It ensures that we have a reply for the user， even if it's a simple， I don't understand。

 could you try rephrasing。

![](img/facb8d14b0867d751d8ff2f9fa820d03_81.png)

Likewise， this is why we have the welcome node greeting the user at the very top。



![](img/facb8d14b0867d751d8ff2f9fa820d03_83.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_84.png)

That node has a special welcome condition that is only true at the beginning of the conversation with the user。



![](img/facb8d14b0867d751d8ff2f9fa820d03_86.png)

By placing it up top， we ensure that it's executed prior to any other node being considered。



![](img/facb8d14b0867d751d8ff2f9fa820d03_88.png)

The fact that the condition is only true once ensures that we don't keep greeting the user every time we evaluate their input。



![](img/facb8d14b0867d751d8ff2f9fa820d03_90.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_91.png)

Nodes can also have children nodes， and there are situations in complex chatbots。

 where employing this feature enables us to create a more nuanced chatbot。



![](img/facb8d14b0867d751d8ff2f9fa820d03_93.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_94.png)

Children nodes are considered for execution only after the parent node has been executed unless some other node in the dialogue explicitly jumped to a given child node。

 children nodes are then also executed top to bottom。

 and we stop executing at the first child node that meets the condition Watsson assistant introduced many cool new features that actually allows us to rely less on children nodes。

 greatly simplifying our dialogue design。

![](img/facb8d14b0867d751d8ff2f9fa820d03_96.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_97.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_98.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_99.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_100.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_101.png)

By the end of this course， you'll become familiar with both children nodes and the simpler alternatives you can commonly use in many scenarios。



![](img/facb8d14b0867d751d8ff2f9fa820d03_103.png)

![](img/facb8d14b0867d751d8ff2f9fa820d03_104.png)