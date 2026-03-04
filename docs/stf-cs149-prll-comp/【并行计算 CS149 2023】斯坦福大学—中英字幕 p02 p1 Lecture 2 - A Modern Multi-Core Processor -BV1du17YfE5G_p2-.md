# 【并行计算 CS149 2023】斯坦福大学—中英字幕 p02 p1 Lecture 2 - A Modern Multi-Core Processor -BV1du17YfE5G_p2-

![](img/9be0983c46a7ddc10da75418d0f65d45_0.png)

So let， let's get going from a review from last time because， you know， some， sometimes it's， it's。

 it's good to， to page back in what we learned。

![](img/9be0983c46a7ddc10da75418d0f65d45_2.png)

![](img/9be0983c46a7ddc10da75418d0f65d45_3.png)

Okay， so I asked you a couple of trivial questions。 One of those questions was。

 what is a computer program， And really， I meant， what is a computer program。

 as we're gonna think about it in this class from the perspective of a computer。

So what was a computer program？

![](img/9be0983c46a7ddc10da75418d0f65d45_5.png)

It's in the habit of just shouting out things that are， you know， maybe even obvious。

 And it'll just keep the。So a list of instructions。 or if you want even， you know， I could ask you。

 what's an instruction， you know， if we want to be more abstract， It's just， it's a list of commands。

 A program is a list of commands telling the machine you will do this。 You will do that， right。

 So its， you know， I have here the slides of a list of processor instructions At the end of the day。

 This program text turns into a list of commands。😊。



![](img/9be0983c46a7ddc10da75418d0f65d45_7.png)

![](img/9be0983c46a7ddc10da75418d0f65d45_8.png)

对。Allright， and。What did a processor do？Given a list of commands， what does a processor do。

It executes those commands。 I'll give you that one。 But when we talk about executing the commands。

 what are the effects of those， those commands。 What do they do。



![](img/9be0983c46a7ddc10da75418d0f65d45_10.png)

Modify state， and we talked about two types of state， right， we talked about registers。



![](img/9be0983c46a7ddc10da75418d0f65d45_12.png)

And we talked about main memory。Right。So this processor， it executes instructions。

 I gave you this really simplistic notion， just just enough detail to help us think about it is like it's useful to think about there's components of the processor that are about control。

 given the program， What do I do next， Like what's the next operation。 or if there's like a branch。

 where do I go next。 I typically， I just have that as my orange boxes here， fetch and decode。

 And you have a part of a processor。 Some of the hardwares actually responsible for doing stuff。

 So I'm calling that the execution unit。 And we have two forms of context。

 We have the register state of the processor。 and then not shown on the diagram。 We have memory。😊。

And my simple processor last time was going to execute one instruction every clock tick making progress。

Right？But then we said something else， we said， well， if we look at the instructions in a program。

 if we look at those instructions。And this was a larger program。We can take a look at them and say。

 you know， not all the instructions depend on the previous one in the sequence。

So this was a sequence where I really recommend that you。

 you go offline and confirm to yourself that if these are the numbers of the instructions and I'm representing those instructions as a node in the graph。

 there are certain dependencies， I have to do instruction 2， for example， you know。

 after I do instructions 0 and1， because I I can't add two numbers if I haven't brought them in for memory or something like that。

😊，And so we said that， you know， in the same way that you could look at this program and go。

 I know I'm supposed to get an answer。 that's the same as if I ran these all and serially。



![](img/9be0983c46a7ddc10da75418d0f65d45_14.png)

But if I had extra resources sitting around， I can do some of these things in parallel without really telling anybody that I change the order。

 and they'll never know All they'll see is that this program goes a little bit faster。



![](img/9be0983c46a7ddc10da75418d0f65d45_16.png)

And so this， we talked about this one idea last time of， of superscalealar expectation。

And if you break down the word， you know， it's kind of a weird word term。 But if you think about it。

 it's like scalar execution， which is like doing one thing at a time。

 And then the super scalear is kind of like a a fancy， you know， like technical term for say。

 we're actually doing a little bit more than that。 But your program is still saying I'm doing one thing at a time。

😊，So it's something that's going on under the hood。 So this was the first thing that we。

 we talked about where there was a little bit difference between the abstraction。

 the meaning of a program。 A program is a list of instructions and says if you perform these operations on this state at the end of the day。

 you should get this answer。

![](img/9be0983c46a7ddc10da75418d0f65d45_18.png)

Then there's the implementation in a modern processor that says， we。

 we can do them in a little bit different order。 It'll be better for you， and you'll never know。

So that was a little bit what we talked about with processing。

We also talked a little bit about memory。 and I asked you what was memory。 So in the same way。

 if I ask you， what is a program， it's just a list of commands where those commands modify state in a machine。



![](img/9be0983c46a7ddc10da75418d0f65d45_20.png)

![](img/9be0983c46a7ddc10da75418d0f65d45_21.png)

What is memory。Yeah， memory is just  theologically， abstractly， it's just an array of bytes。

It's part of that state for that program。 And if a program says。

 please read the value and address 42。Memory says， well， address 42 has some value。

 And sure I'll give you that value。If a processor says write the value to address， know。

 write the value fu bar to address 42， well， everybody says， okay， I'll take in that value。

 and I'll put the value fo bar there。 Okay so we talked about memory just being a big array of bytes。

But we didn't talk very much about。 Oh， right。 And I even showed you， you know， like， okay。

 but we didn't talk very much about implementation。 So notice I'm setting this up over and over。

 there's what something means it's semantics。 like， add these two numbers。

 then add those two numbers。 or there is an array of， of addresses and every address has a value。

 And then the underlying implementation of that。Okay， so if I tell you memory。

 many of you might say the word D Ram or remember， you know。

 a big stick of memory that you might have shoved into a laptop at some time or or something like that。

 right， And so what a D Ram chip does is， is it provides。

 It's the implementation of this abstraction。 You send that D Ram chip a command It says。

 give me the value that stored at address， You know， Hex B。 And this memory chip will send 2，55 back。

😊。

![](img/9be0983c46a7ddc10da75418d0f65d45_23.png)

![](img/9be0983c46a7ddc10da75418d0f65d45_24.png)

But we talked about last time how it could take a while to go get that message out there to memory and come back。

And so， all modern systems have。Some form of， of a cache。

And this cache is another form of storage That's part of the implementation of memory。

But if the processor says， I need address 4。Well， that value might be stored in cash。

 And it can get the answer much， much faster。So that was kind of right where we left off last time。

Any questions？Just trying to， you know， like I often overlap just a little bit because it's good。

 Yes， Sir。

![](img/9be0983c46a7ddc10da75418d0f65d45_26.png)

😀H。😊，dynamicy Ramm， just dynamic ram， and it's dynamic in that if you cut the power。know。

 as opposed to something that's persistent， like SSD or method。Okay。That's true。

 Even reading a value， it destroys the， destroys the value。 when you read a value。

 you actually got to put it back。 Otherwise you lose it。 But for fun。

 we actually have 30 minutes on D Ram very， very much at the the end of of class。 But for now。

 you should think about it as it's far away。😊。

![](img/9be0983c46a7ddc10da75418d0f65d45_28.png)

![](img/9be0983c46a7ddc10da75418d0f65d45_29.png)

And since it's far away， it's like it's standing in the back of the room or it's storage in your garage or something like that。

 If you w to go get something there， it's gonna take a little bit。

 And you should think about the cash is like， what's right on my desk。So these。

Don't think about implementation。 They're just addresses。 I have something。 you know。

 I have this concept。 I have memory。 Memory takes a value address。 It gives you a value。



![](img/9be0983c46a7ddc10da75418d0f65d45_31.png)

D Ram is one way to implement that。 A cache is gonna be another one a way to implement that。

 And this' something we haven't stressed very much in the class in previous years。

 And so this is kind of we're， we're trying to set the stage a little bit more this year。

 So there's two kind of details of how a data cache works that are kind of useful， to think about。😊。



![](img/9be0983c46a7ddc10da75418d0f65d45_33.png)

