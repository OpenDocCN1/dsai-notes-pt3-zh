# IBM数据工程专业证书课程10：《NoSQL数据库导论》｜introduction-to-nosql-databases｜ - P7：6_acid vs base.zh_en - GPT中英字幕课程资源 - BV1UN41187Zz

![](img/8fe7ce88c823c13234b33c1db9b658eb_0.png)

![](img/8fe7ce88c823c13234b33c1db9b658eb_1.png)

Welcome to acid versus base operations。 After watching this video。

 you will be able to define what acid and base operations stand for。

 identifydent the use cases for acid and base model systems and describe the difference between acid and base。

 One of the biggest and most striking differences between relational database management systems and no SQL databases is their data consistency models。

 The two most common consistency models that are known and in use nowadays are acid and base relational databases use the asset model and no SQL databases use the base model。

 Although acid and base models are often seen as enemies or one versus the other。

 The truth is that both come with their advantages and disadvantages。

 So let's take a closer look at what both terms mean。😊。



![](img/8fe7ce88c823c13234b33c1db9b658eb_3.png)

![](img/8fe7ce88c823c13234b33c1db9b658eb_4.png)

![](img/8fe7ce88c823c13234b33c1db9b658eb_5.png)

![](img/8fe7ce88c823c13234b33c1db9b658eb_6.png)

![](img/8fe7ce88c823c13234b33c1db9b658eb_7.png)

![](img/8fe7ce88c823c13234b33c1db9b658eb_8.png)

![](img/8fe7ce88c823c13234b33c1db9b658eb_9.png)

![](img/8fe7ce88c823c13234b33c1db9b658eb_10.png)

![](img/8fe7ce88c823c13234b33c1db9b658eb_11.png)

The As acronym stands for Atomic， All operations in a transaction succeed。

 or every operation is rolled back consistent on the completion of a transaction。

 the structural integrity of the data in the database is not compromised。



![](img/8fe7ce88c823c13234b33c1db9b658eb_13.png)

![](img/8fe7ce88c823c13234b33c1db9b658eb_14.png)

![](img/8fe7ce88c823c13234b33c1db9b658eb_15.png)

![](img/8fe7ce88c823c13234b33c1db9b658eb_16.png)

Isolated transactions cannot compromise the integrity of other transactions by interacting with them while they are still in progress and durable。

 The data related to the completed transaction will persist。

 even in the case of network or power outages。 If a transaction fails。

 it will not impact the already changed data。

![](img/8fe7ce88c823c13234b33c1db9b658eb_18.png)

![](img/8fe7ce88c823c13234b33c1db9b658eb_19.png)

![](img/8fe7ce88c823c13234b33c1db9b658eb_20.png)

![](img/8fe7ce88c823c13234b33c1db9b658eb_21.png)

Many developers are familiar with acid transactions from working with relational databases， as such。

 the As consistency model has been the norm for some time。



![](img/8fe7ce88c823c13234b33c1db9b658eb_23.png)

The asset consistency model ensures that a performed transaction is always consistent。

 This makes it a good fit for businesses that deal with online transaction processing。

 such as financial institutions or data warehousing types of applications。



![](img/8fe7ce88c823c13234b33c1db9b658eb_25.png)

![](img/8fe7ce88c823c13234b33c1db9b658eb_26.png)

These organizations need database systems that can handle many small。

 simultaneous transactions like a relational database can。

 an acid system provides a consistent model you can count on for the structural integrity of your data。

 While there are many possible use cases for acid databases。 One stands out。

 Financial institutions will almost exclusively use acid databases for their money transfers。

 Since these operations depend on the atomic nature of acid transactions。



![](img/8fe7ce88c823c13234b33c1db9b658eb_28.png)

![](img/8fe7ce88c823c13234b33c1db9b658eb_29.png)

An interrupted transaction that is not immediately removed from the database can cause a lot of issues。

 Money could be debitted from one account and due to an error never credited to the other or not credited at all。



![](img/8fe7ce88c823c13234b33c1db9b658eb_31.png)

![](img/8fe7ce88c823c13234b33c1db9b658eb_32.png)

![](img/8fe7ce88c823c13234b33c1db9b658eb_33.png)

The base acronym stands for basically available， rather than enforcing immediate consistency。

 base modeled no SQL databases will ensure availability of data by spreading and replicating it across the notess of the database cluster。

 So state due to the lack of immediate consistency， data values may change over time。



![](img/8fe7ce88c823c13234b33c1db9b658eb_35.png)

![](img/8fe7ce88c823c13234b33c1db9b658eb_36.png)

![](img/8fe7ce88c823c13234b33c1db9b658eb_37.png)

![](img/8fe7ce88c823c13234b33c1db9b658eb_38.png)

In the base model data， stores don't have to be right consistent。

 nor do different replicas have to be mutually consistent all the time。



![](img/8fe7ce88c823c13234b33c1db9b658eb_40.png)

Eventually consistent， the fact that the base model does not enforce immediate consistency does not mean that it never achieves it。

 However， until it does， data reads might be inconsistent。



![](img/8fe7ce88c823c13234b33c1db9b658eb_42.png)

![](img/8fe7ce88c823c13234b33c1db9b658eb_43.png)

![](img/8fe7ce88c823c13234b33c1db9b658eb_44.png)

In the No SQL database world， asset transactions are less fashionable because some databases have loosened the requirements for immediate consistency。

 data freshness and accuracy they do this to gain other benefits such as availability。

 scale and resilience。

![](img/8fe7ce88c823c13234b33c1db9b658eb_46.png)

![](img/8fe7ce88c823c13234b33c1db9b658eb_47.png)

![](img/8fe7ce88c823c13234b33c1db9b658eb_48.png)

The base consistency model is used by marketing and customer service companies that deal with sentiment analysis and social network research。

 social media applications that contain huge amounts of data and need to be available at all times。

 and worldwide available online services like Netflix， Spotify and Uber。

A base data store values availability over consistency。

 but it does not offer guaranteed consistency of replicated data at right time。

 No SQL databases used the base consistency model。Essentially。

 the base consistency model provides high availability。

Base data stores can be and are used in a lot of specific use cases。

 The fame of base databases increased because well known worldwide online services such as Netflix。

 Apple， Spotify and Uber use them in applications like user profile data storage。



![](img/8fe7ce88c823c13234b33c1db9b658eb_50.png)

![](img/8fe7ce88c823c13234b33c1db9b658eb_51.png)

A common characteristic of these services is that they need to be accessible at all times。

 no matter which part of the globe you are in。 So if a part of their database cluster becomes unavailable。

 the system needs to be able to serve the user requests seamlessly In this video。

 you have learned that acid and base are the consistency models used in relational and no SQL databases。



![](img/8fe7ce88c823c13234b33c1db9b658eb_53.png)

![](img/8fe7ce88c823c13234b33c1db9b658eb_54.png)

Ad stands for atomity， consistency， I， durableable B stands for basically available， soft state。

 eventually consistent， while the asset model is focused on data consistency。

 The base model is focused on data availability。 Both consistency models have their applicability。

 usage should be selected based on a case by case analysis。



![](img/8fe7ce88c823c13234b33c1db9b658eb_56.png)