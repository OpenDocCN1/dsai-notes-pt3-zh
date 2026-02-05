# 吴恩达《机器学习工程师的生产实践（MLOps）Machine Learning Engineering for Production》中英字幕 - P130：1_模型服务简介.zh_en - GPT中英字幕课程资源 - BV1pi4y167g5

![](img/d8d6ab6c7878cd7529d1e587fd08289d_0.png)

Hi， everybody， and welcome to this course， where we'll discuss model serving patterns and infrastructures。

 We'll also look at management and delivery， as well as monitoring。😊，This week。

 I'll give you an introduction to Model serving where you'll explore methods for deploying models before getting hands on and trying it for yourself。

😊，And don't worry， you're not going to need a serving infrastructure of your own。

 you're going to be able to do all of the exercises using collLab， so let's get started。😡，First。

 we'll discuss model performance and resource requirements。

 starting with a discussion of batch inference。So what exactly do we mean by serving a model Well that's a great question。

😊，Training a good machine learning model is only the first part。

 you do need to make a model available to your end users。

 and you do this by either providing access to the model on your server。

 which will explore this week。Serving also includes the facility to deploy a model file to an application。

 and this is a scenario that's usually found with mobile ML。😊。

When serving an ML model in a production environment， you should consider three key components。

 there's the model itself， there's an interpreter for the execution and there's input data。

These components are used by an inference process， which is aimed at getting the data to be ingested by a model in order to compute predictions。

A high level look at ML workflows boils down to something like this where you take into consideration。

 model training and prediction while understanding the types of inference or prediction that you want to do with your model。

😊，Model training is performed either with offline， also known as batch or static learning。

 where the model is trained on a set of already collected data。

After deploying to the production environment， the ML model remains constant until it's retrained because the model will see a lot of real live data。

 and then it becomes stale quite quickly。 This phenomenon is called model decay。

 and it's something that should be carefully monitored。😊，There's also online learning。

 also known sometimes as dynamic learning， and here the model is regularly being retrained as new data arrives。

 for example， as data streams。😊，This is usually the case for ML systems that use time series data。

 such as sensors or stock or anything like that， and the idea is to accommodate the temporal effects in the ML model。

😊，Then when using your model for prediction， there's also two main types with batch predictions。

 the deployed ML model makes a set of predictions based on historical input data。😊。

This is often sufficient for data that's not time dependent or when it's not critical to obtain real time predictions as output。

Or with real time predictions， also known as on demand predictions。

 these predictions are generated in real time using the input data that's available at the time of the request。

😊，When we talk about optimizing online inference， most of the materials surrounding it will first give us an overview about the important metrics to optimize。

 namely latency， throughput and cost。Latency is the delay between a user's action and the response of the application to the user's action。

😊，In the case of ML inference， it's the whole process of online inference。

 starting from sending data to the server， performing inference using the model。

 and then returning the response。Most applications are user facing。

 so minimal latency is a key requirement to maintaining your customer satisfaction。😊，So for example。

 your users might complain that app that suggests hotels is too slow to refresh the search results based on a user's input。

😊，Throughhput is the number of successful requests served in a unit of time。

 An example here could be if you want your models to process large amounts of data， for example。

 video from security cameras at a very high fidelity in order to assure that any security events are spotted quickly。

And we should always try to remember and factor in the cost associated with each inference。

Your serving infrastructure will always have associated costs。

 so you should consider the costs for things like CPUus。

 harder accelerators like GPUus and caches for storing input features for easy retrieval with minimum latency。

Many customer facing applications have the aim to minimize this latency while also maximizing throughput。

😊，An example of this could be an airline recommendations website and this gives you recommendations about the best flights that are available to you based on your input Smarter systems could be running ML models to predict the best options for their users。

😊，At some points in time such as holidays， this application could face a very high load of users。

 so you have the burden of providing low latency， giving your users the results quickly。

 with high throughput， having a model serving infrastructure that can handle that high load。

We can scale the infrastructure used to meet these thresholds of response time and throughputs。

 but this can increase the cost proportionally。So the cost of running your ML model in production can increase sharply as your infrastructure is scaled to handle latency and throughput。

And this leads you to play a balancing game between costs and customer satisfaction。😊。

There's no perfect answer， and there are always trade offs， but fortunately。

 there are tactics you can use to try to minimize any impact on your customer while you attempt to control costs。

😊，These may include reducing costs by sharing assets like GPUs。

 using multiple models to increase throughput， and perhaps even exploring optimizing your models。



![](img/d8d6ab6c7878cd7529d1e587fd08289d_2.png)

Okay，Now that you've seen the basic concepts that you need to understand for hosting models on a server and understanding the decisions that you may need to make。

 we'll next look at some of the tactics that will help you in these decisions。

 including maybe even not using a server and exploring the deployment of a model directly into a user's hands on their mobile or edge devices。

😊。