One is， even though memory says if I， if you give me an address， I'll give you a value。

The underlying implementation in any modern system that I know about will move data from memory into the cache。

At some larger granularity of cache lines。 So in this figure。

This cache holds data for two cache lines。 Each of those cache lines is 4 bys。

So the bys store you know， beginning at address 4。 So 4，5，6，7。

 These are the values out in memory that are replicated in the cache。

 You should be able to confirm that if I did not mess up my figure， right，0，0，6，0。 Okay。

 so this is a cache that has the ability to replicate 8 B。

 It's organized into  two cache lines of 4 B each。And what I'm highlighting in red is sort of the the place in the address space that corresponds to these two cache lines。

 I've seen a bunch of questions。 Yeah， address。

![](img/9be0983c46a7ddc10da75418d0f65d45_35.png)

Will we just the next is。 Yeah， good question。 Think about you're gonna access and move data from off。

 you know， from D Ram memory onto the chip in the granularity of 4 B rooted at address mod 4。

 So if you want address 5。 the actual command out to memory is give me the cache line of 4。😊。



![](img/9be0983c46a7ddc10da75418d0f65d45_37.png)

Yeah。Yeah。Do different execution units have different caches or is No I going to answer the question just yet I just want everybody to learn it for one processor just yet absolutely yes。

 but and you probably already thinking about how the heck if I replicate data all over the place。

 how do I keep things consistent， you are correct， but not today。



![](img/9be0983c46a7ddc10da75418d0f65d45_39.png)

Keep the Ram so far away。Why not put a garage on my desk？



![](img/9be0983c46a7ddc10da75418d0f65d45_41.png)

Go。

![](img/9be0983c46a7ddc10da75418d0f65d45_43.png)

Yeah。Maybe you could explain one more time to update what cashline definitionly and so what is memory？



![](img/9be0983c46a7ddc10da75418d0f65d45_45.png)

Memory is an address space and a value at every address。Somehow， we have to implement that。

So somewhere in the system， I need to have storage for every address。And typically。

 that is your off chip memory these days。 Okay， O， now。

 a cache is just keeping a copy of this information。Right on my desktop。😡，Okay， now。

 the organization of， of almost any modern cash， any。

 anything you get on any chip that you're probably gonna run。

Is that data is gonna move between memory and the cache at the granularity of lines。

 So on an Intel chip， that's a 64 B cache line on my diagram。

 It's a 4 B cache line because I didn't want to draw 64 numbers。😊。



![](img/9be0983c46a7ddc10da75418d0f65d45_47.png)

And so if you want address5 in myC。You're gonna go ask memory。

 give me all the information for the line starting an address for。That makes sense。



![](img/9be0983c46a7ddc10da75418d0f65d45_49.png)

And Im going next slide， I'm going to get into why we work at granularity too。



![](img/9be0983c46a7ddc10da75418d0f65d45_51.png)

The starting address from which you take things is basically always multiples of gold or multiples of。

we're gonna work that great because we don't want to have a dynamic allocation situation here。

 this is gonna be hardware。 you know， the whole point is to be able to access。

 like when this processor says I want address 5。 and we say load address 5。 Okay here。

 let's think about this。 What happens if the cash if the processor says I want to load address。

 actually， I'm gonna go something else address。 Yeah， let's say address 5。😊。



![](img/9be0983c46a7ddc10da75418d0f65d45_53.png)

Conceptually， it's asking memory。Please give me the value at address 5。

 But what it's first going to do is it's going ask the cash， Hey， do you have address 5。

And the cache is gonna go， yeah， I do。 actually， It has value 0。

RightIf the cache doesn't have the value， now we're gonna to go get it。

And on the cache iss gonna ask memory， hey， can I get the line that contains5。

And that's when those four values come in in this case。 So let， let's think about it in a。

 in a slightly， you know， richer situation is what we're going through right at the end of class。

 In class。 Nobody knows， you know， everybody's tired。 Nobody remembers anything anyways。

 So we're doing it again。 Okay， so here is the value of memory。😊，Notice that I'm。

 I'm really saying memory。 and I'm not saying D Ram or any implementation。

 even though almost all of us， if we say memory and computer architecture。

 we're probably thinking about off chip stuff。 Okay， so this is just the state。

 This is the state of my program， these values。 And here is a list of an addresses that my program is gonna access。

😊，So it's gonna be like， I'm gonna add access address 0， then address 1， then address 2 in time。Okay。

 and what I'm gonna show here is what is the cache doing in response to those processor actions。



![](img/9be0983c46a7ddc10da75418d0f65d45_55.png)

So let's say that the program says， please load the value at address zero。

And let's just start from the place where there's， there's nothing in the cache or everything is sort of invalid in the cache。

 Well， the cache is gonna go， hey， wait a minute。 I don't have that value。

So it's gonna go ask memory for， for a cache line or D Ram for right， So。

 and these are my cache line。 Sorry， I didn't。 I didn't draw up for you。 right， So when we say， hey。

 I need address 0。

![](img/9be0983c46a7ddc10da75418d0f65d45_57.png)

The cashka， you never asked me for that before。 Why would I have it。

This term called so it's a cache miss。 The value is not in the cache。

 And if you read a computer architecture textbook， they， they taxonomize the reason for these misses。

And so in this case， you know， I， I wrote on the slide cold Miss because like。

 we have never even touched that data before。 There's really no reason it should be in the cast。

 Like， you know， so the the idea is that the data is cold compared to data that's hot that you're often accessing。

 the。

![](img/9be0983c46a7ddc10da75418d0f65d45_59.png)

Okay， so notice what happened in the cache state。 The cache now has one valid line in it。

 and it's the line beginning at address 0。So that may have taken a while。

 There might be some real latency in that operation。Now。

 what happens when the processor says in some later instruction。Sometime later in the program。

 the cache hasn't changed。 Nothing's changed。 It's done no other memory And says， you know what。

 I want to read address 1。What was the cache day？It was like I got address one， that's a hit。

 nothing happens， right？So that can potentially be really， really fast。

 And the same is gonna happen for 2，3。And then what happens if I go back to 2。We're good。

 it's another hit， one， another hit， four。Don't have that。 That's got to get brought in。 And now。

 my cache in this example has capacity for two lines。 So we'll just put that other thing in。

 When I go back to one， what happens。I'm good。 exactly。

 So one thing I want you to to take away from this slide is actually。

 the cache is sort of solving two problems at the same time。The。

 I'm actually Im gonna go to the second one first。 The one that I've kind of set this up for is if you've already touched data。

 if you've already accessed data。The cache has it， which means all subsequent accesses will be faster。

So in general， that like one of the big reasons for a cache is that if I'm touching stuff a lot。

 the paper that I'm working on right now， the homework that I'm grading。

 that's why I keep it on my desk。 I don't take it to the garage every single time。 I， you know。

 wanna， wantan to look at it。

![](img/9be0983c46a7ddc10da75418d0f65d45_61.png)

![](img/9be0983c46a7ddc10da75418d0f65d45_62.png)

So that's this notion of temporal locality， back to back a in time。



![](img/9be0983c46a7ddc10da75418d0f65d45_64.png)

That data is sitting there。 So that's what it's helping me with。 It's prevent， you know。

 preventing me from going out and looking at it。 The other thing that you might have noticed is that this granularity of operating at the granularity of lines。

😊，First of all， bulk transfers are almost always efficient。

So I can transfer data efficiently to the cache。 But it's based on the assumption that if I if I access address 0。

 oftentimes programs then go access 1，2 and 3，2， because they're like running right down an array。

 for example。So there's actually two forms of the way reducing latency here。

 One form is almost like the line is functioning as a prefetch for the next items in the。

 in the array。

![](img/9be0983c46a7ddc10da75418d0f65d45_66.png)

![](img/9be0983c46a7ddc10da75418d0f65d45_67.png)

The second one is， by bringing the data in now， I'm assuming you're probably going to touch it again。

Like a common thing would be to read something， do some logic， and then update。

