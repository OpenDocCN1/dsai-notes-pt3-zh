# ExamPro《生成式AI训练营｜Free GenAI Bootcamp》中英字幕（deepseek - P4：-04-Gen AI Architecting.zh_en - GPT中英字幕课程资源 - BV1SFEWzLEab

Hey everyone， it's Angie Brown。 I want to finish off our architectural diagraming so you have something to submit for week1。

 you'll notice that in this diagram I've kind of pulled out that other part。

 What I want you to do is go get some software lucid charts PowerPoint dry Excel draw whatever you need or even pen and paper and I want you to recreate this part here and I took out this part here and we're going to now walk through this architectural diagram and recreate it。

 Now I know that we had over here this very large list here which is really good。

 and then we also have rolls list down here below。 The thing is is that both Roa and Chris are super experts and they're showing you the real and worldd way that you would do it So if you were working for a very large company consulting for another very large company and you had to dot all the eyes you would fill all this stuff in。

 But for the scope of this project we can do something a lot simpler and I want your first week to be really easy I just want to make sure that you're able to do diagraming because as we go through this boot camp we're going continue。



![](img/a019dd4f18120d1bba780fd4e8073049_1.png)

![](img/a019dd4f18120d1bba780fd4e8073049_2.png)

![](img/a019dd4f18120d1bba780fd4e8073049_3.png)

![](img/a019dd4f18120d1bba780fd4e8073049_4.png)

![](img/a019dd4f18120d1bba780fd4e8073049_5.png)

![](img/a019dd4f18120d1bba780fd4e8073049_6.png)

![](img/a019dd4f18120d1bba780fd4e8073049_7.png)

![](img/a019dd4f18120d1bba780fd4e8073049_8.png)

![](img/a019dd4f18120d1bba780fd4e8073049_9.png)

![](img/a019dd4f18120d1bba780fd4e8073049_10.png)

![](img/a019dd4f18120d1bba780fd4e8073049_11.png)

to doing diagramming。 and at this point in time， it might not be solidified in your head exactly what these diagrams should look like。

 And so I don't want it to be really hard for you。 Okay， if you can do something more complex。

 happy to see that you do that。 But we're just going go and recreate what Ro has provided for us step by step up here。

 I' going keep it off screen And then we're gonna put it in our repo and then in a separate video。

 I'll show you how to submit your homework and for homework in week one。

 you need to have sentence construction done。 and also。



![](img/a019dd4f18120d1bba780fd4e8073049_13.png)

![](img/a019dd4f18120d1bba780fd4e8073049_14.png)

![](img/a019dd4f18120d1bba780fd4e8073049_15.png)

![](img/a019dd4f18120d1bba780fd4e8073049_16.png)

![](img/a019dd4f18120d1bba780fd4e8073049_17.png)

This architectural diagramming。 Okay， So again， pen and paper， anything you want。

 just make it happen and you'll be good。 So what we're going to do is recreate this one here。

 And so basically， these study activities are going to be isolated here。 So we're going to represent。



![](img/a019dd4f18120d1bba780fd4e8073049_19.png)

![](img/a019dd4f18120d1bba780fd4e8073049_20.png)

A study activity over here。 Let's just assume that it's the sentence constructor。



![](img/a019dd4f18120d1bba780fd4e8073049_22.png)

Okay。And for now， I'm just gonna leave this up here because it's sometimes hard to work with an elements。

 But we're gonna model the first part。 And the first part is having our model API。嗯。

And then inside of that， we have generation。You know。

 I might just represent this as a simple box and call it an LM， but it's totally fine。

And we'll go here。 I think she put it generation here to make it very clear that it's generating something out。



![](img/a019dd4f18120d1bba780fd4e8073049_24.png)

Then we'll have our user。

![](img/a019dd4f18120d1bba780fd4e8073049_26.png)

So here we have a user。

![](img/a019dd4f18120d1bba780fd4e8073049_28.png)

Or users。Because remember that this app， what it will do， will'll take this out here。 We're not。

 we're gonna have a payment gateway。But what it will do is it will launch these activities。

 And then the student interacts with them this way， right？ So here we're going to drag out。



