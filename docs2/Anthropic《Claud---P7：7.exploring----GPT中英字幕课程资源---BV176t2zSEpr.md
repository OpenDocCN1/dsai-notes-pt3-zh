# Anthropic《Claude Code 高度主动式编程助手｜Claude Code A Highly Agentic Coding Assistant》中英 - P7：7.exploring-github-integration-&-hooks.zh_en - GPT中英字幕课程资源 - BV176t2zSEpr

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_0.png)

In this lesson， you'll learn how to use cloud code outside of the terminal with a Gitthub integration。

 You'll see how to set up cloud code to review pull requests and fix issues in Gitthub。

You'll then learn how to execute code before and after using tools through Cla code hooks。

 Let's dive it。 We left off in the last section， merging our work trees together。

 But we forgot to ask Clade to remove those work trees。 So we're gonna to hop back into Cla。

 So I'm going to go and pass in the resume flag to go back to a previous conversation that I had with my work trees in this particular conversation。

 we can now go back to where we were before and finish up with removing our work trees。

 So let's ask Claude remove the dot trees folder and the underlying work trees。 and once you're done。

 push this code to get up。 So let's go ahead give Cla code a second to run the necessary git commands to remove that folder and then push our merge code to Gi up。

😊。

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_2.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_3.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_4.png)

We'll go ahead and give cloud code access to see the underlying work trees so that we not only remove the work trees。

 but also delete the corresponding branches。 We'll go ahead and remove these particular trees now remove the directory and then remove the underlying branches。

 Now that we've done that， let's go ahead make sure that worked as expected。 which is good。

 we don't have that folder。 And now let's push this code to Github。

 We'll confirm that we want to run the gi push origin main command。

 And it looks like our code is push to Github。 Now that we've committed and push our code to Github。

 Let's start installing the Github integration that comes with cloud code。

 I'll do that using the install Github app command。

 here you might see that you need to include additional authentication using the command line interface。

 So if you see those setup instructions， make sure to follow them。

 We'll now be able to install the Github app for the current repository that we're working in。

 So let's go ahead and do that。 This will open up the browser。 And if I have not yet。😊。



![](img/7b3dd101bf8aa901d7ddca0c39cd9201_6.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_7.png)

Figed I'll have the option to install What this integration allows us to do is use cloud code in pull requests and issues to respond to feedback。

 fix errors， modify code and much more。 in order for this functionality to exist。

 It's built on top of the software development kit that comes with cloud code。

 This SDK allows you to use cloud code outside of the terminal interface。

 So let's head back to the terminal。

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_9.png)

And specify the workflows we want to install。 These workflows allow for tagging Cla in issues and using Cla to automatically review code in our poll requests。

 Let's install both。 We'll create a long live token。



![](img/7b3dd101bf8aa901d7ddca0c39cd9201_11.png)

And here we'll have to authorize and authenticate with Cla Once that's done。

 we can head back and we'll see that it's creating the repository information。

 sending up any additional information I need， and sending me right back to Github to open a poll requests with the changes that have been made we can see here automatically this poll request allows for Github actions to enable bug fixes。

 writing tests and code reviews， we can change this if we'd like。

 or we can go ahead and create a poll request with a default information in this poll request we can see that not only have we created a Yaml file for cloud to operate。

 We also have one for code reviews here we can see out of the box we have some pretty s defaults。

 we can filter by authors， we can specify what this is running on but out of the box。

 we get quite a bit of really nice functionality if you'd like to modify the prompt that you have in your code review you can do that here and since this is a file that is track by Git you can constantly edit this。



![](img/7b3dd101bf8aa901d7ddca0c39cd9201_13.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_14.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_15.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_16.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_17.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_18.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_19.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_20.png)

If you need， I'm gonna go ahead now and merge this in so we can start using cloud code in Github。

 We can go ahead and see right out of the box that a cloud Github action has actually started。

 This is what we're going to see out of the box in our future poll requests it's going to read and analyze files check code quality identify security considerations and out of the box we now have a new teammate Cla to check the work that we and our other team members are doing。

 This sometimes takes a little bit of time to start but once this has finished。

 we'll get some detailed assessments from cloud and we'll be able to merge in the poll request when we're ready so it looks like the review is done and depending on the prompt that we give it we can specify how much depth and information we want here we see some things that are working well maybe some considerations that we might need and if this looks good to us we can merge in that poll request now we're going to see out of the box in future poll requests Cla will help review our code this is really helpful when humans might miss certain things and extra step to check that what you have。



![](img/7b3dd101bf8aa901d7ddca0c39cd9201_22.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_23.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_24.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_25.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_26.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_27.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_28.png)

Working as expected。 Let's imagine there's a situation where an issue comes up。

 Someone on our team decides to add a new issue。 we could do this in Github。

 we could even do this in cloud code as you might have noticed as we kept building on top of this application we started to see a new header that was added This new header might look kind of nice。

 but maybe we want to revert to what we had previously So let's add an issue see if cloud can help us out You can imagine we have an issue here。



![](img/7b3dd101bf8aa901d7ddca0c39cd9201_30.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_31.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_32.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_33.png)