So there's already two memory accesses。Now， I want， I want to throw out one more pattern for you。

 which is kind of interesting。 Same cache。

![](img/9be0983c46a7ddc10da75418d0f65d45_69.png)

And now all I'm gonna do is I'm going to read write down an array。

 noticeice that the addresses are just increasing by a byte every time。



![](img/9be0983c46a7ddc10da75418d0f65d45_71.png)

Except I am， yeah， okay。 so let's， let's just do this。 So hit。



![](img/9be0983c46a7ddc10da75418d0f65d45_73.png)

![](img/9be0983c46a7ddc10da75418d0f65d45_74.png)

Right， hit， hit， hit。 Now what happens。Miss， good， hit， hit， hit。But what do I do？My cash is full。

So now we got to throw something out， right？ And and last time I told you that we're gonna take're in this class。

 we're gonna assume a very， you know， simple policy of least recently used。

 There some questions on a website about this。 So the line that I have touched least recently。

 the longest time ago。 is the one that I'm least likely that's the assumption to touch again。

 And in this case， what color would it be。😊，It's red， so we're going to drop red and bring in green。

So this is a cold miss on green， right， because I've never touched green before。

It first I' going to touch this data。So， this will continue。H， then we get to address 12 or hex C。

It's another cold mess， and we got to throw out。Blue。Exactly。This question somewhere， yes。

IIn computer architecture is in this call the capacity miss since you're throwing something out。 No。

 this is， this is a cold miss。 It's the first time you've touched the data。

 The name of the myth is relative to the data that I'm accessing。

 I have like if we would have had an infinitely sized cache。😊，I still would have missed here， right。

It's first time I touched it。But your question is relevant now。Your question is relevant now。

 So what happens when I go back。Yeah， I will yeah。😊，So， so here， look what's happened。

 I have already accessed address 0 right at the very beginning。

If I had an infinitely large cache or arguably a cache that could have that could store 16 B。

 that would have been a hit。So that's a myth that occurred because of actually。

 I even got that wrong。 That's a capacity miss。 Sorry， a little。One second。Yeah， my bad。Yeah。

 so this is a myth that occurred only because a cache has a finite size。

If I could have put my garage on my desk， I would have been， you know， hitting。

 hitting on everything。You asked me about a capacity miss。

 a capacity miss is actually a miss that we will not talk about in this class。

 but comes from the fact that the cache might have been big enough。

 but the organization of where data goes doesn't allow the data to still be there。

 So we'd have to talk。カフ。Oh， sorry， yeah sorry。 yeah， sorry。

A conflict miss is one where the organization of the cache means that like， hey。

 I could have put it somewhere if I could have put any data anywhere in the cache。

 but increasingly large caches tend to have policies that say this data can only go here and this data can only go here。

😊，有。Besides to change the names， is there anything different cost for business than we are？

There's only no。 I mean， the， the， the the name is， is， is giving you a reason。And， and really。

 if you， yeah， if， if you think about it as so when you evict something， when you evict a line。

 your behavior will be different based on whether or not that line has been written to。

 because if it hasn't been written to and only read， you just toss it。 If it has been written to。

 you got to push that data back out to memory。 So that's the biggest difference。ますご。反我。



![](img/9be0983c46a7ddc10da75418d0f65d45_76.png)

So we got zero， one， two， three， four， and then we did it zero5。



![](img/9be0983c46a7ddc10da75418d0f65d45_78.png)

たちもかしろ。我I wonder。9 three line。so and this would be a good thing for you to just work out。

 but what I do want to say is this is similar to the earlier question。

 the mapping of cache lines to addresses。That， that is fixed。 like like， you know。

 like a cache doesn't even think about addresses really。 It thinks about cash lines。

 And so I've just divided my address space up into these cache lines。 mod cache line size。

 So if you decided to go， I want to read 0，1，2，3，5。😊，5 would trigger a load of the blue cash line。Y。

 so what you've done is you've actually reduced the spatial locality of your aes。 So if you did 0，1。

2，3，5，6，7，8，10。😊，You just would be loading four values in this case。

 the cash line and never touching one of them。Right。

 so you're incurring memory traffic or communication that you didn't need。

 but that's just the way the underlying implementation works。



![](img/9be0983c46a7ddc10da75418d0f65d45_80.png)

Okay， I'll take two more questions， and I'll keep it keep it moving。 Yeah。

 I'm wondering if you could say a little bit more about the difference between the conflict I'd rather not now actually。

 I don't believe that anybody has had any kind of set of sociivity or or that kind of stuff。

 So I yeah， I'm not。 you're asking questions about how to design real caches now。 And yeah， maybe。

Combo。When we talk about capacity this and important good。

The processor doesn't know it was capacity doesn't matter。 Yeah， maybe maybe in hindsight。

 maybe I should just said this but but for the sake of the classes of this， either way。

's I don't have the data， I've got to go get it and I need to invoke my eviction policy to figure out who's leaving。

😊。

![](img/9be0983c46a7ddc10da75418d0f65d45_82.png)

![](img/9be0983c46a7ddc10da75418d0f65d45_83.png)

有嗯。The reason for that doesn't matter。The only thing that the reason matters for would be like。

You might be able to like， if you knew the reason， you might be able to change your program a little bit to to。

To avoid the mess。All good， all right， last one。Sure what's the overhead for？

And if there's a significant oversight， isn't like a ratio of like load like that you need in order for to be like knowledge。

 We're going slowly graduate towards all that because the reason why I'm spending all this time on of cash is is for those kind of reasons。

 But the main thing that I want you to take away is that。



![](img/9be0983c46a7ddc10da75418d0f65d45_85.png)

![](img/9be0983c46a7ddc10da75418d0f65d45_86.png)

Cashs exist。Theyre an implementation detail。 If I took the cache out of a computer。

 you would get the same results。It just may run slower。Right， that's。

 that's the most important thing。And the caches exist to reduce the latency of memory access。



![](img/9be0983c46a7ddc10da75418d0f65d45_88.png)

So that this processor is not waiting。 Now， under the hood。

 if I had to elaborate a little bit more in the same way that like， I have a desktop。

 a filing cabinet， a hallway closet in a garage， and I put different stuff in those different storages based on how often I might need them。

 Most modern computers have a hierarchy of various caches。

And I think a reasonable rule of thumb is that if some， if a unit of storage is bigger。

It is farther away and has higher latency to access。

And we'll also talk about how it actually has higher energy to access and stuff like that。

 but for example， if you rip open most modern machines。

 you usually see like a L1 cache that's pretty small。

 a few kilobytes right next to the processor that can be accessed in a few cycles。



![](img/9be0983c46a7ddc10da75418d0f65d45_90.png)

![](img/9be0983c46a7ddc10da75418d0f65d45_91.png)

If you miss the L1， you'll ask the L2， if you miss the L2， often you'll see an L3。

 and if you miss the L3， you'll go out to DRA。 and this is something I showed you to finish class up。

 You ask that you started a hint about what are the consequences of missing。

So these are all this graph is to scale of the number of cycles a few years ago now on Intel CPUs that it took。

 If you issued an instruction， how long would it take to get the data And an L1 cache hit was about four cycles。

Ppeline。 So you can， you could actually really cover that。 No， you know， like， if I。

 if I did it in animation， thought that fast。If you get it out of the next level of cash。

 it's going to take a little bit longer。The next level of cash is gonna take a little bit longer。

 And if you miss this cache hierarchy， you're waiting。You're definitely waiting。

 So consider a system that's like， load， do some math， load， do some math。

 We're worried about using four cores， getting a 4 x speed up。 And if you get your memory wrong。😊。

You could potentially be off by a factor at 2，50。So the scale of these effects that deal with data movement are enormous。



![](img/9be0983c46a7ddc10da75418d0f65d45_93.png)

Okay， so I want you to just， that's， that's like us finishing up last time。 Yeah one question。

You' are taking it from and that。Well， that's the latency I'm talking about。



![](img/9be0983c46a7ddc10da75418d0f65d45_95.png)

