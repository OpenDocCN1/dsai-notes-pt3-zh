# IBM应用人工智能（从0开始搭建AI机器人）｜IBM Applied AI （中英字幕） - P110：3_为您的聊天机器人添加语音选项.zh_en - GPT中英字幕课程资源 - BV1p64y1H7LM

🎼。Watson Assant provides an intuitive interface to data；

 it captures why artificial intelligence is in a class by itself。



![](img/e667a0c5c60c6973de927f1154794f54_1.png)

We're no longer just limited to explicit interfaces with Watson you can now explore natural。

 implicit interfaces to data， while chatbots are wonderful pieces of technology。

 there are many ways to interact with them， and which one works best depends on your application。



![](img/e667a0c5c60c6973de927f1154794f54_3.png)

![](img/e667a0c5c60c6973de927f1154794f54_4.png)

![](img/e667a0c5c60c6973de927f1154794f54_5.png)

![](img/e667a0c5c60c6973de927f1154794f54_6.png)

For example， some use cases call for text based interfaces and some for voice based interfaces。

 however most often， voice based interfaces are more intuitive and easy to use compared to their text based counterparts。

This is because voicebased interfaces require less effort to leverage on the user's part Speech is a communication ability that humans have had for over 1。

3 million years， whereas written language has only been around for about 6000 years when going about implementing a voicebased interface for your Watson assistant chatbots there are three main paths you can take。



![](img/e667a0c5c60c6973de927f1154794f54_8.png)

Making the chatbot available through phone calls， implementing the solution yourself。

 implementing an application that leverages Watson's speech to text and text to Sp APIs。



![](img/e667a0c5c60c6973de927f1154794f54_10.png)

![](img/e667a0c5c60c6973de927f1154794f54_11.png)

And finally， making the chatbot available through the phone。

 relying on the easy integration offered by the voiceice agent with Watson service， there are。

 of course， other options， including integration with devices such as Amazon Echo We're not going to cover them in this course。

 but the skills you'll learn will equip you to quickly figure out how to integrate Watson services with any thirdparty channels on your own。

 but let's go over the advantages and disadvantages of these three approaches。



![](img/e667a0c5c60c6973de927f1154794f54_13.png)

![](img/e667a0c5c60c6973de927f1154794f54_14.png)

![](img/e667a0c5c60c6973de927f1154794f54_15.png)

![](img/e667a0c5c60c6973de927f1154794f54_16.png)

![](img/e667a0c5c60c6973de927f1154794f54_17.png)

First， let's discuss using phone calls as an interface for Watson assistantant in this case let's assume you're using an API like Twilio。

 which provides built in speech to text and text to speech abilities phone calls are great for accessibility。

 no matter what kind of phone someone's using。

![](img/e667a0c5c60c6973de927f1154794f54_19.png)

![](img/e667a0c5c60c6973de927f1154794f54_20.png)

![](img/e667a0c5c60c6973de927f1154794f54_21.png)

Whether or not they have an Internet connection or in some cases， whether or not they have power。

 they can access the services provided by the chatbot。

 This also enables quick access instead of having to download an application to interface with the chatbot。

 they just need to call a phone number， however， from a development and implementation perspective。



![](img/e667a0c5c60c6973de927f1154794f54_23.png)

![](img/e667a0c5c60c6973de927f1154794f54_24.png)

![](img/e667a0c5c60c6973de927f1154794f54_25.png)

![](img/e667a0c5c60c6973de927f1154794f54_26.png)

This kind of interface does introduce a few problems。 For example。

 service orchestration needs to be done by you。

![](img/e667a0c5c60c6973de927f1154794f54_28.png)

![](img/e667a0c5c60c6973de927f1154794f54_29.png)

This means you need to manually connect， integrate and test Watson assistant with the voice API you're using if you are using any other APIs along with the assistant。

 you'll need to plug those in manually as well this approach isn't very flexible either as you are limited to the keypad and voice on the phone and can't take any other form of input like touch。

 acceleration or visual input。

![](img/e667a0c5c60c6973de927f1154794f54_31.png)

![](img/e667a0c5c60c6973de927f1154794f54_32.png)

![](img/e667a0c5c60c6973de927f1154794f54_33.png)

![](img/e667a0c5c60c6973de927f1154794f54_34.png)

![](img/e667a0c5c60c6973de927f1154794f54_35.png)

