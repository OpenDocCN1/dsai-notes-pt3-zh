# IBM应用人工智能（从0开始搭建AI机器人）｜IBM Applied AI （中英字幕） - P114：7_将您的聊天机器人部署到Slack.zh_en - GPT中英字幕课程资源 - BV1p64y1H7LM

🎼。Slack is a communication tool typically used by people working in a team。



![](img/513a180df0c8f09dcde106c2738295ee_1.png)

You can improve the workflow in your team or set reminders of important events with your friends and family by deploying chatbots on Slack。



![](img/513a180df0c8f09dcde106c2738295ee_3.png)

For this lab， you will integrate our chatbot with Slack。



![](img/513a180df0c8f09dcde106c2738295ee_5.png)

We'll start off by creating a Slack app， The first step is to create a Slack Workspace to get started we'll head over to Slack。

com here you'll enter your email address to get started。

 give your new workspace a name of your choice and do the same for project and team name after you created the workspace will proceed to creating a Slack app to allow it to communicate with our Watson Assistant chatbot。

 so our step2 is signing into Slack Workspace and then visiting the apps section of the Slack website。



![](img/513a180df0c8f09dcde106c2738295ee_7.png)

![](img/513a180df0c8f09dcde106c2738295ee_8.png)

![](img/513a180df0c8f09dcde106c2738295ee_9.png)

![](img/513a180df0c8f09dcde106c2738295ee_10.png)

![](img/513a180df0c8f09dcde106c2738295ee_11.png)

Once there， we'll create a new app。

![](img/513a180df0c8f09dcde106c2738295ee_13.png)

You want to give your app a name and specify the workspace that you want to deploy this app on。

 then create the app。

![](img/513a180df0c8f09dcde106c2738295ee_15.png)

Now that we have a Slack app， we'll need to create a Slack bot user from the relevant section in the Slack API section of the Slack website here we'll add a new bot user。



![](img/513a180df0c8f09dcde106c2738295ee_17.png)

![](img/513a180df0c8f09dcde106c2738295ee_18.png)

We'll ensure the bot is always online and ready to answer our users and then create the user。



![](img/513a180df0c8f09dcde106c2738295ee_20.png)

Next we'll make note of our client ID， client secret。

 and verification token we'll need these credentials when integrating Slack from within Watson Assistant。



![](img/513a180df0c8f09dcde106c2738295ee_22.png)

![](img/513a180df0c8f09dcde106c2738295ee_23.png)

Now， we need to install our Slack app within our workspace and we'll also need to authorize it。



![](img/513a180df0c8f09dcde106c2738295ee_25.png)

![](img/513a180df0c8f09dcde106c2738295ee_26.png)

Save the Oathth access token and bot user Oathth access token that will be provided。



![](img/513a180df0c8f09dcde106c2738295ee_28.png)

Now that we have all these credentials for our Slack app。

 the next step is to add a Watson assistant integration for Slack。

Log into your IBM cloud account and launch your Watson Assistant instance。

Select our Student Advisor chatbot。

![](img/513a180df0c8f09dcde106c2738295ee_30.png)

From the assistanceance section we'll add an integration。



![](img/513a180df0c8f09dcde106c2738295ee_32.png)

Here we'll select a service like we did in the previous lab。

 but this time we'll of course select Slack。

![](img/513a180df0c8f09dcde106c2738295ee_34.png)

Here we'll paste some of our credentials， namely verification token， OOth access token。

 and bot user OOth Access token， This allows Watson assistant to connect to Slack。



![](img/513a180df0c8f09dcde106c2738295ee_36.png)

![](img/513a180df0c8f09dcde106c2738295ee_37.png)

We'll also be able to generate a request URL for our Slackbot to subscribe to we will make note of it as we'll need it to configure our Slackbot back in Slack will need to enable incoming web hooks。



![](img/513a180df0c8f09dcde106c2738295ee_39.png)

![](img/513a180df0c8f09dcde106c2738295ee_40.png)

![](img/513a180df0c8f09dcde106c2738295ee_41.png)

Next we enable events and connect Slack to the request URL we received from Watson Assistant whenever a selected event happens in Slack。

 an HTTP call to this URL will notify Watson assistantant so that it can respond appropriately the events that will want to enable our message。

 IM and app underscore mention this will enable both direct messages and mentions to trigger a response from the chat bot。



![](img/513a180df0c8f09dcde106c2738295ee_43.png)

![](img/513a180df0c8f09dcde106c2738295ee_44.png)

![](img/513a180df0c8f09dcde106c2738295ee_45.png)

![](img/513a180df0c8f09dcde106c2738295ee_46.png)

![](img/513a180df0c8f09dcde106c2738295ee_47.png)

You know the drill now it's your turn to implement the actual steps in the next lab。 Good luck。



![](img/513a180df0c8f09dcde106c2738295ee_49.png)