Like like think about it this way is if the data is in DRA and the processor says I want address X。

 let's think about the， you know moving it from DRA into the L3， bringing it from the L3 to the L2。

 L2 to the L1 all the way to the processor， that's 250 I there way to bring。There are ways。 Yeah。

 there are ways。 There are， there are instructions， you can say， is read this data。

 And I want you to bypass all the caches。 I don't think there're as much about reducing latency as they are about not plotting your caches。

 I， I think I don't， I have a feeling like it actually probably go through the whole path and then just doesn't get stored would be how I would implement it。

 I guess if yeah。😊。

![](img/9be0983c46a7ddc10da75418d0f65d45_97.png)

Okay。Oops， shoot。All right， I'm going to reemphasize this。

 but apparently Keynote won't let me go through until the animation is done。😊，Yeah。

 while we're waiting， yes。Good。Or simply just read the data and you win instead of just。いア。Yeah。

 that was the question here is like， are there really any benefits on a modern system of bypassing the whole thing。

 they're not going to be latency benefits。

![](img/9be0983c46a7ddc10da75418d0f65d45_99.png)

They're not going to be。

![](img/9be0983c46a7ddc10da75418d0f65d45_101.png)

Okay， so I wanna， I wanna， let's put memory aside。 It's coming back at the end of the day。



![](img/9be0983c46a7ddc10da75418d0f65d45_103.png)

But now let's go back to processing a little bit。 So the rest of the lecture is going to be talking about kind of three major ideas。

On parallelism on how we start adding more and more capability to do more stuff into a machine。

And we're going to come full circle and end up saying some of these ideas。



![](img/9be0983c46a7ddc10da75418d0f65d45_105.png)

Are about combating this latency problem。 So I already gave you caches as one way to combat the latency problem。

Okay， and then so here's an example program。 and I'm gonna to use is the running example for the next 50 minutes or the next 47 minutes。

 Okay， this is some some straight line C code。 Take a look at it。 make sure you know what it does。

 what it does is it takes this input and array X。 It reads values， n values from the array X。

 It writes n values to the array Y。 and what it does is for every input value X。

 It computes the s approximates the s of x。 given a numerical approximation using the Taylor expansion。

 So like how it computes the sine of x doesn't matter。

 The only thing that matters is really you look at the C code。 You go， okay。

 I've got a piece of C code for I equals sorry outermost for I equals 0 to n for every input element perform a computation that ultimately computes value and is stored to the output element。

😊，The the inner for loop is just an iterative algorithm to approximate sign。So what。

 what this is doing doesn't really matter。 You could just think about this as some function that takes this input X sub I and outputs sine of X sub I。

Any questions about the code as I might need any， more time to Okay。

 so that's all I want you to think about。 And， and， you know。

 my illustration on the right just shows you all the input values of x and and the output values of Y。

 okay。So it just does that。Okay， so if we compile this program， we want Kang or GCC。

 pick your favorite compiler， we're gonna get out a sequence of instructions， right。

 for this program。😊，And I want you to kind of focus on the sequence of instructions that's the basic block inside the for loop。

So at the moment， we're going to think about， there's a sequence of instructions that says once I load X sub I。

 here's all the stuff I have to do to produce the value that is then stored to y sub I。And now。

 given that sequence of instructions， we， we're gonna execute it。 right， Like。

 so that sequence of instructions， the processor is gonna say， okay， what's the next one。 Oh。

 it's a load to this value。 Then there's a multiply and so on and so on。

 It'll run those instructions。 It'll produce a value。 And then at some point at the end of that。

 there will be a store instruction， which to store this value to the address given by X of I。😊。

And just to repeat myself， if that processor is smart。It might look into that program。

 into that instruction sequenc and go， yeah， there's some of those instructions that can be done in parallel。

 right， Let me back up and let's look at it， like。嗯。We， we certainly can find some stuff， right。

 like this computing the numerator。Is independent of computing the denominator， right？

 So there's a little bit of instruction level parallelism there。

 And so one way for me to run this program a little bit faster would be to take the superscalealar idea。

 I'm gonna build a processor。 It still has like one set of registers。 It has access to， to memory。

 but it has the ability to kind of figure out if there's two instructions that are。

 can be done in parallel。 and it has two execution units to do them， if it wants to。Again， like。

You compile your program and C。 You see a sequence of instructions。

 processorsor Intel does this or AM D does this under the hood。 You never know。Right。

 but in this program， or at least in this region of the program， at least。There's， there's not any。

ILP， you know， like just in my， in those instructions that I chose， they are all dependent。

So this processor， if it was running that sequence of instructions。

 is only going to be making use of one of these execution units and one of these fetch and decos。

 right， There's no ILP here。

![](img/9be0983c46a7ddc10da75418d0f65d45_107.png)

So。This gets back to。The broader thing。 But there's tons of parallelism in this program， right。

 because we can process every in element of this array completely in parallel。



![](img/9be0983c46a7ddc10da75418d0f65d45_109.png)

But if all the processor is doing。It's kind of looking at like micro instruction sequences。

 All it sees is dependent instructions。 It doesn't have the ability or it would be intractable to kind of to have the ability to look over a huge window of the program。

 like that outer for loop and go， oh， even though this is a for loop in C plus plus。 And technically。

 every loop iteration is dependent because there's I plus plus。

They all seem to be accessing different input variables。

 That's the type of analysis that goes well beyond what could happen， you know。

 in a clock tick in a hardware， in hardware。So what？Hardware architects did， as they said。

 you know what， Let's just assume that the programmer。Tells us。What where that parallel is。

 So we don't have to work so hard for it。 So this is。

 I made that diagram that I had on the last slide just a little bit fancier。 I said， look， like。

 you had this out of order execution logic。

![](img/9be0983c46a7ddc10da75418d0f65d45_111.png)

Outside of this class， all this other fun stuff that's in a processor to make an instruction stream go faster。

 A lot of it's about not accessing memory。 Like you might put a big old data cache that has a ton of transistors to hold a bunch of data on cache。

 You might actually have logic that predicts what memory you're gonna access in the future as a prefeure。

 and all this fancy stuff in there to try and make the inner loop go as fast as possible。😊。

But there's this outer loop that's trivial in a paralyze。So idea number one is。

 let's take some of this fancy stuff out。Maybe a little bit smaller data cache。

 We're not gonna maybe do as much out of order execution or anything like that。

 And if we clear all that stuff out。We just have our basic processor with just a few， you know。

 which means far fewer transistors。And I'm going to use all those transistors I have on a modern chip。

To just replicate this， to make more of these processors。So now I have， you know， a processor。

 but it's a parallel processor。 And this is， you know， I'm gonna use the term core。 but there。

 there's nothing precise about this in the industry。 So now I have a。

 a multi core processor that just duplicated everything that was needed to run one instruction stream。

So if I give this processor there are two instruction streams。And say， hey， you know， core 0。

 run this instruction stream and core 2， do that instruction stream。I might be better off， right。

 Like， for example， maybe these cores because they don't have all the fancy stuff in them can run one instruction stream 25% slower。

Maybe they take more cash misses because the cash is smaller。 Maybe they。

 they mis predicteddicted a branch or something like that。But now， with those same resources。

 I could have two of these things。And if I put both of them running on different elements of the array at the same time。

 I have a two core processor that might run 1。5 times faster。Okay， see some questions。

We just duplicated everything We duplicated the hardware for executing instructions。

 we duplicated the registers， there's an R0 r1 r2 here。

 there's an R0 R1 r2 here and there's the ability for each of these processing course to take a look at the instruction stream that they're supposed to run and say my little Ex unit here and needs to run this instruction next and if that instruction is multiply R0 and R0 into R1 that's modifying in these registers I think compared to。



![](img/9be0983c46a7ddc10da75418d0f65d45_113.png)

How execution context， I'm not sure if that we'reuplicating everything， we're duplicating everything。

Yeah。So talking about the resources you just so basically using tools using two transistors。

 you have an option， you can a superscate processor or create a like two code， too simpler problem。

