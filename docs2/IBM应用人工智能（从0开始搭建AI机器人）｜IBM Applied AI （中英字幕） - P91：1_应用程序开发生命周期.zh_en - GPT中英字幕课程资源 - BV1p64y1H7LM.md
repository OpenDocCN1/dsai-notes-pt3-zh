# IBM应用人工智能（从0开始搭建AI机器人）｜IBM Applied AI （中英字幕） - P91：1_应用程序开发生命周期.zh_en - GPT中英字幕课程资源 - BV1p64y1H7LM

![](img/b80da62518b7772d1b21885f0f826658_0.png)

Welcome to Application Development Lifecycle After watching this video。

 you will be able to list the steps in the application development lifecycle。

 describe the different phases of the application development lifecycle。

 and recognize the importance of writing application codes in multiple files。



![](img/b80da62518b7772d1b21885f0f826658_2.png)

![](img/b80da62518b7772d1b21885f0f826658_3.png)

![](img/b80da62518b7772d1b21885f0f826658_4.png)

Imagine this。 a customer requests you to build an application to help their employees track their daily tasks。



![](img/b80da62518b7772d1b21885f0f826658_6.png)

Now， consider a scenario where a customer wants you to build a web app to manage hotel reservations from creation to customer checkout。



![](img/b80da62518b7772d1b21885f0f826658_8.png)

![](img/b80da62518b7772d1b21885f0f826658_9.png)

In either scenario， can you start building the application when the customer makes a request。

 Not really， you will need to perform certain activities like analyzing requirements。

 planning and coding before the application is ready for users。



![](img/b80da62518b7772d1b21885f0f826658_11.png)

Regardless of the application type， every application will go through different phases called the applicationpplication development Lifecycle。



![](img/b80da62518b7772d1b21885f0f826658_13.png)

You can divide the application development lifecycle into seven phases。



![](img/b80da62518b7772d1b21885f0f826658_15.png)

Requirement， gathering， analysis， design， code and test， user and system test。

 protection and maintenance。

![](img/b80da62518b7772d1b21885f0f826658_17.png)

Let's look at each of the application development phases in detail。



![](img/b80da62518b7772d1b21885f0f826658_19.png)

Requirement gathering is the first phase in the application development process In the requirement gathering phase。

 you will capture the requirements across all aspects of the application。

 including user requirements， business requirements and technical requirements。

 Let's consider the hotel reservation app For this app。

 a user requirements may be that users must be able to view the different rooms and amenities available。

😊。

![](img/b80da62518b7772d1b21885f0f826658_21.png)

![](img/b80da62518b7772d1b21885f0f826658_22.png)

![](img/b80da62518b7772d1b21885f0f826658_23.png)

Determining the right charge for different rooms and amenities may be a business requirement。



![](img/b80da62518b7772d1b21885f0f826658_25.png)

A technical requirement might be that the app must run on all browsers and mobile devices。



![](img/b80da62518b7772d1b21885f0f826658_27.png)

The goal should be to capture as many requirements as possible。

 even if it seems redundant or trivial。You must also identify any constraints of design and viability of the business model。

 For example， for the hotel reservation app， one constraint is that the server needs to keep the status of room availability updated at all times。

 which has an associated cost， Therefore， to keep the business viable。

 a minor convenience fee is added to the final payment。



![](img/b80da62518b7772d1b21885f0f826658_29.png)

After gathering the requirements and constraints， you must analyze each to create a possible solution for the application's design。



![](img/b80da62518b7772d1b21885f0f826658_31.png)

During analysis and design， there might be multiple rounds of verification and revision to create a model solution that meets all the specified requirements。



![](img/b80da62518b7772d1b21885f0f826658_33.png)

![](img/b80da62518b7772d1b21885f0f826658_34.png)

Across the analysis and design phases of application development。

 you must maintain proper documentation with records of all updates in the design。



![](img/b80da62518b7772d1b21885f0f826658_36.png)

The documentation should be clear and concise as used during the code and test phase。



![](img/b80da62518b7772d1b21885f0f826658_38.png)

The final proposed design and the specified requirements are passed on to the code and test phase。