The application has a new header that was added， let's go back to the old one。

 make sure to keep the toggle theme， but just make the header look like what it was before。

 we'll also specify make sure to remove the course material assistant header。

 remove the subheader around ask questions and then remove the horizontal row below the subheader。



![](img/7b3dd101bf8aa901d7ddca0c39cd9201_35.png)

Now that we created this issue， we could assign someone to tackle it。

 but why don't we just ask Claude to help us out。 Claude。

 can you fix this for me Once we tag in Claude， we're gonna to start to give Claude a little bit of time to fix the issue at hand when Cla is fix that issue it should be able to generate a pull request to fix that particular one So let's give Claude a little bit of time to find that action here we're gonna to see Cla code is working and if we want to see the underlying job that's run。

 we can go ahead and do that So let's give Clade a little bit of time and see what it can come up with What you're seeing is going to look very familiar to what we saw in the command line analyze the structure remove the header and here I can even choose what to prioritize if I'd like but what you're seeing here is the same thing we saw just outside of the terminal not only can we use Cla to tackle issues and pull requests we can also use Cla to review code as we saw before as we start to see its plan we'll notice what the changes are that are being made where in the code base its proposing things and as we see the pull。



![](img/7b3dd101bf8aa901d7ddca0c39cd9201_37.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_38.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_39.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_40.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_41.png)

We can start to see some of the thinking and logic behind what's being done。

 Sees like this one isn't too tough。 So it's going to follow these steps， Test the changes。

 commit and push those。 It's now made the commit necessary。

 We can see the underlying description here。

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_43.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_44.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_45.png)

If we'd like， we can create this pull request or we can just have Cla do all that work for us。

 when we create the pull request， we see exactly what was generated in the commit。

 And now let's go take a look。 see what Cla did。 We can take a look at the underlying files that we changed。

 There wasn't too much here。 We merge this in。 As we saw before。

 Cla's also going to take some time and review the code。 that Cla wrote。

 And this can actually be quite helpful because as much as we want to trust Claude。

 it's nice to have another claw double checking its work。

 So it looks like Cla code has approved the task I have here。 Let's merge this in。

 and then we'll head back to the terminal and make sure to pull down the changes that we have。

 So I'll head over to Vs code。 pull down the changes。😊。



![](img/7b3dd101bf8aa901d7ddca0c39cd9201_47.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_48.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_49.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_50.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_51.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_52.png)

And let's see far front end looks any better。

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_54.png)

And there we have it。 The headers taken out the horizontal rows taken out。

 We might want to bring back that horizontal row or move this to another place。

 but now we know how to do it not only in the terminal， but also in Giub。

 One more piece of functionality that I want to show is something that was recently released。

 which is the ability to add what's called a hook to cloud code if you're familiar with this idea of hooks。

 This is gonna to feel very similar。 The idea is that as we have different operations in cloud code like executing a tool or something happening after a tool we can inject specific code to run at any point in the lifecycle of cloud code's operation。

 Let me show you what I mean by that back in Vs code， I'm gonna hop in back to cloud again。

 And while we can make these changes manually I want to show you the editor that we have So I'm gonna type inlash hooks manage configurations for tool events。

 What you're seeing might look a little bit scary。 but it's our obligation to let you know if you are running arbitrary shell。

😊。

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_56.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_57.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_58.png)

Commands you have to be very careful about what you're doing。

 There are quite a few different events that we can run hooks before a tool is executed。

 we can even stop that tool from being executed。 we can do something after when a notification is sent when the user submits a prompt when something stops or even before a subag concludes its response。

 So we have the ability programmatically to tap in to any of these events I want to show a simple example with a post tool use hook start by adding a match in this matcher I can specify the tools that I want to be matched for this hook to run I'm going add a very very simple example here any time there is a read or any time there is a I'm going run a simple terminal command the new hook or command I'm gonna run is the say command the say command runs the computers audio and a path for what text you'd like it to say So if I've done this correctly after we have read something or use the。

😊。

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_60.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_61.png)

![](img/7b3dd101bf8aa901d7ddca0c39cd9201_62.png)

ToTo find something in a file our machine should say all done。

 Let's add this again in our project settings。 We mentioned earlier the settings local json file where we can specify permissions。

 This is also where your hook slip inside of our do cloud we can see in our settings local Json not only do we have our permissions but we now have a hook that we've defined host tool use is the name of the hook the matcher which if you take out will apply to anything But here reading or grip。

 go run the command， say all done when we're done。 let's try this out。

 I'm gonna to quit at a cloud code。 I'm gonna open it up again read the contents of the runsh file。

 This should use the read tool as expected all done and once it's done it notifies us and tells us all done while this is kind of a fun little example。

 you can imagine executing code like running tests or runninglins or potentially stopping tools from being used if that's not what we want or even having cloud review itself。



![](img/7b3dd101bf8aa901d7ddca0c39cd9201_64.png)

When certain things happen， there's a lot you can do with hooks and there's so much more that's coming。

 So make sure to look at the documentation to see everything you can do。

 and you can always use cloud code to write hooks for you and modify them accordingly in the next section。

 we'll explore using cloud code with Jupyter notebooks to create visualizations。

 refactor code and operate in a slightly different environment。😊。



![](img/7b3dd101bf8aa901d7ddca0c39cd9201_66.png)