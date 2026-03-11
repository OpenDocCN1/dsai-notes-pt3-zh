# 【EDUCBA】应用生成式人工智能集成与部署策略-｜-Apply-Generative-AI-Integration-and-Deployment-Strate-p04-01_02_02_评估部署方法与供应商--BV1dcF2zMENZ_p4-

Evaluating deployment methods and vendors。Behind the scenes of every AI powered application lies a complex web of infrastructure and processes。

 This is the deployment landscape， from training models to serving predictions。

 the journey from research to real world impact is fraught with challenges and opportunities。

 Let's uncover the intricacies that make AI models truly work AWS SageMaker AWS SageMake is a fully managed service provided by Amazon Web services that facilitates the process of building。

 training and deploying machine learning ML models at scale。

AWS SageMaker provides a comprehensive environment for data scientists and developers to manage the entire life cycle of machine learning projects。



![](img/3a02e161ef6d50d36f7da62229011baf_1.png)

Its functionalities can be categorized into several key areas， data preparation。

 tools for data labeling， cleaning and transformation。

 including SageMaker data wrangler for easy data preparation from various sources。

Model training includes pre-built algorithms built in Jupiter notebooks for exploratory data analysis。

 EDA， and support for popular ML frameworks like TensorFlow， Pytorrch and PsyitLn。

 Model hosting and deployment offers SageMaker endpoints for realtime inference and batch Trans for batch inference。



![](img/3a02e161ef6d50d36f7da62229011baf_3.png)

![](img/3a02e161ef6d50d36f7da62229011baf_4.png)

Automatic model tuning provides hyperparameter tuning to optimize model performance with minimal manual intervention。

 built in Jupyter notebooks， enables data scientists to interactively develop and refine their models。



![](img/3a02e161ef6d50d36f7da62229011baf_6.png)

AWS SageMaker is designed to improve productivity and scalability while also streamlining the operational aspects of machine learning in cloud environments。

 setting up SageMake environment， Se up a SageMake environment involves several steps。

 Here is a step by step guide step1 AWS account， createate an AWS account。

 registerister for an AWS account if you don't have one。



![](img/3a02e161ef6d50d36f7da62229011baf_8.png)

Step2， access SageMaker console， open the AWS management console。

 navigategate to the SageMaker service， step3， create a notebook instance。



![](img/3a02e161ef6d50d36f7da62229011baf_10.png)

In the SageMake console， select Note instances and create a new instance。

Choose an instance type based on the expected resource usage， CPU， GPU I am Ro。

Create or select an IAM role with appropriate permissions that allows SageMaker to access your S3 buckets and other AWS services。

 Step4， configure networking and security VPC configuration， if necessary。

 configure the networking settings to fit your security and availability needs。Step 5。

 access Note instance， launch the instance and utilize Jupiter notebooks to write and execute code。

Connect to S3 for data storage and retrieval， step 6， install additional libraries。

 if using custom libraries， ensure they're installed in the notebook environment。

Deploying Geni models on SageMaker After training a generative AI model， the next step is deployment。

Here's how step one， train your model， use the SageMaker integrated environments to train your model。



![](img/3a02e161ef6d50d36f7da62229011baf_12.png)

![](img/3a02e161ef6d50d36f7da62229011baf_13.png)

You can use built in algorithms or your custom code step 2， create a model Once the model is trained。

 you need to create a model in SageMaker， specify the location of the model artifact， for example。

 in S3 and the inference image， for example， a Docker container。



![](img/3a02e161ef6d50d36f7da62229011baf_15.png)

![](img/3a02e161ef6d50d36f7da62229011baf_16.png)

Step 3， create an end point configuration， define the model's end point configuration。

 specifying the instance type and number of instances needed for scaling。



![](img/3a02e161ef6d50d36f7da62229011baf_18.png)

Step 4， deploy the model。Real time inference， use thee。

 create underscore Endpoint API or the SageMaker console to deploy the model to a real time inference endpoint。

 allowing you to generate predictions in real time。Is batch transform jobs for batchch inference。

 use SageMaker batchch transformform to call your model with a batch of input data？



![](img/3a02e161ef6d50d36f7da62229011baf_20.png)

Step 5， secure the endpoint， configure authentication and access permissions for the endpoint to control who can invoke it。



![](img/3a02e161ef6d50d36f7da62229011baf_22.png)

![](img/3a02e161ef6d50d36f7da62229011baf_23.png)

Monitoring and maintaining models on SageMaker Once deployed。

 monitoring and maintaining models is crucial for their success。Set up monitoring。

SageMaker provides built in CloudWatch metrics for endpoints， including latency。

 invocation count and errors。 consider using SageMaker tobugger to monitor model training and detect anomalies in model behavior log data。



![](img/3a02e161ef6d50d36f7da62229011baf_25.png)

Enable logging to capture requests and responses， which helps in understanding the performance of your model。



![](img/3a02e161ef6d50d36f7da62229011baf_27.png)

Model performance tracking monitor Model Dr and data drift through SageMaker model Monitor。

 which allows you to analyze the quality of your predictions over time。



![](img/3a02e161ef6d50d36f7da62229011baf_29.png)

![](img/3a02e161ef6d50d36f7da62229011baf_30.png)

The train models establish a feedback loop to collect feedback from users and continuously improve the model。



![](img/3a02e161ef6d50d36f7da62229011baf_32.png)

![](img/3a02e161ef6d50d36f7da62229011baf_33.png)

Autommate retraining using scheduled jobs or periodically assess the performance metrics to decide when to retrain。