![](img/a019dd4f18120d1bba780fd4e8073049_30.png)

A few lines， I'm just going to drag it out this way， so it's a little bit easier。

We'll keep them detached for the the current moment。

 because we're gonna be tweaking this pretty quickly。 And so we'll have query。And response， okay。

So pretty straightforward。 Also， I'm going make my head a little bit smaller。

 I just want to get out of the way here and not causes too many issues。

 So I'm gonna be nice and tiny。

![](img/a019dd4f18120d1bba780fd4e8073049_32.png)

So we have query and response。 The next part that we want to have is we want to implement the Ra data data。

 So this looks a little bit different than how I would do it and both ways are totally valid we just want to get it working here。

 So for the query it needs to first we want to implement RaG and so RaG stands for retrieval augmentation。

 we cover enough in the gen essentials。 So if you need a bit more information about it it isn't there。

 But what RaG does is it allows us to fetch data from an external source could be the internet could be a database and maybe we could represent that with the Internet。

 So we have an internet icon here， internet。

![](img/a019dd4f18120d1bba780fd4e8073049_34.png)

![](img/a019dd4f18120d1bba780fd4e8073049_35.png)

![](img/a019dd4f18120d1bba780fd4e8073049_36.png)

Right。

![](img/a019dd4f18120d1bba780fd4e8073049_38.png)

And the idea here is that Reg can go to these sources prior to this。Okay。

 so we can go here and it can go。

![](img/a019dd4f18120d1bba780fd4e8073049_40.png)

ItTrying to drag out the other line。 Sometimes it's a bit tricky to drag out these lines。



![](img/a019dd4f18120d1bba780fd4e8073049_42.png)

Each software has different challenges， so just try to figure out what best works for you， okay。And。

 it's a bit tricky。 So I to try this over like that， perfect。And。

This one needs to go a little bit to the right。

![](img/a019dd4f18120d1bba780fd4e8073049_44.png)

If you've been to my previous boot camp， you're probably really good at diagramming right now。

 So if it's your first time。

![](img/a019dd4f18120d1bba780fd4e8073049_46.png)

Hope you're having fun。 So we have the query。 It goes to the rag。 It goes here。

 and then it goes to here。 And then we get a response in this way。



![](img/a019dd4f18120d1bba780fd4e8073049_48.png)

![](img/a019dd4f18120d1bba780fd4e8073049_49.png)

You know， it's like if we were building a sentence constructor and we said。

 I want to practice sentences based on my favorite movie and we happen to have that stored in a database or I want to practice on the latest news that maybe goes out to the Internet。

 right？ And so that could be something that we have it doing here。

 Let's go take a look at the next one。

![](img/a019dd4f18120d1bba780fd4e8073049_51.png)

![](img/a019dd4f18120d1bba780fd4e8073049_52.png)

Here we have input guardrails。 so， and we also have scoring。



![](img/a019dd4f18120d1bba780fd4e8073049_54.png)

So I'm going to go over to here and we'll put some input output guard wheelils here。

And this is being shown after the rag， which I guess is fine because it's near the model， right。

 So maybe what we can do。

![](img/a019dd4f18120d1bba780fd4e8073049_56.png)

![](img/a019dd4f18120d1bba780fd4e8073049_57.png)

It's going to detach this here。And detach this one here。 But what we'll do is we'll take this here。



![](img/a019dd4f18120d1bba780fd4e8073049_59.png)

And we'll go。We'll say input card rail。And then we have output grid rail。

Make that a little bit bigger， so we have a little bit of room。A little bit creativity。

 You gotta put into this。

![](img/a019dd4f18120d1bba780fd4e8073049_61.png)

And so now we have this， and then it comes back to the user here。 whoops， Oh， cool。

 I can drag that up and down。 I like that。

![](img/a019dd4f18120d1bba780fd4e8073049_63.png)

Right and so the user's here and we're just still working through it。

 So now we're starting to get this process here。 Let's take a look at the next one。

 We do have scoring in here。 And so， you know， the reason I think Rilla put that scoring in there is that a lot of traditional models will provide you a score of how well it did。

 but this really depends on what the model is right because if this is an LLM。

 it's not necessarily going to have scoring it's just going to return your result because LMs do not return a confidence score。