ExactlyNow， notice that both my multi core processor and a super scalar processor both have two fetch and decocode units and two execution units。

 right， But I've decided to organize them a little bit differently and now duplicate the execution context。

😊，So I got rid of all that logic to try and find ILP。I got rid of logic。

 maybe to have a really big data cache to avoid stalls。But now I have the ability to。

 if you gave me two instruction streams， I'll guarantee that you'll run both of them and get double the performance。

 but then it's only working on stuff that it knows statically。



![](img/9be0983c46a7ddc10da75418d0f65d45_115.png)

![](img/9be0983c46a7ddc10da75418d0f65d45_116.png)

![](img/9be0983c46a7ddc10da75418d0f65d45_117.png)

In this case， modern advanced compilers probably could。

 But the then I throw a small wrinkle in that program， The compiler is gonna go， I don't know。

 I can't reason about this anymore。 And we have to rely on the hardware， yes。



![](img/9be0983c46a7ddc10da75418d0f65d45_119.png)

Would you like to really just start by just saying that okay instead like I this doing chunks like okay。

 doing like I love these comments because it's fun。 You see， can't you trivially just do it。



![](img/9be0983c46a7ddc10da75418d0f65d45_121.png)

That's the point。In a program like this， which looks a lot like a tensor operation， right。

 It's trivial for you， the programmer or or maybe even a software compiler to generate code that says this is different from this。

 It's parallel， Trust me。😊。

![](img/9be0983c46a7ddc10da75418d0f65d45_123.png)

We don't need to rely on hardware to do it。 So the observation is that doing that automatically in hardware is not an efficient use of resources。

 What's better is to have push that up the stack。 Okay， now， right now， this is C code。

 This is valid， compilable C code。 If you compile it。

 Kang will kick out unless you're turning on some very fancy stuff。



![](img/9be0983c46a7ddc10da75418d0f65d45_125.png)

A single instruction stream， because the semantics in this program are serial。 Okay。

 So if I take this program and I run it on my dual core processor。

 I'm going to create one instruction stream to run on one of those cores。

 and those cores are wimpy cores。 It's going run slower。😊，Some makes sense。

 so I've got to change my program。 So let's do it in the only way that we know how。

 assuming that you've taken 1，11 is let's spawn some threads。So take a look at this program。

Take a break。 You know， I've been talking a lot。 Talk to your partner for， for。

 or your friend or your enemy or whatever for， for 45 seconds。

 And I want you to tell me what this program does。 And specifically what I mean。

 is it computes the same answer as everything I've shown you。But there's two threads。

 There's the original thread， and there's the thread that I spawn。

 One thread deals with some elements。 Another thread deals with some other elements。

 What thread does what？ Take 30 seconds to just talk that over。But。All right。

 so tell me how does this program divide the parallel work？



![](img/9be0983c46a7ddc10da75418d0f65d45_127.png)

。あすせ。which is Sineex， the main program does the second enough。

 and the does the first half portion Yeah， so I have two threads。 They both call Sineex。



![](img/9be0983c46a7ddc10da75418d0f65d45_129.png)

The main thread actually works on。The pointer at x plus n。Which is actually N over 2， R N。 So the。

 the call， the， the thread I spawned as the first half。

 the thread that I I already had as the second half。😊，That doesn't matter。

 What does matter is as the programmer， I've created two threads。

And from the programmer's perspective， a thread， from the machine perspective。

 to instruction streams， the operating system here， which we're not gonna talk about， just says， oh。

 look， here's a program with two threads， two instruction streams， Hey， processor。

 Here's two instruction streams。 And the processor goes， okay。

 I'll run one on core 0 and the other one on core 1。😊，Okay。

 but without me explicitly creating parallelism or some magical compiler explicitly creating parallelism。

 this processor is not given to instruction streams to want to run。😊，Now。

 another way to think about this is you're like， gosh， like， this is kind of gnarly。

 I even had to ask you to parse the code。 Really， the way you want to think about it is like。

 if I go back to the original program， you'd probably be like。

 it's a lot more intuitive just to like， have some way to say that outer for loop is parallel。😊。

Or as independent， like by saying， look， everything is outer for loop。

 you can do independently on different threads if you want to。

 you go figure out what threads should do what。 And so you should assume that in， you know， modern。

 modern programming languages， whether it be you know。

 like pytorch or or any kind of programming language that has's parallel constructs。

 There's almost always some way to have some form of a for loop， an iterator where you。

 the programmer declare， trust me， I know you can do all the loop iterations in parallel if you want to。



![](img/9be0983c46a7ddc10da75418d0f65d45_131.png)

Okay， so what I did here is I made up， I made up syntax。 This is not valid C anymore。

 And I just said， imagine a for all loop。Where instead of， you know， saying I plus plus。

 instead of empirically saying here's how we iterate all the loop。 I just look。

 there's a for all loop。 there's going be iterate。 There's going be N iterations。

You can identify your current iteration by the variable I。

And I guarantee you that I wrote the program。 I know that all those iterations are potentially parallel。

Like， you can do them in parallel and you will get the same answer or good。

And if I write code in this higher level of abstraction。Shoot， like it's not hard at all。

 All of you could sit down and go， I know how I would do that。 I would actually， like。

 if I was running on a machine with two cores， I would create two threads。

 and then I would create a four loop on each。 And one of them would do half。

 You could kind of think through how you would transform this program。😊，Into this program。

 if you knew you were running out a two core processor。RightNow。

 imagine we weren't running on two core processor。 You were running on a four core processor。

 If you wrote code with P threads like this， you would be like， shoot。

 I'm only actually going to use two of those four cores。

Whereas that's why it's kind of useful to sort of think about how the programming model can give me a much more abstract way to just say this stuff is independent and however you want to schedule it in parallel you can。

Because if I start writing code like this。If I happen to run on a four core machine under the hood。

 that runtime can spawn four threads， or if I'm running on a 16 core machine。

 it can spawn 16 threads。I don't need to know as a programmer。 All I'm doing is I'm saying， trust me。

 these iterations are independent。 Cre as many instruction streams as you feel appropriate on the computer that you're running on。

So I can scale up to a lot of core pretty quickly if I take out a lot of the fancy fancy stuff。

 if I start like getting rid of a lot of superscalealar execution。

 if I kind of maybe move to smaller caches， I do all the things that architects have have done to make single instruction streams run fast。

I can rip some of them out。 And in a modern era， I can get a lot of cores on a chip。 So， you know。

 here's an Intel CPU。 If you look at a chip diagram。

 you can kind of just see where the transistors for the various cores are。嗯。That's a 10 core Intel。

 This is actually the R T X 4090。 And if you look closely， the replicated unit is about this size。

 we've got 144 of them on there。 Intel like sorry Nvi likes to call them S Ms for shared multiprocessors。

 But that's the granularity of the duplication。 You know。

 pull out your iPhone And if you look at Apple's bionic chip， there's six CPU cores in there。

 they're actually heterogeneous， they're not even the same design。

 So you have two cores that are bigger cores that have more of the big caches。

 the out of order execution in order to run single threads fast。

 And then for stuff where you have more parallelism， they have additional four small cores。

 or more of that superscalealar stuff has been ripped out and things like that。😊，对。Alright， and yeah。

 we've kind of already discussed this a little bit。 Okay， so I said that like， if I。

 if I write code in this kind of manner， I said， here's what we need to compute。

 But here are the computations that can be done independently。

There's another property of this code that's pretty nice。

I'm saying that everything that is being done independently。It's actually doing the same thing。

The body of the loop is being done。 The same body of the loop is being done by all threads。

 If I executed this thing。 The only thing different is that they're loading and storing different values。

So that gets me to the next major idea here。So what folks said is， you know。

 in a lot of these modern applications， machine learning for sure， graphics， for sure。

 any kind of numerical computing or data science or anything like that。

 You're often working on code that looks a lot kind of like this。 Like。

 I've got a big array of values。 I've got a tensor。 I need to do the same thing on everything。😊。

