# 吴恩达《机器学习工程师的生产实践（MLOps）Machine Learning Engineering for Production》中英字幕 - P68：27_模式开发.zh_en - GPT中英字幕课程资源 - BV1pi4y167g5

![](img/2bba3af9c63f9dea9ca92da997e37b00_0.png)

Now， let's discuss schema development In this lesson on evolving data。

 you'll learn about developing enterprise schema environments。

And how to iteratively create and maintain enterprise data schemas。

 you'll be using schemas quite extensively， so let's quickly review what a schema is and how helpful they are in the context of production ML。

Schemes are relational objects， summarizing the features in a given data set or project。

They include the feature name， the feature variable type， so for example， an integer float。

 string or categorical variable。Whether or not the feature is required the valency of the feature。

Which applies to features with multiple values like lists or array features and expresses the minimum and maximum number of values。

Information about the range and categories。And feature default values。

Schemas are important as your data and feature set evolves over time。From your experience。

 you know that data keeps changing， and this change often results in change distributions。

Let's focus on how to observe data that is changed as it keeps evolving。

 Ching data often results in a new schema being generated。 However， there are some special use cases。

 Imagine that even before you assess the data set， you have an idea or information about the expected range of values for your features。

 and the initial data set that you' have received is covering only a small range of those values。

In that case， it makes sense to adjust or curate your schema to reflect the expected range of values for your features。

A similar situation may exist for the expected values of categorical features。Besides that。

 your schema can help you find problems or anomalies in your dataset set。

 such as missing required values or values of the wrong type。

All these factors have to be considered when you're designing the schema of your ML pipeline。

As data keeps evolving， there are some requirements which must be met in production and deployments。

 Let's consider some important ones。 The first factor is reliability。

 The M O platform of your choice should be resilient to disruptions from inconsistent data。

 There is no guarantee that youll receive clean and consistent data every time。 In fact。

 I can almost guarantee you that you won't。 Your system needs to be designed to handle that efficiently。

Also， your software might generate unexpected runtime errors。

 and your pipeline needs to gracefully handle that also。

Problems with misconfiguration should be detected and handled gracefully。 And above all。

 the orchestration of execution among different components in the pipeline should happen smoothly and efficiently。

Another factor to consider in your M pipeline platform is scalability during data evolution during training。

 your pipeline may need to handle a large amount of training data well。

 including keeping expensive accelerators like GPUus and TUus busy when you serve your model。

 especially in online scenarios such as running on a server。

You'll almost always have varying levels of request traffic。

 Your infrastructure needs to scale up and down to meet those latency requirements while minimizing the cost。

If your system isn't designed to handle data evolution。It will quickly run into problems。

These include the introduction of anomalies in your data set。

 will your system detect those anomalies？Your system and your development process should be designed to treat data errors as first class citizens in the same way that bugs in your code are treated。

 and in some cases， those anomalies are alerting you that you need to update the schema and accommodate valid changes in your data。

The evolution of your schemas can be a useful tool to understand and track the evolution of your data。

 also schemas can be used as key inputs into automated processes that work with your data like automatic feature engineering。



![](img/2bba3af9c63f9dea9ca92da997e37b00_2.png)