Because they're just producing continuous text。 So let's assume that this is an LLM。

 And so we would not put scoring in this case。 but for a different kind of model。

 we absolutely would。

![](img/a019dd4f18120d1bba780fd4e8073049_65.png)

The next step here is that we have routing。

![](img/a019dd4f18120d1bba780fd4e8073049_67.png)

And so I'm thinking that， you know what role is suggesting here is more complex orchestration。

What I would probably do if I wanted to represent routing。

 I would probably show that more in a diagram。 But for this model， it's very simple。

 So we don't need routing， but routing could be very， very useful。 Then we have a cache。

 And so we have a few different places where we can have a cache for optimization。

 We have a cache of the user's input and we have a cache that comes back from the rag。

 I kind of like the one where it's。

![](img/a019dd4f18120d1bba780fd4e8073049_69.png)

![](img/a019dd4f18120d1bba780fd4e8073049_70.png)

![](img/a019dd4f18120d1bba780fd4e8073049_71.png)

![](img/a019dd4f18120d1bba780fd4e8073049_72.png)

I don't think the user input's a big deal， but it really depends on how large the thing that they're sending because let's say they're sending a document every time。

 That could be a huge challenge。 But you could put cache is in quite a few different places。

 You could put a cache between the rag in here。 You could put a cache between the user and the rag。

 You could put a cache between the rag and the user input。 But I gonna to call this prompt caching。

 I me say prompt cache。

![](img/a019dd4f18120d1bba780fd4e8073049_74.png)

![](img/a019dd4f18120d1bba780fd4e8073049_75.png)

![](img/a019dd4f18120d1bba780fd4e8073049_76.png)

![](img/a019dd4f18120d1bba780fd4e8073049_77.png)

嗯。And maybe we cash here。Right， there's lots of places where you can cash。

 And there's just going be different trade offs based on what you do。

 And so I'm just gonna put it here， alright。

![](img/a019dd4f18120d1bba780fd4e8073049_79.png)

![](img/a019dd4f18120d1bba780fd4e8073049_80.png)

Let's continue on and take a look。And here。

![](img/a019dd4f18120d1bba780fd4e8073049_82.png)

Rightrite actions， update order， send email response。

 So before we had read actions and write actions。 And yeah， we could。

 we could say like maybe they do that later in the boot camp。 when we do the text adventure。

 that's something that we do。

![](img/a019dd4f18120d1bba780fd4e8073049_84.png)

![](img/a019dd4f18120d1bba780fd4e8073049_85.png)

But for this， I'm going to keep it simple。

![](img/a019dd4f18120d1bba780fd4e8073049_87.png)

And we're just gonna assume there's no right action here。 And this is all we have to do。

 I'll take this out here。 and we'll get a sququiiggleler。A squiggler， a squiggly。

 a squiggly one here。

![](img/a019dd4f18120d1bba780fd4e8073049_89.png)

![](img/a019dd4f18120d1bba780fd4e8073049_90.png)

And again， I'm just trying to drag out。

![](img/a019dd4f18120d1bba780fd4e8073049_92.png)

There we go。And I'm not sure why it's down there。

![](img/a019dd4f18120d1bba780fd4e8073049_94.png)

The users are a little bit trickier to drop。

![](img/a019dd4f18120d1bba780fd4e8073049_96.png)

![](img/a019dd4f18120d1bba780fd4e8073049_97.png)

Perfect。And so this is a way we can represent our diagram。

 I'm gonna to go ahead and now drag this around this， like this。



![](img/a019dd4f18120d1bba780fd4e8073049_99.png)

![](img/a019dd4f18120d1bba780fd4e8073049_100.png)

![](img/a019dd4f18120d1bba780fd4e8073049_101.png)

So now again， we're trying to do this so we can communicate to our。



![](img/a019dd4f18120d1bba780fd4e8073049_103.png)

![](img/a019dd4f18120d1bba780fd4e8073049_104.png)

To our key stakeholders。 And so there's just some things I might want them to know。 And so I might。

 I'm gonna just take a generation here andll call this an LO M。

 And so there might be some key things I want to put in here。

 One key thing I might want to put in here is the size I might put in here， like， let's say。