![](img/b80da62518b7772d1b21885f0f826658_40.png)

During the code and test phase， the team uses the programming requirements specified in the design documentation to code。

 test， revise， and test the application programs until the code meets all documented requirements。



![](img/b80da62518b7772d1b21885f0f826658_42.png)

![](img/b80da62518b7772d1b21885f0f826658_43.png)

![](img/b80da62518b7772d1b21885f0f826658_44.png)

Let's review the testing phase。 The tests you conduct for the unit code is called unit testing。



![](img/b80da62518b7772d1b21885f0f826658_46.png)

Conduct the unit testing at the programming level to ensure you meet all required specifications。



![](img/b80da62518b7772d1b21885f0f826658_48.png)

After the unit testing， you can generate an acceptable application version。

 the new version of the application is then run through a series of user and system level tests。



![](img/b80da62518b7772d1b21885f0f826658_50.png)

![](img/b80da62518b7772d1b21885f0f826658_51.png)

The user tests verify the functionality from a user's point of view。In addition。

 you will need to execute several system level tests， including integration and performance testing。



![](img/b80da62518b7772d1b21885f0f826658_53.png)

Integration tests verified that all involved programs continue functioning as expected after integration。

Integration testing also verifies that the application functions within a larger framework。



![](img/b80da62518b7772d1b21885f0f826658_55.png)

Performance testing helps evaluate the speed， scalability and stability of the application based on varying workloads。

😊。

![](img/b80da62518b7772d1b21885f0f826658_57.png)

After testing， you can generate a new application version and send it to production。



![](img/b80da62518b7772d1b21885f0f826658_59.png)

Once in production， end users can access and use it。

 You must ensure that the application functions accurately and is available to users。



![](img/b80da62518b7772d1b21885f0f826658_61.png)

When the application is in the production phase， it must remain in a steady state。In a steady state。

 you should not make any changes to the application。 However， this is not always possible。

 For example， you might need to make changes to the application in case of an error。



![](img/b80da62518b7772d1b21885f0f826658_63.png)

These changes are tightly controlled and heavily tested before being implemented into production。



![](img/b80da62518b7772d1b21885f0f826658_65.png)

The last phase in the application development life cycle is maintenance。



![](img/b80da62518b7772d1b21885f0f826658_67.png)

The application might need an upgrade， or you might need to add new features。 In this case。

 the new features must go through all previous phases before being integrated into the application version deployed in production。



![](img/b80da62518b7772d1b21885f0f826658_69.png)

![](img/b80da62518b7772d1b21885f0f826658_70.png)

Let's briefly review why maintaining multiple files for coding different functionalities is a best practice。



![](img/b80da62518b7772d1b21885f0f826658_72.png)

Every app usually has multiple functionalities， and the requirements for each functionality might vary。



![](img/b80da62518b7772d1b21885f0f826658_74.png)

The best practice is to code each functionality in separate files。



![](img/b80da62518b7772d1b21885f0f826658_76.png)

You can then create a central program， which runs the application and calls the individual files to perform specific functions。



![](img/b80da62518b7772d1b21885f0f826658_78.png)

This approach to organizing code makes code maintenance efficient and easy。



![](img/b80da62518b7772d1b21885f0f826658_80.png)

Having multiple files also helps when you need to add new functionality to an existing application。

When you write the code for new functionality in a separate file。

 only the file will go through the entire design and verification process before being integrated into the running application。

In this video， you learn that the application development lifecycl has seven phases。

 including requirement gathering where you collect user。

 business and technical requirements for the app。

![](img/b80da62518b7772d1b21885f0f826658_82.png)

![](img/b80da62518b7772d1b21885f0f826658_83.png)

Analysis where you analyze the requirements， design where you design the complete solution。

 code and test where you build and test the different components of the app。



![](img/b80da62518b7772d1b21885f0f826658_85.png)

User and System Test， where users test the app for usability。

 and you perform system integration testing and performance testing。Production。

 where the application is available to all end users。Maintenance。

 where you upgrade or fix any user or system issues。For efficient coding。

 always use essential program to call the individual files and functions for performing different actions。



![](img/b80da62518b7772d1b21885f0f826658_87.png)