So what they decided to do。And now there's a change to my diagram。

 No change at all to the orange box。There's still a processor that grabs one operation per clock can kind of like do the control。

 Like， okay， what， what is Oh it's an ad。 Oh， it's a multiply。 Oh， it's a load。

But now I've actually replicated my A L Us。So I have8 A Us on this diagram or 8 execution units。

 And what's gonna happen is like， if the N instructions is an ad。

We're not just going to do one ad on one value。 We're gonna do 8 ads on8 different values。

 So all of these are kind of locked together with the same control。And for now。

 one way to think about it is I also took all the registers， R 0， R1 or whatever。

 And I turned them into 8 wide vector registers。So when I say add pro， so， so let's see here。 So。

 so I used to have a program that when we compiled it。

 we would compile it to instructions that worked on scalar registers。

 like 32 bit values or 64 bit values。That's what the C code does。But now I have a processor。

That has the ability to run an instruction that runs on a vector of 8 values and should read and write vectors of registers。

So one way I can get the compiler to generate。These new instructions that I need。

Is I can open up my favorite parallel programming library。

 and I can change every variable in my program。😊，2， the equivalent variables using these macros。

 these intrinsic macros that every variable here is a 256 B or an 8 by 32 B flow vector。😊。

So all I did is， I rewrote the program where I took here an int or a float。

And I turned it into a float vector of 8 things or an int vector of 8 things。

 And then notice that my for loop， my outermost for loop is not for I equals 0 to n。



![](img/9be0983c46a7ddc10da75418d0f65d45_133.png)

But I equals 0 to n by 8。So every time through this for loop， I'm actually doing the same logic。

 but I'm doing it for8 things。😊，And I've also made the code almost impossible to read。Right， okay。

Yeah， so this is a So now when this program gets compiled by a compiler that supports these。

 these little macro functions， the output。Our instructions。That modify vectors。

Not instructions that modify scrs。 So you see the difference。

 I changed my R  zeros to these X M Ms just to indicate that they were something different。So。

My compile program processes 8 elements， simultaneously， using vector instructions。

With one instruction stream。 So I still have， I have one instruction stream。

 but the instructions now are these wide ones。Now， I can combine that。

With multiple instruction streams。 So if I take this new type of core。

And I apply it to my 16 core processor。 I have a 16 core processor that runs 16 on instruction streams。

 but the instructions in those streams are processing eight pieces of data at once。So altogether。

 my chip。Has 16 core，16 instruction streams。16 times 8 or1 hundred and28 execution units。

 which means I can do work on 1 hundred 28 pieces of data at once。So arguably。

 I could maybe be going 128 times faster on the 16 core chip。Notice that。

You could imagine if I asked you to if you knew this was a for all loop。

 you could turn this for all loop。 if you were a little compiler。 And in fact， assignment1。

 you will do this into 16 threads and those vector instructions inside those threads and change that for all loop for equals 0 to n to for  equals0 to n by 16 by by 8。

😊，So you can imagine how if I ask you to do this in one assignment。

 the value coming comes from you being told what is potentially independent。

 The value is not from the mechanical transformation into vector instructions or threats。Question。

 if you only were kind of just taking through green Mill to serve。Well。

 were have mean we' got to move that data。 We are suspending disbelief temporarily on how。

 how costly it is to move data。 And we're first getting set up on how to crank on that data。



![](img/9be0983c46a7ddc10da75418d0f65d45_135.png)

And then we're gonna come back with the question at the end of， can we get the data there。



![](img/9be0983c46a7ddc10da75418d0f65d45_137.png)

Okay， so this was't kind of like a pretty big intellectual change。 I'd like everybody to， to。



![](img/9be0983c46a7ddc10da75418d0f65d45_139.png)

There's a good time to raise your hand， if you can't。



![](img/9be0983c46a7ddc10da75418d0f65d45_141.png)

Mentally think through。What's going on here。Right， I have 16 threads running on a 16 core chip。

And those threads， the instruction stream， contains instructions that are processing 8 wide vectors。

 And if I think of what's going on at any moment in time。

 there's 128 pieces of work getting done at any point in time。So if I。

 if I perfectly paralyze and I compare my performance to my original starting processor that had one core and one A O U per core。

 I might be up to 128 times faster。😊，Yeah。そういうがてわてはい。で事。我。



![](img/9be0983c46a7ddc10da75418d0f65d45_143.png)

The first answer to your question is now I have 8 execution units that can do 8 things per core instead of one execution unit that can do one thing。

Yeah， real question is， well， why don't people， Why'， why don't we just make eight times more cool。

 right？ And so what's going on is we're amortizing a lot of the costs of controlling our processing and instruction stream over these8 execution units。

 And like in my cartoon diagram， notice that there's still one fetch and decocode unit。

Like you still do。 what's the next instruction。 Okay， that instruction， great。

 Now you're just gonna say， I'm gonna run that instruction on vector registers with my vector of values。

😊，So this is an， like， this is a good ideaca I can amortize a costs of a processor across many execution units。

 And I can do that if my code does the same thing and needs the same logic for all of the elements。😊。

There also resources and all， I think like。A single leg 16， single COVd processor。



![](img/9be0983c46a7ddc10da75418d0f65d45_145.png)

しグ？つて。

![](img/9be0983c46a7ddc10da75418d0f65d45_147.png)

So16 point processor that I'm messing up the。Basically 16 codes you would be surprised。

 I know what you're getting at， how few resources are needed to produce an arithmetic unit。

Compared to everything else， especially when it's not high precision floating point。



![](img/9be0983c46a7ddc10da75418d0f65d45_149.png)

Yeah， so the idea here is those things are cheap。 We can pack a chip full of those。

If the code is set up to use them。That's the main idea。

And now we're gonna get to something that might， oh， sorry， let me I meant to go this way。O。

Now there's this question， is the code set up to use them？

 So I'm going change the example for just one slide。



![](img/9be0983c46a7ddc10da75418d0f65d45_151.png)

Imagine that this was my piece of code for all N elements。 do this logic。😊。



![](img/9be0983c46a7ddc10da75418d0f65d45_153.png)

So for all N elements， every element can be processed independently。 Do this logic。 read the value。

And then maybe you need to do the if statement， and maybe you need to do the else。

But I just built a processor that has。 Every core has8 execution units that have to do the same thing。

And now I have iterations of the loop that some of them need these instructions and some of them need these instructions。

 So I'm gonna diagram this out for you as going down the slide is like time as we execute the program。

 going across the slide is what each of the A L Us are doing。

 This is just about what's going on in one core。😊。

![](img/9be0983c46a7ddc10da75418d0f65d45_155.png)

So at the beginning of the program， the A L user just， they're doing what， what I just told you。

 like theyre， they loaded X sub I all in one big vector operation。

 They actually even can do the if T is greater， you know， if， if for every iteration。

 if the value loaded is greater than 0 and they'll get a vector。😊。



![](img/9be0983c46a7ddc10da75418d0f65d45_157.png)

A bo vector of truths and falses as a result of those tests。

 notice that some of these iterations evaluate to true， and some of them evaluate to false。

What do you think happens next？Any ideas？对。only the because the rules of my underlying implementation are I only。

 I execute 8 things at once， and they got to be the same， same instruction。And in this case。

 what I might do is I might say， you know what， I know that。

This code that I have to run has to run the instructions in the if branch。 So let's do it。

Let's run those instructions in the if branch。And then let's just， you know。

 mask off or or not even run， you know， like， maybe like cancel out the operation of any A L U that's responsible for data that actually doesn't need that instruction。

And then we're gonna run the else branch。And we'll flip that， flip that mask。

And so at the end of the day， not all A A O Us are doing useful work。

 I built this chip that has eight things in it。😊，Becauseuse I know that if。

 if I could do 8 things at once， I got a really big。 I got a lot of compute for free。

But if code isn't set up to do eight things at once。

I'm essentially just spinning my wheels on some of those execution units that don't have anything to do。