70 billion parameter model。70 billion。Prameterters。

 we would have to explain to them what parameters are。Like just to say， like， that's。

 that's the size of the brain。 like I said earlier， the more， the more brain cells you have。

 the bigger the， the bigger the thing is。 So， or maybe we'll just put 70 billion on here instead instead of doing it this way。

 whoops。

![](img/a019dd4f18120d1bba780fd4e8073049_106.png)

Right。嗯。

![](img/a019dd4f18120d1bba780fd4e8073049_108.png)

There are specialized types of database， So we might call this a vector database。

Does't have to be vector， but's something that we can do。Okay， and so。You know。

 I think from a business perspective， I'd like to tell people like， yes， the。

 the size of it is a 7 billion parameter thing。 We have input and output for security。

 We have a caching layer to improve performance， and we have a database。 And so， you know。

 if you're talking to them， you're just showing them all these moving parts。



![](img/a019dd4f18120d1bba780fd4e8073049_110.png)

And you might need to explain like what is the cost of the vector database。

 what is the cost of this component， what is the complexity and reliability of this of these things。

 and you can use those as talking points。 And really， this is all I want you to do。

 Just keep it nice and simple。 And I would call this done。

 So what we'll do is I'll take a screenshot here。

![](img/a019dd4f18120d1bba780fd4e8073049_112.png)

![](img/a019dd4f18120d1bba780fd4e8073049_113.png)

Okay， again， you have to recreate it。 It shouldn't look one to one with mine。

 It should look a little bit different。 But I'm gonna go into our my personal repo。

 This one's Omen King Free Jent bootcamp。 I'm gonna press period。



![](img/a019dd4f18120d1bba780fd4e8073049_115.png)

![](img/a019dd4f18120d1bba780fd4e8073049_116.png)

I'm going to make a。New folder， and we're going to call this one GenI architecting。Okay， and。



![](img/a019dd4f18120d1bba780fd4e8073049_118.png)

I I have to open up paints'cause I'm on Windows， So it's didn't really go where I want it to go。

 which is fine。 I'm gonna save it here。 I'm gonna save it as a PN G or JPg。

 If you you save it as either of those， it'll make it really easy for me to view it。 So if you can。

 please do that。 I'm gonna go to my desktop here and we'll just say， Jenny， I。



![](img/a019dd4f18120d1bba780fd4e8073049_120.png)

![](img/a019dd4f18120d1bba780fd4e8073049_121.png)

Jenny I architecture。

![](img/a019dd4f18120d1bba780fd4e8073049_123.png)

I don't care about the name of the file， per se I just need to make sure that it's in this exact folder name。

 if you have in that exact folder name we're going to be in good shape and so we'll open this up。

I'm just looking for a folder here， sorry。And we'll make a new。And I'm dragging this。

 I have it on my desktop here。 Like here， see。And I'm going to drag that image right onto here。



![](img/a019dd4f18120d1bba780fd4e8073049_125.png)

![](img/a019dd4f18120d1bba780fd4e8073049_126.png)

And there we go。 Now， if you want to optionally， you can create a markdown file here。

 We'll call it read me。 And what we can do is go through here a little bit and see if there's something that we could pull out and ask answer questions on。

 So for the requirements。

![](img/a019dd4f18120d1bba780fd4e8073049_128.png)

![](img/a019dd4f18120d1bba780fd4e8073049_129.png)

![](img/a019dd4f18120d1bba780fd4e8073049_130.png)

Business goal and objectives， specific capabilities the system must have。

 So maybe for requirements like functional requirements。



![](img/a019dd4f18120d1bba780fd4e8073049_132.png)

You know， we might say for this， I'm not gonna do all of them， but we'll do some of them。

 And you can pick any random ones you want out here as practice。I'll say。The hardware。

We're using must。Since we。I'm just trying to think of this because we have， we have a portal here。

 right， and so。I'm thinking， you know， you know， the company， the company wants to。Invest in。

Owning their infrastructure。To ensure。You know and the reason why they might want to own their infrastructure is because。

 you know。The company wants to invest in owning their own infrastructure。

