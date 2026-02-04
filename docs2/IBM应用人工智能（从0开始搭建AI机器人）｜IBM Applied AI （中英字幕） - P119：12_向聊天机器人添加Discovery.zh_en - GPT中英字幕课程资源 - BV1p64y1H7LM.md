# IBM应用人工智能（从0开始搭建AI机器人）｜IBM Applied AI （中英字幕） - P119：12_向聊天机器人添加Discovery.zh_en - GPT中英字幕课程资源 - BV1p64y1H7LM

🎼。In this video we'll discuss the steps you'll take in the second lab of this module since you'll be taking these steps while working on the lab。

 you can simply focus on watching this video now rather than trying to recreate the steps as you watch the goal of Lab4 is integrating Watson Discovery with your chatbot using IBM functions。



![](img/4302cc581195a5813e882acd18f3c1a6_1.png)

Let's start with Watson Discovery from our IBM Cloud dashboard。

 we'll want to select services to show the list of services we have already instantiated。

 find your discovery service in the list and select it if you don't have a discoveryover instance in your account go back to the lab one in the first module of this course and follow the instructions to create one next you will obtain API key and URL of your discoveryovery instance。

 making note of them for later， then launch Watson Discovery。



![](img/4302cc581195a5813e882acd18f3c1a6_3.png)

![](img/4302cc581195a5813e882acd18f3c1a6_4.png)

![](img/4302cc581195a5813e882acd18f3c1a6_5.png)

Open the Coursera Course catalog collection you previously created。

 select API to retrieve some credentials for this collection。

 make note of collection ID and En ID we are going to need these to query the collection from our function。



![](img/4302cc581195a5813e882acd18f3c1a6_7.png)

![](img/4302cc581195a5813e882acd18f3c1a6_8.png)

Let's navigate to the Skills Network Lab， log into the SN labs with your cognitive class or other social media accounts。



![](img/4302cc581195a5813e882acd18f3c1a6_10.png)

Once you logged in， select Jupiter Lab this process can take a few minutes to launch once the Jupiter La is opened。

 we'll make sure to select Python 3。

![](img/4302cc581195a5813e882acd18f3c1a6_12.png)

![](img/4302cc581195a5813e882acd18f3c1a6_13.png)

This is what a Jupiter La notebook looks like。In the first cell。

 you'll copy the lines provided in the lab and then run the cell to evaluate it。

This will copy the scripts and configuration that we'll need in our lab。



![](img/4302cc581195a5813e882acd18f3c1a6_15.png)

At this point you should see a lab 4 folder in your Jupiter lab environment This folder contains all the code and configuration for our serverless function This function will connect to the discovery service and retrieve the list of courses from our collection for us select the La 4 folder and then the La4 adding discovery to chatbot subfolder you will see a file called serverless。

yMl In this file you'll replace the credential values we made note of earlier on and save the configuration then you'll create another cell and copy more code from the lab before running this new cell This will install some libraries will need to interact with IBM cloud Next you will need to log in to your IBM cloud account from the notebook to log into your account you'll create a new cell and copy the snippet of code provided in the lab。



![](img/4302cc581195a5813e882acd18f3c1a6_17.png)

![](img/4302cc581195a5813e882acd18f3c1a6_18.png)

![](img/4302cc581195a5813e882acd18f3c1a6_19.png)

Here you'll specify your IBM Cloud credentials and run the cell once。

We'll output some information about our account so that we can retrieve the region and name of the organization from our IBM Cloud account。

 we'll use that information to create a space within that organization and region。



![](img/4302cc581195a5813e882acd18f3c1a6_21.png)

![](img/4302cc581195a5813e882acd18f3c1a6_22.png)

Next we'll target that space， install some required libraries for our serverless infrastructure and deploy our JavaScript function to cloud functions at any time we can list all the functions we created。

 in our case we'll only have one that ends with/ Connect Discovery Next we'll want to retrieve the API key for our function so that we can later on use it to call the function from Watson Asant。



![](img/4302cc581195a5813e882acd18f3c1a6_24.png)

![](img/4302cc581195a5813e882acd18f3c1a6_25.png)

To find the information， we'll log in on IBM Cloud and find the functions section。



![](img/4302cc581195a5813e882acd18f3c1a6_27.png)

We'll find a list of actions and select the one we created from here we'll select endpoints。

 where we will obtain the URL for the action and make copy of it。

 we'll then select API key to show and copy the Cloud Foundry based API key these will be used in Watson Asistant You're now all set to begin integrating this function with Watson assistantsant from your IBM Cloud dashashboard launch your Watson Asant service。



![](img/4302cc581195a5813e882acd18f3c1a6_29.png)

![](img/4302cc581195a5813e882acd18f3c1a6_30.png)

![](img/4302cc581195a5813e882acd18f3c1a6_31.png)

Select your student advisoror skill and then select the Option section here you will be given the opportunity to provide the URL for our action as well as our authorization credentials derived from the Cloud Foundry based API key we recently retrieved in a previous step。



![](img/4302cc581195a5813e882acd18f3c1a6_33.png)

Finally， we'll save these credentials， find the courses node in the dial and add a child node named discoveryy below it。

 we'll need to customize courses to use web hookooks we'll find the relevant section and toggle it on Now we will add a parameter input as a key and quote lesss than question mark input dot text Que mark greater than end quote as its value Sc down and set the return variable to webhook underscore result underscore1 Next we'll indicate that the final action for node should be a jump to the discovery node we created specifically we'll jump to evaluating the condition for the node。



![](img/4302cc581195a5813e882acd18f3c1a6_35.png)

![](img/4302cc581195a5813e882acd18f3c1a6_36.png)

![](img/4302cc581195a5813e882acd18f3c1a6_37.png)

![](img/4302cc581195a5813e882acd18f3c1a6_38.png)

![](img/4302cc581195a5813e882acd18f3c1a6_39.png)

![](img/4302cc581195a5813e882acd18f3c1a6_40.png)

With the new node selected， we'll set the condition as true as we always want to execute it when giving course recommendations。

Add the following sample response， which retrieves a list of relevant courses from discovery via the function we defined earlier on Now you're all set try running。

 recommend me a course on databases in try itout panel to confirm that the node works as expected if you see a result similar to the image below you are all set for this lab in the next section of this course you' will find the lab where you'll have an opportunity to take these steps yourself。



![](img/4302cc581195a5813e882acd18f3c1a6_42.png)

![](img/4302cc581195a5813e882acd18f3c1a6_43.png)

![](img/4302cc581195a5813e882acd18f3c1a6_44.png)

![](img/4302cc581195a5813e882acd18f3c1a6_45.png)