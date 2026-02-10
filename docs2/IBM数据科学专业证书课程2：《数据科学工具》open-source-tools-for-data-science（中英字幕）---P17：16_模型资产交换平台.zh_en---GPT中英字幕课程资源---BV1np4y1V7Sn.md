# IBM数据科学专业证书课程2：《数据科学工具》open-source-tools-for-data-science（中英字幕） - P17：16_模型资产交换平台.zh_en - GPT中英字幕课程资源 - BV1np4y1V7Sn

In this video we will introduce you to the Model As Exchange on IBM developer。

 a free open source resource for deep learning models Throughout the video we will refer to the model asset exchange as max in the previous video we briefly outline the high levelvel tasks you need to complete to train a model from scratch due to the amount of data labor time and resources required to complete the tasks time to value can be quite long。



![](img/a499bc5565a61718bf8d602eb23256bf_1.png)

To reduce time to value， consider taking advantage of pre trained models for certain types of problems。

These pre traineded models can be ready to use right away， or they may take less time to train。



![](img/a499bc5565a61718bf8d602eb23256bf_3.png)

The Model asset Exchange is a free open source repository for ready to use and customizable deep learning microservices。



![](img/a499bc5565a61718bf8d602eb23256bf_5.png)

These microservices are configured to use pretrained or custom trainable state of the art deep learning models to solve custom business problems。



![](img/a499bc5565a61718bf8d602eb23256bf_7.png)

![](img/a499bc5565a61718bf8d602eb23256bf_8.png)

These models have been reviewed， tested and can be quickly deployed in local and cloud environments。

 All models in Macs are available under permissive open source licenses。

 making it easier to use them for personal and commercial purposes and reducing the risk of legal liabilities。



![](img/a499bc5565a61718bf8d602eb23256bf_10.png)

![](img/a499bc5565a61718bf8d602eb23256bf_11.png)

![](img/a499bc5565a61718bf8d602eb23256bf_12.png)

![](img/a499bc5565a61718bf8d602eb23256bf_13.png)

On Max， you can find models for a variety of domains， including image， audio， video。

 and natural language analysis。

![](img/a499bc5565a61718bf8d602eb23256bf_15.png)

This list includes a small selection in the lab for this module。

 you'll have a chance to explore those models。 Let's take a look at the components of a typical model serving microservice。

 each microservice includes the following components， a pretrained deep learning model。

 code that prepro the input before it is analyzed by the model and code that postprosses the model output。

 a standardized public API that makes the services functionality available to applications。



![](img/a499bc5565a61718bf8d602eb23256bf_17.png)

![](img/a499bc5565a61718bf8d602eb23256bf_18.png)

![](img/a499bc5565a61718bf8d602eb23256bf_19.png)

The Mac model serving microservices are built and distributed as open source Docker images。



![](img/a499bc5565a61718bf8d602eb23256bf_21.png)

Docker is a container platform that makes it easy to build applications and deploy them in a development。

 test or production environment。 The Docker image source is published on Gitthub and can be downloaded。

 customized as needed and used in personal or commercial environments。



![](img/a499bc5565a61718bf8d602eb23256bf_23.png)

![](img/a499bc5565a61718bf8d602eb23256bf_24.png)

![](img/a499bc5565a61718bf8d602eb23256bf_25.png)

![](img/a499bc5565a61718bf8d602eb23256bf_26.png)

You can deploy and run these images in a test or production environment using Kubernetes。

 an open source system for automating deployment， scaling。

 and management of containerized applications in private， hybrid or public clouds。



![](img/a499bc5565a61718bf8d602eb23256bf_28.png)

![](img/a499bc5565a61718bf8d602eb23256bf_29.png)

![](img/a499bc5565a61718bf8d602eb23256bf_30.png)

A popular enterprise grade Kubernetes platform is Red Hat Openshift， which is available on IBM Cloud。

 Google Cloud Plat， Amazon Web services and Microsoft Azure the model serving microservices expose a RE API that developers can use to incorporate deep learning into their applications and services because RE APIs can be consumed using any programming language you can easily integrate these services into your existing ecosystem。



![](img/a499bc5565a61718bf8d602eb23256bf_32.png)

![](img/a499bc5565a61718bf8d602eb23256bf_33.png)

![](img/a499bc5565a61718bf8d602eb23256bf_34.png)

![](img/a499bc5565a61718bf8d602eb23256bf_35.png)

The API exposes a prediction endpoint and one or more metadata endpoints。



![](img/a499bc5565a61718bf8d602eb23256bf_37.png)

This example shows the endpoints for the object detection microservice。



![](img/a499bc5565a61718bf8d602eb23256bf_39.png)

The slash model/lash predictdict endpoint takes an image as input and returns as a response a list of objects that were detected in the image along with the bounding box coordinates that identify where the detected object is located。

Some prediction endpoints can also accept additional input parameters that impact the produced results。

 such as filters。

![](img/a499bc5565a61718bf8d602eb23256bf_41.png)

This microservice exposes two metadata endpoints， slash model slash labels。

 and slash model slash metadata。These endpoints provide information such as the objects that can be detected and the deep learning model used to derive the answer given the input。

In the lab portion of this module， you will have a chance to explore and test these endpoints using a web browser。

Each endpoint accepts application friendly inputs， such as an image in JPEG。

 Ping or GIF format instead of a model specific data structure。

Each endpoint also generates application friendly outputs such as standardized JSON。

 which is a lightweight data interchange format。Let's take a closer look at what happens when an application invokes the prediction endpoint。

 In this example， a user has selected an image in a web application。

 The prediction endpoint is invoked and the image is uploaded。



![](img/a499bc5565a61718bf8d602eb23256bf_43.png)

![](img/a499bc5565a61718bf8d602eb23256bf_44.png)

![](img/a499bc5565a61718bf8d602eb23256bf_45.png)

The microservice prepares the input image for processing。

 runs the deep learning model that identifies objects in the image。

 generates a response using the prediction results， and returns the result to the application。



![](img/a499bc5565a61718bf8d602eb23256bf_47.png)

![](img/a499bc5565a61718bf8d602eb23256bf_48.png)

The application renders the results by drawing bounding boxes and labels。



![](img/a499bc5565a61718bf8d602eb23256bf_50.png)

In this video， we've introduced the Model As Exchange。

 a free and open source repository for microservices that make deep learning functionality available to applications and services in local and cloud environments。



![](img/a499bc5565a61718bf8d602eb23256bf_52.png)

![](img/a499bc5565a61718bf8d602eb23256bf_53.png)

![](img/a499bc5565a61718bf8d602eb23256bf_54.png)

In the lab， you will have a chance to try a model serving microservice， explore its API。

 and learn more about how you can leverage it from a web application and an Internet of Things application。



![](img/a499bc5565a61718bf8d602eb23256bf_56.png)

![](img/a499bc5565a61718bf8d602eb23256bf_57.png)