The reason is because there is a concern。About the privacy of。

User data and also a concern that the cost。Of managed services。For Jennyi。Will， greatly。

Raise in cost。诶。They want to invest in。An AI PCC。Where they can afford spend of 10 to 15 k。

They have 300 active students。诶。And students are located。



![](img/a019dd4f18120d1bba780fd4e8073049_134.png)

Within the city。Of and we'll pick a city out。 I'm trying to think of it Nagasaki。

 Maybe we'll go to Nagasaki here。

![](img/a019dd4f18120d1bba780fd4e8073049_136.png)

![](img/a019dd4f18120d1bba780fd4e8073049_137.png)

Or maybe what we can do for fun。

![](img/a019dd4f18120d1bba780fd4e8073049_139.png)

I'm trying to see where the town of。

![](img/a019dd4f18120d1bba780fd4e8073049_141.png)

Oh， I'm not sure， but we'll go with Nagasaki。They want to invest in AC where they could port to spend 10 to 15 k。

They have 300 active students and students are located in the city of。N Nagaaki。So。嗯。You know。

 when you consider those kind of things， then it's like， okay。

 if I only have to consider about this city and this active people and they're coming to physical classes。

 right， and as long as it's good enough that they can self host。

 then that might be an option that is totally totally applicable to them if they're not trying to serve it on a global market。

And and so that might be something that they might want to do。 So now that we know that we've。

 and again， I'm just making this up。 you can make up whatever you want。



![](img/a019dd4f18120d1bba780fd4e8073049_143.png)

Nonfunctional requirements。 So functional requirements specific capabilities the system must have。

 And maybe that's not clear because it's like capabilities as opposed to constraints。 And， you know。

 we just got to fix the better assumptions are considered be true without proof at the time of planning and development。

 And so assumptions is technical uncertainty to me。 So we'll say assumptions。



![](img/a019dd4f18120d1bba780fd4e8073049_145.png)

![](img/a019dd4f18120d1bba780fd4e8073049_146.png)

![](img/a019dd4f18120d1bba780fd4e8073049_147.png)

![](img/a019dd4f18120d1bba780fd4e8073049_148.png)

You know， we are assuming。That the open source。L Ms that we choose will be able。

We will be powerful enough。

![](img/a019dd4f18120d1bba780fd4e8073049_150.png)

To run on hardware。With an investment。Of。10 to 15 k， right。



![](img/a019dd4f18120d1bba780fd4e8073049_152.png)

And these people are going to really just like。

![](img/a019dd4f18120d1bba780fd4e8073049_154.png)

You know， they're going to， they're going to， you know， the other assumption is like。You know。

 we're just going to hook up。A single server in our office。To the Internet。



![](img/a019dd4f18120d1bba780fd4e8073049_156.png)

And we should。Have enough。Bandth。To serve。

![](img/a019dd4f18120d1bba780fd4e8073049_158.png)

The 300 students。Right。

![](img/a019dd4f18120d1bba780fd4e8073049_160.png)

嗯。Data strategy， develop a comprehensive data strategy。 So we might do a little bit of this。



![](img/a019dd4f18120d1bba780fd4e8073049_162.png)

RightYou can see how this is not too hard to figure out。

 But the more you kind of like role play this and and try to figure it out。

 the more it you can reflect that back into your architectural diagram， which we're not revisiting。



![](img/a019dd4f18120d1bba780fd4e8073049_164.png)

![](img/a019dd4f18120d1bba780fd4e8073049_165.png)

But we managed data strategy here， and so data collection and preparation， data quality， diversity。

 privacy， security concerns， maybe there's a concern， you know。

 there is a concern of copyrighted materials。

![](img/a019dd4f18120d1bba780fd4e8073049_167.png)

![](img/a019dd4f18120d1bba780fd4e8073049_168.png)

So we must purchase and supply materials and store them。



![](img/a019dd4f18120d1bba780fd4e8073049_170.png)

