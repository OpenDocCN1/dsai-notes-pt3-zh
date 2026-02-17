# Anthropic《Claude Code 高度主动式编程助手｜Claude Code A Highly Agentic Coding Assistant》中英 - P9：9.creating-web-app-based-on-a-figma-mockup.zh_en - GPT中英字幕课程资源 - BV176t2zSEpr

![](img/2c28b42201aea7b037177541de5cf7c9_0.png)

In this last lesson， you'll connect Claud to the Figma MCP server to import a design mockup to cloudcode and develop the application。

 Let's have some fun now that we've seen how to use cloudcode to get up to speed on codebas to create applications and work across many different environments I want to showcase really powerful ability for cloudcode to work alongside MCP servers to take mockups from tools like Figma and turn them into web applications quickly in order to do that。

 we're gonna to be making use of the Figma MCP server and in order to do that you will need a Figma account we'll also provide an alternative if you want to use that without subscribing to Figma's dev mode we're also going to be using our playwright MCP server so that we can analyze a mockup from Figma generate the necessary HTML and then programmatically test that by opening it in the browser and taking screenshots of how best to interact with this application。

Since I'm building a front end application with a more modern technology stack。

 I'm going to be using N Js to do that。 So I'm just going to start by creating a N Js application with the latest version inside of the folder that I'm in。

 I'll follow most of these same defaults。 and I'll go ahead and let it install the necessary dependencies。

 If you have not worked with next Js before。 that's more than fine。

 it's a couple command line commands and then we'll be in the browser before you know it。

 While this is installing。 let's go take a look at the mock up that we have in Figma in Figma。

 I have a mock right here for a dashboard that I'd like to build using federal Reserve economic data。

 This mock right here in Figma is not the most detailed in terms of all the layers and all the analytics behind。

 but this is enough to get me started。 What I'm going to do in Figma is first make sure that I have gone to preferences and selected enable dev mode MCP server。

 Once I have that selected。 I'm going to take this。😊。



![](img/2c28b42201aea7b037177541de5cf7c9_2.png)

![](img/2c28b42201aea7b037177541de5cf7c9_3.png)

![](img/2c28b42201aea7b037177541de5cf7c9_4.png)

![](img/2c28b42201aea7b037177541de5cf7c9_5.png)

particular layer that I have and copy it because I'm gonna need that when I specify what to use with the MCP server Now that I've successfully created this next JS application。

 we need to add to Cla the two MCP servers that I want to use for Figma and for playwright I'm going go ahead and add the necessary command here to bring in the MCP server for Figma and then I'll do the same for playwright so I'm going to add an MCP server for playwright and that is started locally using the following command and even though we already added this remember we're in a separate project in a separate environment so this does not get applied to every single cloud code application I built we have to do this for each one to make sure I've done this correctly I'm going to hop into cloud and I'm going to use the MCP command to make sure this looks good if I take a look I can see that both of these are connected and if I take a look at the dev mode MCP server I can see there are five tools available to get underlying code。



![](img/2c28b42201aea7b037177541de5cf7c9_7.png)

To get an image， to get design rules around a particular mockup that I have in Figma Now that we've connected to both of our MCP servers。

 let's go and ask Claud to use the following Figma mockup and the Figma MCP server to analyze and build the underlying code necessary。

 we'll ask it to use the recharts library for creating charts。

 and then we'll check how this application looks using the Playwright MCP server。



![](img/2c28b42201aea7b037177541de5cf7c9_9.png)

![](img/2c28b42201aea7b037177541de5cf7c9_10.png)

But before I do this， I want to go ahead and make a quick change。

 If you are able to make this change and you're not on the pro plan。

 you can use Ous as a different model。 If not， Sonet will still do a fine job。

 but Ous will do slightly better for a little bit more of a complex task。

 Once I've switched to that model。 Let's go ahead and run our prompt and see how it does。

 We'll first need to connect to our MCP servers make sure we use the correct mockup and the tools necessary to write the underlying code to power this mock。

 here we can see we're using the getim tool from the Figma dev MCcP server followed by the get code tool to get the underlying code behind that mock。

 We'll then make sure we install the necessary dependencies using NM or the package manager。

 And here we're gonna to see it's not installed。 So cloudcode is most likely going to ask us to install it。

😊，We'll do so and continue onwards。 Since we're inside of this next Js application。

 we're gonna to be doing the majority of the work in the app folder。 We'll analyze any global Css。

 And here start creating the main dashboard structure。

 here we're gonna add a little bit of metadata and this looks good。 So for future edits。

 I'll just let Clade go ahead and run those。 We're now going create the dashboard layout and build this with more of a componentbased architecture and react。

 Now that we've created the underlying structure。 let's start to make sure things look as expected。

 And since I've already run the server here。 I'm just going to say don't run the server。

 It's already running Con on。 We're now going to test with playwright and take a look at how things are。

 we'll go ahead and navigate to localho 3000 take a picture of that as well。

 let's go ahead and let it take a screenshot。 we can see here in playwright So far。

 it's looking pretty good compare it to the mock。 we've got a little extra styling on some of these bars。

 But this is a pretty good start from where we began with the mock right over here。 In fact。

 I'd actually argue this looks a little bit nicer。 We're still。😊。



