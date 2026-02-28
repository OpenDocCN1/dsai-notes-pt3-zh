# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p98 14_01_04_持续部署Flask机器学习应用.zh_en -BV1tz421i7Ev_p98-

![](img/a243bc91a1f8e6e8f18d92f1ed40ad26_0.png)

Let's talk through how you can set up a continuous deployment pipeline for a flask machine learning service on any cloud platform so the core concepts to do this really involve the source code and this could be stored in GitHub。

 I think this is probably one of the most commonplaces it could also be stored in Gitlab or maybe a privately hosted Git repository or a cloudbased Git repository is another commonplace to store your code like for example。

 the native hosting service for AWS or for Azure or for GCP Next you'll have a branch and this branch will be let's say a master branch or a staging branch or potentially the production branch and this would be what will actually get built and in the case of production it would be the production machine learning application and as soon as an event happens here。

So this would be a push event， for example， a new change to the code。

 this triggers the build system and so this build system has some instructions set up into it and these instructions could be for example links my code make sure that there's no syntax problems with it do some basic tests in it and then go ahead and trigger infrastructure as code and you could use something like terraform or polemi or maybe AWS cloud formation or maybe a Yaml file for a cloud provider。

 but regardless this infrastructure as code step here will configure the remote deployment environment and allow you to do a deploy now note that in this case these are cloudn build servers and what's important about this word cloud native is that it means that these build servers are specifically designed for the cloud platforms that they're in。

has a cloud native build service called Azure Devops Google has one called Google Cloud build and AWS has one called AWS code build。

 so they're all very conceptually quite similar and their job is to sit in the middle here and listen for those events from source control and then do this change including setting up the infrastructure as code So defining the infrastructure。

 So once that's created and the code gets pushed now we're actually into the deployment target。

And the key thing to look at here is that the entire point of deploying machine learning automatically like this is so that it serves out a prediction and in this particular environment it could be let's say Azure app services which is a serverless environment that can run a flask application it could be Google app engine which again can run a flask application and it's not managed by the user or AWS Elastic Bean Sock is again another serverless environment so really there's much more in common than there is different in doing a flask-based machine learning service there are in the major cloud platforms's very similar serverless products and once it's deployed you would go through and maybe check it out and you can have a post deployloy action that would call the predict function and verify that it's actually serving out the correct prediction and this process would go on and on every time a change is occurring。

To this source control。 So really， this is the first trigger here。 All you need to do。

It's push a change to whatever branch you want to deploy to in the case of production。

 it would go through， build the software and then deploy it into production。

 it's possible in a day maybe there could be five changes that are made to production and they're continuously deployed constantly as updates to either the application source control or maybe the machine learning model accuracy are all created。



![](img/a243bc91a1f8e6e8f18d92f1ed40ad26_2.png)

![](img/a243bc91a1f8e6e8f18d92f1ed40ad26_3.png)