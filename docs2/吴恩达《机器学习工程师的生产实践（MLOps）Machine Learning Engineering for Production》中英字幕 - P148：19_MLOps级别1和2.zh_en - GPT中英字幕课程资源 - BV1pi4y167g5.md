# 吴恩达《机器学习工程师的生产实践（MLOps）Machine Learning Engineering for Production》中英字幕 - P148：19_MLOps级别1和2.zh_en - GPT中英字幕课程资源 - BV1pi4y167g5

![](img/795565b1aa7b428a58fbc1702582f304_0.png)

Let's take a look at ML Ops levels1 and2， which introduce pipeline automation。



![](img/795565b1aa7b428a58fbc1702582f304_2.png)

One of the key goals of level1 is to perform continuous training of the model by automating the training pipeline。

This lets you achieve continuous delivery of trained models to your model prediction service。

To automate the process of using new data to retrain models in production。

 you need to introduce automated data and model validation steps to the pipeline。

 as well as pipeline triggers and metadata management。

There is a need to have repeatable training in your ML workflows。

 so let's look at some of the characteristics of pipeline automation。

Notice here that since the steps of the experimentation are orchestrated。

 the transition between steps is automated。That enables you to rapidly iterate on your experiments and makes it easier to move the whole pipeline to production。

😊，Now， let's expand this out quite a bit to include the different environments， dev， test， staging。

 pre production and production。Note that the architecture shown here is typical。

 but different teams will implement this differently depending on their needs and infrastructure choices。

In this architecture， models are automatically retrained using fresh data based on live pipeline triggers。

 which I will discuss soon。The pipeline implementation that is used in the development or experimentation environment is also used in the pre production and production environment。

 which is a key aspect of Mlop's practice for unifying the Devop's effort。To construct ML pipelines。

 components need to be reusable， composable， and potentially shareable across pipelines。Therefore。

 while exploratory data analysis code can still live in notebooks。

 the source code for components must be modularized。In addition。

 components should ideally be containerized。 You do this in order to decouple the execution environment from the custom code run time。

It's also done to make code reproducible between development and production environments。

This essentially isolates each component in the pipeline。

 making them their own version of the runtime environment and have different languages and libraries。

Note that if the exploratory data analysis is done using production components and a production style pipeline。

 it greatly simplifies the transition of that code to production。

An ML pipeline in production continuously delivers new models that are trained on new data to prediction services。

Note that when I say continuously， I mean in an automated process in which new models might be delivered on a schedule or based on a trigger。

The model deployment step is automated， which delivers the trained and validated model for use by a prediction service for online or batch predictions。

 in level 0， you simply deployed the trained model to production。

But here you deploy a whole training pipeline， which automatically and recurrently runs to serve the train model as a prediction service。

When you deploy your pipeline to production， one or more of the triggers automatically executes the pipeline。

The pipeline expects new live data to produce a new model version that is trained on the new data。

So automated data validation and model validation steps。Are required in the production pipeline。

First， let's talk about why data validation is necessary before model training to decide whether you should retrain the model or stop the execution of the pipeline。

This decision is automatically made only if a data is deemed valid。For example。

 data schema ss are considered anomalies in the input data。

 which means that the downstream pipeline steps， including data processing and model training。

 receives data that doesn't comply with the expected schema。In this case。

 you should stop the pipeline and raise a notification so that the team can investigate。

 The team might release a fix or an update to the pipeline to handle these changes in the schema。

Schema Ss include receiving unexpected features， not receiving all the expected features or receiving features with unexpected values。

Then there are data value Skus， which are significant changes in the statistical properties of data。

 and you need to trigger a retraining of the model to capture these changes。

Model validation is another step which runs after you successfully train the model given the new data。

Here you evaluate and validate the model before it's promoted to production。

This offline model validation step may involve first producing evaluation metric values。

 using the trained model on a test data set to assess the model's predictive quality。

Then the next step would be to compare the evaluation metric values produced by your newly trained model to the current model。

 for example， the current production model or a baseline model or any other model which meets your business requirements。

Here， you make sure that the new model performs better than the current model before promoting it to production。

