# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p94 10_01_03_单体架构与微服务对比.zh_en -BV1tz421i7Ev_p94-

![](img/c8b645012ad3223173ce198e4243df7d_0.png)

What is the difference between a microservice and a monolithic application well in the old days you would build something that had every piece in one application and this is called a monolithic application。

And it would have the authentication right so how to sign into an account。

 it would have the data so you know maybe connecting to a relational database potentially with an object relational mapper that was a very common way to do things with web frameworks and then you would have the logic and the logic would serve out a request that maybe gave a customer a record for a database product all these aspects of the application were kept in this particular monolithic codeb and it could be let's say maybe 20。

000 lines of code could be inside of this monolithic application and if there's a problem with the authentication system。

 for example。You would have to look at the entire application to debug it and so this really created many problems in maintainability and complexity。

 And so what the industry has come up with is this idea of a microservice and a micro serviceice what's powerful about it is that each component is its own separate entity so it's an independent service there's an authentication service that handles just that one thing it handles letting someone sign in there's a separate service。

 which is the service that deals with let's say the data so it goes through and it makes request that talk to a database pulls records out。

But it doesn't require the authentication service Next there's the logic right This could be you know maybe a backend that gives reports or you know some other piece of business logic or business intelligence or machine learning as well each of those would be separate services So that's really the key idea is that each process of the application is built as an independent component that runs as a service and that service can communicate using lightweight API operations and each service performs a single function and that service can support multiple application so really a microservice architecture provides a much quicker way to develop code develop automation and overall speed and so you can start fast。

 you can find mistakes and you can really recover fast So that's really the key difference between microservice and a monolithic and it works very well for machine learning。



![](img/c8b645012ad3223173ce198e4243df7d_2.png)