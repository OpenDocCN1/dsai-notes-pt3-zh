# 002：IBM《生成式人工智能工程｜Falsk、生成式AI应用、数据分析、机器学习、Keras、架构和数据、NLP基础、transformer、微调、高级微调、RAG》 p02 1_应用程序开发生命周期.zh_en -BV1NAq6Y9E7z_p2-

Welcome to Application Development Lifecycle After watching this video。

 you will be able to list the steps in the application development lifecycle。

 describe the different phases of the application development lifecycle。

 and recognize the importance of writing application codes in multiple files。



![](img/1eef05a73c45838eb2f1378110d236b2_1.png)

![](img/1eef05a73c45838eb2f1378110d236b2_2.png)

Imagine this。 A customer requests you to build an application to help their employees track their daily tasks。

 Now， consider a scenario where a customer wants you to build a web app to manage hotel reservations from creation to customer check out。

😊，In either scenario， can you start building the application when the customer makes a request。

 Not really， you will need to perform certain activities like analyzing requirements。

 planning and coding before the application is ready for users。Regardless of the application type。

 every application will go through different phases called the applicationpplication development Lifecycle。

You can divide the application development lifecycle into seven phases。Requirement gathering。

 analysis， design， code and test， user and system test， protection and maintenance。

Let's look at each of the application development phases in detail。

Requirement gathering is the first phase in the application development process In the requirement gathering phase。

 you will capture the requirements across all aspects of the application。

 including user requirements， business requirements and technical requirements。

Let's consider the hotel reservation app for this app。

 A user requirement may be that users must be able to view the different rooms and amenities available。

😊，Determining the right charge for different rooms and amenities may be a business requirement。

A technical requirement might be that the app must run on all browsers and mobile devices。

The goal should be to capture as many requirements as possible。

 even if it seems redundant or trivial。You must also identify any constraints of design and viability of the business model。

 For example， for the hotel reservation app， one constraint is that the server needs to keep the status of room availability updated at all times。

 which has an associated cost， Therefore， to keep the business viable。

 a minor convenience fee is added to the final payment。

After gathering the requirements and constraints， you must analyze each to create a possible solution for the application's design。

During analysis and design， there might be multiple rounds of verification and revision to create a model solution that meets all the specified requirements。

Across the analysis and design phases of application development。

 you must maintain proper documentation with records of all updates in the design。

The documentation should be clear and concise as used during the code and test phase。

The final proposed design and the specified requirements are passed on to the code and test phase。

During the code and test phase， the team uses the programming requirements specified in the design documentation to code。

 test， revise， and test the application programs until the code meets all documented requirements。

Let's review the testing phase。 The tests you conduct for the unit code is called unit testing。

Conduct the unit testing at the programming level to ensure you meet all required specifications。

After the unit testing， you can generate an acceptable application version。

 The new version of the application is then run through a series of user and system level tests。

The user tests verify the functionality from a user's point of view。In addition。

 you will need to execute several system level tests， including integration and performance testing。

Integration tests verified that all involved programs continue functioning as expected after integration。

Integration testing also verifies that the application functions within a larger framework。

Performance testing helps evaluate the speed， scalability and stability of the application based on varying workloads。

😊，After testing， you can generate a new application version and send it to production。

Once in production， end users can access and use it。

 You must ensure that the application functions accurately and is available to users。

When the application is in the production phase， it must remain in a steady state。In a steady state。

 you should not make any changes to the application。 However， this is not always possible。

 For example， you might need to make changes to the application in case of an error。

These changes are tightly controlled and heavily tested before being implemented into production。

The last phase in the application development life cycle， is maintenance。

The application might need an upgrade， or you might need to add new features。 In this case。

 the new features must go through all previous phases before being integrated into the application version deployed in production。

 Let's briefly review why maintaining multiple files for coding different functionalities is a best practice。

Every app usually has multiple functionalities， and the requirements for each functionality might vary。

The best practice is to code each functionality in separate files。

You can then create a central program which runs the application and calls the individual files to perform specific functions。

This approach to organizing code makes code maintenance efficient and easy。

Having multiple files also helps when you need to add new functionality to an existing application。

When you write the code for new functionality in a separate file。

 only the file will go through the entire design and verification process before being integrated into the running application。

In this video， you learn that the application development lifecycl has seven phases。

 including requirement gathering， where you collect user。

 business and technical requirements for the app。😊，Analysis where you analyze the requirements。

 design， where you design the complete solution， code and test where you build and test the different components of the app。

User and System Test where users test the app for usability。

 and you perform system integration testing and performance testing。Production。

 where the application is available to all end users。Maintenance。

 where you upgrade or fix any user or system issues。For efficient coding。

 always use a central program to call the individual files and functions for performing different actions。



![](img/1eef05a73c45838eb2f1378110d236b2_4.png)

![](img/1eef05a73c45838eb2f1378110d236b2_5.png)