Also， you ensure the performance of the model is consistent on various segments or slices of the data。

 Your newly trained customer churn model might produce an overall better predictive accuracy compared to the previous model。

 but the accuracy values per customer region might have a large variance。Finally。

 infrastructure compatibility and consistency with the Predi Service API are some other factors that you need to consider before finally deploying your models。

In other words。Will the new model actually run on the current infrastructure。

In addition to offline model validation， a newly deployed model undergoes online model validation in either a canary deployment or an AB testing setup。

During the transition to serving prediction for the online traffic。

 you'll learn more about this in later sessions。An optional additional component for level 1 MLLOs is a feature store。

A feature store is a centralized repository where you standardize the definition。

 storage and access of features for training and serving。Ideally。

 a feature store will provide an API for both high throughput batch serving and low latency real time serving for the feature value。

And support both training and serving workloads。A feature store helps you in many ways。First of all。

 it lets you discover and reuse available feature sets instead of recreating the same or similar feature sets。

Avoiding having similar features that have different definitions by maintaining features and the related metadata。

Moreover， you can potentially serve up to date feature values from the feature store and avoid training serving Sw by using the feature store as a data source for experimentation。

 continuous training and online serving。😊，This approach makes sure that the features used for training are the same ones used during serving。

For example， when it comes to experimentation， data scientists can get an offline extract from the feature store to run their experiments。

For continuous training， the automated training pipeline can fetch a batch of the up to date feature values of the data。

For online prediction， the prediction service can fetch feature values such as customer demographic features。

 product features， and current session aggregation features。

Another key component is the metadata store， where information about each execution of the pipeline is recorded in order to help with data and artifact lineage。

 reproducibility and comparisons。It also helps you debug errors and anomalies。

Each time you execute the pipeline， the metadata store tracks information such as the pipeline and component versions。

 which were executed， the start and end time and date。

 and how long the pipeline took to complete each of the steps and the input and output artifacts from each step and more。

Basically， what this means is that you could rely on pointers to the artifacts produced by each step of the pipeline。

 like the location of the prepared data or the validation anomalies。

 computed statistics and so on to seamlessly resume execution in case of an interruption so。

Tracking these intermediate outputs helps you resume the pipeline from the most recent step。

 If the pipeline stopped due to a failed step without having to restart the pipeline as a whole。

The truth is that the current stage are at the current stage of the development of Amalov's best practices。

Level 2 is still somewhat speculative。This diagram presents one of the current architectures。

 which is focused on enabling rapid and reliable update of the pipelines in production。

This requires robust， automated CICD to enable your data scientists and MLL engineers to rapidly explore new ideas around feature engineering。

 model architecture and hyperparameters。They can implement these ideas and automatically build test。

And deploy new pipeline components to the target environment。

This MLO setup includes components like source code control， test and build services。

 deployment services， a model registry， a feature store， a metadata store。

 and a pipeline orchestrator。Since this is a lot to take in。

Let's look at the different stages of the machine learning continuous integration and cos delivery or CICD pipeline in a simplified and more digestible form。

To summarize， let's use this picture to understand the steps of the level 2 life cycle。First。

 you have experimentation and development。This is where you iteratively try out new algorithms and new modeling。

 and the experiment steps are orchestrated。The output of this stage is the source code of the M L pipeline steps that are then pushed to a source repository。

Next comes the CICD stage for the training of the pipeline itself。

Or for the trading pipeline itself rather。Here you build the source code and run various tests。

The outputs of this stage are pipeline entities like software packages。

Executables and artifacts to be deployed in a later stage。

The output of this stage is a deployed pipeline with a new implementation of the model。

 Then you train your models here。 the pipeline is automatically executed in production based on a schedule or in response to a trigger。

The output of this stage is a trained model。And that is pushed to the model registry。

Once the model has been trained， the goal of the pipeline is now to deploy the model using continuous delivery。

 You do this by serving the train model as a prediction service for predictions。

The output of this stage is a deployed model prediction service。Finally。

 once all of your models have been trained and deployed is the role of the monitoring service to collect statistics on the model performance based on live data。

The output of this stage。Is the data collected in the logs from the operation of the serving infrastructure。

 including the prediction request data， which will be used to form the new data set and retrain your model。



![](img/795565b1aa7b428a58fbc1702582f304_4.png)