![](img/2c28b42201aea7b037177541de5cf7c9_12.png)

![](img/2c28b42201aea7b037177541de5cf7c9_13.png)

![](img/2c28b42201aea7b037177541de5cf7c9_14.png)

![](img/2c28b42201aea7b037177541de5cf7c9_15.png)

See some changes that are being made。 There's a layout and the sidebar that needs to be modified。

 and we can always have a cloud go back and forth and iterate across this particular mock。

 One important thing to mention is that this mock in Figma does not have a tremendous amount of layers and underlying components so a lot of this is going to depend on the quality of the underlying mock that you have but this is a really good start with very minimal amount of time we can see here what's been built and what's closely matching Now let's take a look at how things are we can see with a little bit of work from the model and using MCP servers to verify visualizations and build off from mocks things that might have taken days to do and build from scratch can be done over the course of minutes so you might be wondering what comes next here this mock that we have is just the start of what you might imagine building and this data is actually available through an API so I could ask cloud code populate these charts with real worldorld data from the Federal Reserve economic data we'll go ahead and。



![](img/2c28b42201aea7b037177541de5cf7c9_17.png)

![](img/2c28b42201aea7b037177541de5cf7c9_18.png)

![](img/2c28b42201aea7b037177541de5cf7c9_19.png)

![](img/2c28b42201aea7b037177541de5cf7c9_20.png)

![](img/2c28b42201aea7b037177541de5cf7c9_21.png)

Cud code to use one of its web search tools to go ahead and find information to update with actual data Here we'll look at CP。

 unemployment， yields and so on。 but you can imagine this might be data that you're fetching from a backend but here we're going to showcase Cla's ability to research how to work with the API documentation how to fetch data and it might be possible that we need an API key to do so。

 so as we start doing some of this research， Cla's going to let us know what we need to make sure things are working as expected in that mock there were a couple other pieces in the navbar that we're just meant for visualizations but we can add whatever underlying functionality we want next so after it's done some research it realizes that in order for me to fetch actual data from the Federal Reserve。

 I'm going to need to put in an API key I can go ahead to my account get an API key。



![](img/2c28b42201aea7b037177541de5cf7c9_23.png)

![](img/2c28b42201aea7b037177541de5cf7c9_24.png)

This is a relatively simple process that you can see here。Once I have my API key。

 it's going to start writing additional code for me to fetch data and display data visually。

 so I'm going to go ahead and update my API key inside of here。



![](img/2c28b42201aea7b037177541de5cf7c9_26.png)

Now that I've updated the API key， let's see where Cla is at with building additional data。

 it's now written as service to fetch economic data。

 we're now going to update the dashboard and fetch real data using our API。



![](img/2c28b42201aea7b037177541de5cf7c9_28.png)

![](img/2c28b42201aea7b037177541de5cf7c9_29.png)

![](img/2c28b42201aea7b037177541de5cf7c9_30.png)

![](img/2c28b42201aea7b037177541de5cf7c9_31.png)

We're going to test this in playwright， and we're going to go ahead and then take a look at what we have in the browser。

 We'll go see how this looks visually and if there's any underlying code that needs to be modified to make this more visually appealing。



![](img/2c28b42201aea7b037177541de5cf7c9_33.png)

![](img/2c28b42201aea7b037177541de5cf7c9_34.png)

Withch is a little bit of prompting， we can go from the mock with some fake data to actually using real worldor information across a true data source for this data。

 When we're done， we'll head back to localho 3000 take a look at what we have and see that the data that will be fetching is not something that's actually fictitious。

 but real unemployment tenure treasuries and so on。

 we set up quite a bit here to proxy our requests and quite a few more interactive features。

 So let's go see what that looks like。 We've gone from our mock here with some fake data and not a lot of functionality to something quite powerful in just a short period of time。

 The data we're loading here。 His data that is actually reflective of realwor information。

 And as we imagine adding more functionality。 we can tab through for what this will look like。

 but with just a small amount of work with an MCP server pulling data from real world environments and building Us from Figma Mos you can start to imagine how quickly front and development can go especially for building power。

😊。

![](img/2c28b42201aea7b037177541de5cf7c9_36.png)

![](img/2c28b42201aea7b037177541de5cf7c9_37.png)

![](img/2c28b42201aea7b037177541de5cf7c9_38.png)

Re world interfacesYou might want to verify that this data is actually coming from the source。

 and we built that here with this details functionality。



![](img/2c28b42201aea7b037177541de5cf7c9_40.png)

So we can easily see where this data is coming from what things look like and track that back to the dashboards that we're building as well。

 So right here， we're just showing some key indicators。

 But maybe the next thing I want to do is start building my own interface or use another Figmam for things like inflation。

 employment and so on。 So we'll start with this piece of data。

 But I'd love to see what else you can build using this interface and all the data at your fingertips。

😊。

![](img/2c28b42201aea7b037177541de5cf7c9_42.png)

![](img/2c28b42201aea7b037177541de5cf7c9_43.png)