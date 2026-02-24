# 密歇根大学《创造性编程（创意、面向对象、debug、QA）｜Creative Coding： Hands-On Python》中英字幕 p186 53_键类型与最佳实践.zh_en -BV1ef421S7Bc_p186-

![](img/884932b37c26c2e52579df322103311d_0.png)

![](img/884932b37c26c2e52579df322103311d_1.png)

So there's three types of keys that you can use in databases。

 and one we've been using is a primary key。 So this is automatically increment。

 typically in a jerk key that's assigned to each entity。 And but there's a logical key。

 what the outside world uses often for look up， for example， for an album you might look up a title。

 But that isn't necessarily a great thing to use as a。Primary key。

 because even though people might look up a title， there could be two albums with the same title。

 So you might have to differentiateate by year。 And then a foreign key is another integer key。

 that's the primary key in another table。 So in an album table。

 the artist I might be would be a foreign key because it would be the primary key in the artist table and then best practices for using keys is don't use logical keys as your primary keys instead create a separate autoincrement key because logical keys can and do change。

 for example， a user and somebody's username might change over time。

 albeit often slowly and relationships that are batmatched based on matching string fields is less than using integers。

 So typically will create primary keys that are integers and they'll be different from the logical keys。

 That's best practice。

![](img/884932b37c26c2e52579df322103311d_3.png)

![](img/884932b37c26c2e52579df322103311d_4.png)

![](img/884932b37c26c2e52579df322103311d_5.png)