Can you see why the worst case is 1，8。Right， question。shouldnn't always be。

True location and beautiful。 Oh， I see Well， Well， I， first of all， two clarifications。



![](img/9be0983c46a7ddc10da75418d0f65d45_159.png)

Oh， because if none of the， if none of the iterations need the if case。

 we can be smarter about it and and the skip of thing。 Yes， yeah， so here's a question for you。

 This is line to talk over。 Can you give me the simplest piece of code that you can think of。

 And by simplest piece of code， I， I actually say， can you do it with one if statement。😊。

That overall， on average， this processor will be running at one/8。

Notice that it's not in this scenario because it's running at 3/8 efficiency up here and 5/8s efficiency down here。

Can you give me a piece of code。That will create a situation where。We're at 1，8 sufficiency。

 Give yoursel some time to talk about it。 And you only get to use one if statement。ち。All right。

Any thoughts？Let's go that， yes sir。

![](img/9be0983c46a7ddc10da75418d0f65d45_161.png)

If we like take whatever was in the yellow block， like put it into one equation and multiply it by t greater and00 Okay。

 say that again so okay， so we have this code here。And， and what， what goes to the O box。

 we can multi that。Buling statement of bone plus that bullying statement times whatevers the else。

 so if it's true， itll be one times。Whatever you need the yellow box split zero times that same。Okay。

But will have a proper answer and then in the other case it will be 000 arms in the yellow box plus 11。

And then we'll get what' reason to help so we don't need the experience。You're trying， Oh， oh， I see。

 Okay， so， okay， so what you said was， I， I see what you're doing here。 So I。

 I set up this thing where there's an if statement in the code。😊，And what you're proposing is。

 let's remove the if statement and the L statement altogether。The code is just the orange box。

 followed by the blue box。And we get the same effect。

If we multiply these results by 0 at the appropriate time and these results by 0 at the appropriate time。

 Okay， so that is a good implementation of this if statement。

But what you've created is you've created something that still does all the same instructions。

And it has the same cost。So what you've said is like。

 if you wanted to compile this to a machine that has no if statements。In the instructions， you， you。

 you actually given me a good lowering of the if statement to predi， what's called predication。

So good compiler optimization。But we're still running exactly the same performance as before。

 So what I'm looking for is a solution that given that if statement or given your implementation of that if statement gets me running it one。

8th utilization。😊，Hundred% utilization is every A U is doing useful work on every step。

One eighth utilization， eighth at any given time or one eighth at all times on almost all times。や。

Should you modify like if exit I is larger than exit I might this one？

The next branch has to depend on the news。So X of I， I mean， there's no dependency。

But we don't know the values of the data。So what data would you give me to make that？So yeah。

 I send you like you the same。I退。But you decide to put a sequential dependency between every iteration？

Yes， you， okay。 But， by that definition， yes， you are running a worst case performance。

 but youve made the entire program non parallel。 I'm actually thinking about something that stays with the parallel program。

 Yeah， you just did if eyes。😊，If eye is odd， then we're half and half， right？也不愿 here。

So I'm 50% utilization in both。Okay yeah。X sub I equals x of0。If x sub I， if x sub I equal x sub 0。

 you're either gonna be all true or all false， right。

So I'm going run an 100% utilization because everybody's either going go true or false and then the other block gets skipped。

Could make it if I is 0 mod 8 mod I is mod 0 mod 8。

 or let's say I change my input data such that every8 item is， is gonna trigger a true。

 And all other ones Okay， so that'll get me。One orange bar， and7 blue bars。

I'm still not guarantee if those are equal cost things I'm running 50% utilization just half the time on78 the other half of the time I one I thought it was with just an statement and no office so we're only running。

That's we were discussing Oh I see if you're only running the Okay yeah， you're only running the if。

 but I was thinking about if it's an if else but you're almost there， we've almost got it。

 So if you send once eighth of the iterations down the， seven8s down the L。I'm still 50% utilization。

 unless lets me make some assumptions about the。If I send one iteration down if and if is a billion instructions。

And 7，8s down else。 And that's the cheap path， which is almost the same basically as what you were doing。

 Yeah， exactly。是 you see啦。So I can make this chip with an if else run at one8th performance。

And it it's， yeah， by essentially making the if claws very cheap。

The else clause is very expensive and making sure when I'm running the if clauses。

 only one out of 8 are actually running。 But yeah， so that is。

 that is conceptually equivalentvalent to your， your suggestion。



![](img/9be0983c46a7ddc10da75418d0f65d45_163.png)

This can be a problem， right， And on modern Intel hardware and AM MD hardware， the vector width is 8。

 So on modern GPU hardware， that vector width could be as high as sometimes 32。



![](img/9be0983c46a7ddc10da75418d0f65d45_165.png)

So you might be like， well， if I mess things up， if I'm running at 1，32 of my total peak performance。

 that's， that's a little frustrating sometimes。

![](img/9be0983c46a7ddc10da75418d0f65d45_167.png)

Just some terminology， you'll hear， especially if you read a lot of GPU programming stuff。

 You'll hear people go， you have to have coherent execution。 You have to have coherent execution。

 Coherent execution is just kind of a jargon and slang for saying。

 I have a program or all of the iterations in my loop。

 Everything that's going on needs the same instruction stream。

 And the lack of coherence is often called divergence。

 like you think about it as like different control paths are needed。

 So divergent code will not run well on a Simd architecture like this。

 Coherent code will run at high utilization。😊，And here this slides just some extra f that you can see on your own where you know。

 widths vary from about four wide Sd on mobile chips。

 especially a lot of the arm Sd instructions all the way out to about 32 wide Sd on on a modern high end GPU I will create a supplemental video talking a little bit about some slight differences between how GPs implement this concept and how CPUs implement this concept。

 So I'll talk about it。 I'll do an offline kind of watch the video to get into that。 Okay。

 so this kind of interesting。 We have three different ideas that we mixing and matching together。

 They are orthogonal ideas。 We have the idea of superscalear execution。

 which is a hardware implementation detail that requires no change to the program at all。

 which is if there are independent instruction in one instruction stream the hardware figures it out and can execute two of them in parallel inside the same core。

😊，S the same instruction stream。We talked about CMdy， which is the program itself， most of the time。

 says here are 8 operations or 32 operations that can be done in parallel。

 I have one instruction stream， usually。And it's just issuing these vector or larger operations。

 again， with an asterisk on， I will clarify that statement's not precise for GPUs， but conceptually。

 it's the same。And then you have the idea of multi corere。

 which is taking one of these cores that can run one instruction stream。

 maybe with vector instructions， maybe with superscalear and copying that as many times as you have the resources to fit on a chip。

So here are some examples， right， this processor， one core。Super scalar。This processor down here。

 two cores， no vector， no superscalear。This processor here， four cores，8 wide vector。

 no no superscalealar。And I can keep mixing things together。

 Like if I had to draw a diagram of the myth machines， not not quite that four cores。

 three way superscalealar，8 vector。😊，4 cores， every core can run three instructions per clock。

 Those instructions might all be vector instructions。Invidia GPU， about 80 of these cores。

 each one of those cores has about 128 A O Us that are actually organized in 32 wide 70 instructions。

All the same ideas， just different scales。 Some of these scales cause keynote to crash because you can't draw the diagram。

Yeah。你 feel去完。But protection be called have an。Super scalar execution is the core is given one thread。

 That thread has a sequence of instructions。 If it finds one。

 because those instructions are in one thread， they're all reading and writing the same registers。

 There's only one thread in one execution context。If there happens to be the ability to find a couple of those instructions that can be run in parallel。

 this chip may find up the three。Itterifying how many vectors is one core run in this。4 cores。

 It's often。 I want you to think about what's going on in a core because like multi core is just replicating things insideside a core。

 I have one instruction stream registers right here。

This core is running instructions in the instruction stream。 Every ticket runs the next one。

 If it happens to find instructions that are independent， maybe it can run 3。