Secondly， there's the Watson Spch APIs app option。

![](img/e667a0c5c60c6973de927f1154794f54_37.png)

Essentially this approach entails that you develop your own application that the user will download or access online。

 this will typically be a mobile application that will handle the interaction between the user and the bot by leveraging Watson's speech to text and text to speech。



![](img/e667a0c5c60c6973de927f1154794f54_39.png)

![](img/e667a0c5c60c6973de927f1154794f54_40.png)

This approach is usually a good idea if there's some special functionality that your application or chatbot offers that no other more common interface or messaging application can provide this approach is quite flexible as well。

 but it's worth noting that it often comes at the extra inconvenience of the user having to download an application to their device。

 you may also need to develop this application for more than one operating system if you want it to be accessible to a wider user base。



![](img/e667a0c5c60c6973de927f1154794f54_42.png)

![](img/e667a0c5c60c6973de927f1154794f54_43.png)

![](img/e667a0c5c60c6973de927f1154794f54_44.png)

![](img/e667a0c5c60c6973de927f1154794f54_45.png)

For example， you'll want to support both iOS and Android if developing a mobile app。

 this second approach also requires you to handle and implement the orchestration between Wats and services by yourself。



![](img/e667a0c5c60c6973de927f1154794f54_47.png)

![](img/e667a0c5c60c6973de927f1154794f54_48.png)

Finally， let's talk about the voice agent with Watson approachEssential this is a simple。

 yet powerful way to expose Watson assistant over the phone。



![](img/e667a0c5c60c6973de927f1154794f54_50.png)

![](img/e667a0c5c60c6973de927f1154794f54_51.png)

It can be integrated with an SIP trunk， which stands for Session initiation protocoltocol in simpler words you get a phone number assigned to you and voice agent allows people to talk with your chatbot when dial that number。



![](img/e667a0c5c60c6973de927f1154794f54_53.png)

![](img/e667a0c5c60c6973de927f1154794f54_54.png)

![](img/e667a0c5c60c6973de927f1154794f54_55.png)

Behind the scenes the user voice is converted to text via Watson's speech to text。

 the resulting text is sent to Watson Assant， its response is then sent through Watson text to speech to produce the final audio response for the user on the other end of the phone the main advantage of this approach is that the orchestration between Watson's speech to text。

 Watson Assant and Watson textex to Sp is all done for you。



![](img/e667a0c5c60c6973de927f1154794f54_57.png)

![](img/e667a0c5c60c6973de927f1154794f54_58.png)

![](img/e667a0c5c60c6973de927f1154794f54_59.png)

![](img/e667a0c5c60c6973de927f1154794f54_60.png)

Nevertheless， you can customize it through your own SOE or service orchestration engine voice agent does all the heavy lifting。



![](img/e667a0c5c60c6973de927f1154794f54_62.png)

![](img/e667a0c5c60c6973de927f1154794f54_63.png)

Taking care of integrating these Watson services with the SIP trunk you provided。

 it also offers lots of powerful features， one of which is Bargen。

 which enables users to stop Watson by talking over it。

 as well as a way to easily connect directly to a human agent。



![](img/e667a0c5c60c6973de927f1154794f54_65.png)

![](img/e667a0c5c60c6973de927f1154794f54_66.png)

![](img/e667a0c5c60c6973de927f1154794f54_67.png)

If you are looking to deploy your chatbot over a phone interface。

 Voice agent with Watson is definitely the right approach One disadvantage is that some advanced features are only available when voice agent is deployed on premises through the IBM voice gateateway。

 which would require a hybrid IBM cloud approach that includes both public and private cloud components。



![](img/e667a0c5c60c6973de927f1154794f54_69.png)

![](img/e667a0c5c60c6973de927f1154794f54_70.png)

![](img/e667a0c5c60c6973de927f1154794f54_71.png)

![](img/e667a0c5c60c6973de927f1154794f54_72.png)

To summarize， there are many ways to give a voice to your chatbot。



![](img/e667a0c5c60c6973de927f1154794f54_74.png)

In the labs for this module we'll pick the second approach as it is the most flexible and educational one。

 using Python you'll in fact integrate Watson Assistant and Watson Sp APIs。



![](img/e667a0c5c60c6973de927f1154794f54_76.png)

![](img/e667a0c5c60c6973de927f1154794f54_77.png)