For access in our database and maybe that's why the reg is there。

 So coming back to our architectural diagram I might say well why do we need a vector database。

 maybe we don't go to the Internet。 so maybe that's not something we do but maybe we have a database because we have a warehouse of paid materials and when they ask a question saying like oh I want to practice a sentence it's gonna pull from our library of paid content that we have or materials that the students already using or the teachers already know。

 so we could do this all day， but you have an idea here， the more that you do。

 I'd love to see how far some people might take this。

 but it's again completely optional all I'm looking for is the Jen architecture if you're looking to get Redqua right good assumptions here I'd love to go and see that there。

 I'm going to go ahead and commit this Jen Arch diagram you'll see me in the next video for sentence instructors that I will be making features and stuff like this because this is such a small commit I'm not going to do anything beyond that。

 but that's all I really want you to do right so I go。



![](img/a019dd4f18120d1bba780fd4e8073049_172.png)

![](img/a019dd4f18120d1bba780fd4e8073049_173.png)

![](img/a019dd4f18120d1bba780fd4e8073049_174.png)

![](img/a019dd4f18120d1bba780fd4e8073049_175.png)

![](img/a019dd4f18120d1bba780fd4e8073049_176.png)

![](img/a019dd4f18120d1bba780fd4e8073049_177.png)

![](img/a019dd4f18120d1bba780fd4e8073049_178.png)

HereAnd if I go over to here， I can see the architectural diagram。 So I just want to read me in this。

 you want to embed it in here as well， but it's pretty easy for me to click and see the image。

 But yeah， great。 We have lots of great information there。

 I just want to go and check one more thing here。 So what let's go down and roll and choosing a model。

 So earlier on， I talked about IBM IBM granite And that might be a possible model that we want to explore。

 And so if we go back over here， Does this overlap with anything that。😊。



![](img/a019dd4f18120d1bba780fd4e8073049_180.png)

![](img/a019dd4f18120d1bba780fd4e8073049_181.png)

![](img/a019dd4f18120d1bba780fd4e8073049_182.png)

![](img/a019dd4f18120d1bba780fd4e8073049_183.png)

Chris Chris has here。

![](img/a019dd4f18120d1bba780fd4e8073049_185.png)

Risk constraints， considerations， you know， like this is where I have technical uncertainty。 And I。

 I like having broader self。 And so I might say in this， like we wantna。

 we want to utilize IBM granite。 So I might go back to this for a second。 And Im。

 I'm just gonna deviate from this。 and just say technical considerations。



![](img/a019dd4f18120d1bba780fd4e8073049_187.png)

![](img/a019dd4f18120d1bba780fd4e8073049_188.png)

![](img/a019dd4f18120d1bba780fd4e8073049_189.png)

So， you know， you know， we're considering。

![](img/a019dd4f18120d1bba780fd4e8073049_191.png)

We're considering using IBM granite。As because it's a truly open source。



![](img/a019dd4f18120d1bba780fd4e8073049_193.png)

Open source model with model data that is with training data。That is traceable。嗯。

So we can avoid any copyright issues， and we truly。



![](img/a019dd4f18120d1bba780fd4e8073049_195.png)

Understand we。we， we are able。To know what is going on in the model， right， so we might have that。

 We might want to reference hugging face IBM， but we don't， we don't really know。



![](img/a019dd4f18120d1bba780fd4e8073049_197.png)

![](img/a019dd4f18120d1bba780fd4e8073049_198.png)

What's going to happen until we do it， right？

![](img/a019dd4f18120d1bba780fd4e8073049_200.png)

And these are just assumptions。So I'm just looking for IBM granite here。



![](img/a019dd4f18120d1bba780fd4e8073049_202.png)

Somemer in here， right？There we go， IBM granite。

![](img/a019dd4f18120d1bba780fd4e8073049_204.png)

And so I'll go right here and just put this in as one more comment。And there you go。Sa update。

The best commit message， but try to write your commit messages clearly because I actually have to go through them and check them for me。

 I don't have to check my own commit messages。 though maybe I should probably in properly because maybe students are checking them over。

 and that's something I should do。 But yeah， that's all I want you to do in a separate video。

 I will talk about how to submit grading。 Okay， I'll see the next one， Chow。



![](img/a019dd4f18120d1bba780fd4e8073049_206.png)