If those instructions are 8 wide vector instructions， you'll get8 wide vectors。So。If you count here。

 there's 24 execution units。 Peak performance of this core is 24 operations per clock。

 Peak performance of this chip is  four times 24，96 operations per clock。😊。

Peak performance of this chip is 128 times 80， and I can't do the math operations per clock。😊，Yes。

8 to vector operation you。And 8 like， like， I want in this I want you to think about an8 wide vector in instruction is an instruction。

 just like， you know， there's an ad instruction。 and an ad instruction usually is add this scalar register to the scalar register。

 which means like add 42 and， and 10 and you get 52。



![](img/9be0983c46a7ddc10da75418d0f65d45_169.png)

A 70 vector instruction is an instruction that says。

 please add this 8 wide vector to this 8 wide vector， element wise。

So a single instruction does eight scalar operations。



![](img/9be0983c46a7ddc10da75418d0f65d45_171.png)

Like like the same， like imagine you're writing code in numppy or pi torch。

 and you have an eight wide tensor and another8 wide tensor and you use the plus operation。



![](img/9be0983c46a7ddc10da75418d0f65d45_173.png)

That's a machine instruction。Okay， yeah， when will this change。

 like when this change happen that nobody comes。

![](img/9be0983c46a7ddc10da75418d0f65d45_175.png)

On X 86， it was something called the SSE Inions， and I don't know they were four wide。

 I feel like they were probably early 2000s。 Yeah， and they were four wide for RGBA for simple graphics operations。



![](img/9be0983c46a7ddc10da75418d0f65d45_177.png)

Y， okay， so I've kind of beaten in early in the lecture about the effects of latency， right。



![](img/9be0983c46a7ddc10da75418d0f65d45_179.png)

And we motivated caches as being this thing in a processor that is critical to not running at one 2002050th of peak performance。

 waiting on these things。And。M。😊，And I also told you a little bit about， well。

 one of the major hogs of resources in a modern ship is putting these big caches everywhere you can in order to avoid stalls due to memory。

Right， and we talked a little bit about this access pattern。

 where even though it was like really predictable and going right through the array。

 when we came back around。We still missed。We still missed， even though， so。

Another thing that processors have in them。In addition to caches， is they actually have。Prefes。

 they actually analyze your program in the same way that they're looking for independent instructions and superscalealar。

 they might look at your access pattern and go， I'm pretty sure you're gonna be accessing this variable next。

 So I'm gonna go ahead and preload that address for you。😊，And so in a predictable access pattern。

 like I just showed you here， where we're kind of running right through the loop。

It's very possible that this may not。 I had to fix that on a conflictness。

 It's very possible that that last load might have been pre predicted and actually might be there。

But。you know， not all code runs like this， right， Like sometimes it's hard to predict something。Like。

 imagine you're walking through a linked list or you're， imagine you are， you know。

 you have some value。 and like， you just computed a value and you're gonna do an array look up based on that value。

 A very common thing is like， give an array of indices。

 go look up the data at that index or something like that。 So you， you can't。

In these throughput computing ideas， you can't really assume that you can predict what's coming。

 And in order to make room for all of these cores， we might have taken out of the prefetching logic。

 We might have shrunk the size of the cache。 So we've made it even more likely that we're gonna take cash misses。

 yet we pack the machine full of A LUs， which means we're gonna make even more memory accesses and need to make them even faster to keep all these things busy。

😊，So we've really created ourselves a little bit of a problem here。

 We have these amazing processors that have all this stuff yet that are waiting on memory。😊。



![](img/9be0983c46a7ddc10da75418d0f65d45_181.png)

And so in my house tonight， I had a PhD student graduate a couple weeks ago。

 and we're inviting him and his girlfriend over for hotpot。

 And so there's gonna be like a lot of prep going on。

 And so I want you to think about some real life examples。 Let's say you're cooking in the kitchen。

 Let's say you're doing your laundry tonight because you know， it's already day4。 So， you know。

 it might be on that。😊，How many of you when you're doing your laundry。

 put the load in the washer and sit there and wait。

How many people start boiling water and sit there and wait until it is ready before you put the food in。

What do you do instead？I mean， maybe some of you do Wait， I don't know。If not。

 you're gonna come away from this class with a good life hack。So what do you do。

 You put your laundry in， You boil your water。 What's， what's going on。You sit around and wait。

I mean， you watch all of my lectures on 2 X。 So I know you don't sit around wait， wait while you。

 So what do you do。you do something else， right？You did your homework in 1，49。So the main idea is。

 if， if， if you know something that you need to be done is not gonna be done for a while。

You just go do someone else。Now， that means you have to have something else to do。

 like maybe all of your lives are such that， you know， given anything else I have to do。

 I'd rather sit here and wait。 But most of us have multiple things that we can do that wed rather do。

 So this gets to the last idea today。

![](img/9be0983c46a7ddc10da75418d0f65d45_183.png)

We're gonna build processors that remember， like。I just gave you a chip that， you know。

 what did I say it had 16 cores times 8 wide 70， So it had 128 execution units in it。

Which means it can do 1 hundred 28 things at once。But imagine you're doing some machine learning operation。

 Imagine you're processing a 4 megixel photo off your iPhone。 or I guess it's 8 or 12 these days。

 You have millions of pixels。 You have way more things that you need to do。😊。

Then the things you could actually do at once。And so if you're gonna sit there and wait on some of those things。

Let's just go do start working on something else。 Okay， so here's the main idea。

 We're gonna take that core that we had。 Notice that in my this diagram。

 it's a single instruction stream。It's got super no super scalear， one instruction per clock。

 but I'm gonna allow that to be a vector instruction just for the sake of things。 Okay。

 and now what I'm gonna do is I'm gonna take the execution context， the registers。

Andly address space associated with them。Now I'm going to duplicate this。Okay， so remember。

 I said that an instruction stream。The execution context represents the state of the instruction stream。

 Or in other words， we could say the state of a thread。Now， what I'm going to do is I'm going。

 the processor， the orange in the yellow is staying exactly the same。



![](img/9be0983c46a7ddc10da75418d0f65d45_185.png)

But I'm gonna give that processor the ability to hold state。For four instruction streams。

 for four threads。Okay， so we're going to start executing normally。So now we're going to say， look。

 for this processor。Your program is going to say， create four threads now。For one core。

 four execution context here， have four threads to do。And so the processor is going move along。

 and it's going run a thread。 That's what I'm kind of trying to show you here。

 It's going run this thread。 Maybe it's X symmetry0 instructions。 that at some point。

 it gets to a load。Cash miss。This thread cannot make progress for a long time。

 Let's say this is the point at which it becomes runnable again because the data came back from memory。

 That was a 250 cycles that we were waiting。So do you think this core is gonna stay idle。Nope。

 the minute it's like， I can't make any progress because I got to wait。 I'm like。

 I got three other threads that I can go make progress on。 So we're gonna swap。And when I say swap。

 I'm talking about the hardware just， just starts executing instructions from the next thread。

 like no， no delay or anything。 It's just， oh， I can't make any progress with with this instruction stream。

 I've got another one sitting here。 next cycle， I'm gonna run that one。

 gonna run whatever it's available。 And then maybe that one stalls。 But we got another one。😊。

Maybe that one stalls。 We got another one By the time that fourth one has stalled。

We are past the point in time where this one is ready。So we can get going again。

 we can just start working on that other thread and let's say it finishes and we move on and so on。

What is the utilization of this processor？😡，Hundred percent。

What is the latency of actually finishing any one thread。

 It's actually longer because it actually had this time where it could have started running here。

 but it actually runs here。That's the last big idea here。

Is we're actually slowing down the amount of the， the wall clock time to get anything done in order to get everything done quicker because we're running at 100%。

I'll stop there。 Okay， so we'll review this again next time。 We'll start， and then we'll get into。



![](img/9be0983c46a7ddc10da75418d0f65d45_187.png)

Combining the memory and the superscalear。 But you have everything you need to get started and do 90% of your homework assignment。

😊。

![](img/9be0983c46a7ddc10da75418d0f65d45_189.png)