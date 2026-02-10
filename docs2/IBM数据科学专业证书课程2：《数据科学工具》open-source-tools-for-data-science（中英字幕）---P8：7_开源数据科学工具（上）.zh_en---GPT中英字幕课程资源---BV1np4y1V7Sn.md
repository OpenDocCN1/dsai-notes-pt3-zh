# IBM数据科学专业证书课程2：《数据科学工具》open-source-tools-for-data-science（中英字幕） - P8：7_开源数据科学工具（上）.zh_en - GPT中英字幕课程资源 - BV1np4y1V7Sn

In part one of this twopart series will cover data management， open source data integration。

 transformation and visualization tools。 The most widely used open source data management tools are relational databases such as My SQL and PostgresQL。

 No SQL databases such as Mongo DB， Apache Couch Db and Apache Cassandra and filebased tools such as the Hadoop file system or Cloud file systems like CF。

 Finally， elasticastic search is mainly used for storing text data and creating a search index for Fast document retrieval。



![](img/4d8872522b37b73326239bfd265ac03e_1.png)

![](img/4d8872522b37b73326239bfd265ac03e_2.png)

![](img/4d8872522b37b73326239bfd265ac03e_3.png)

![](img/4d8872522b37b73326239bfd265ac03e_4.png)

![](img/4d8872522b37b73326239bfd265ac03e_5.png)

The task of data integration and transformation in the classic data warehousing world is called ETL。

 which stands for extract， transformform and load These days。

 data scientists often propose the term ELT extract load transform。

 stressing the fact that data is dumped somewhere and the data engineer or data scientists themselveslf is responsible for data。

Another term for this process has now emerged， data refining and cleaning。

Here are the most widely used open source data integration and transformation tools。



![](img/4d8872522b37b73326239bfd265ac03e_7.png)

Apache Airflow originally created by Airbnb Cubeflow。

 which enables you to execute data science pipelines on top of Kubernetes。 Apache Kafka。

 which originated from LinkedIn Apache Nfi， which delivers a very nice visual editor。

 Apache Sparks SQL， which enables you to use AiSQL and scales up to compute clusters of thousands of nodes and node red。

 which also provides a visual editor。 nodede Red consumes so little in resources that it even runs on small devices like a Raspberry Pi。

😊。

![](img/4d8872522b37b73326239bfd265ac03e_9.png)

![](img/4d8872522b37b73326239bfd265ac03e_10.png)

![](img/4d8872522b37b73326239bfd265ac03e_11.png)

![](img/4d8872522b37b73326239bfd265ac03e_12.png)

![](img/4d8872522b37b73326239bfd265ac03e_13.png)

We'll now introduce the most widely used open source data visualization tools。

 We have to distinguish between programming libraries where you need to use code and tools that contain a user interface。

 The most popular libraries are covered in the next videos。



![](img/4d8872522b37b73326239bfd265ac03e_15.png)

A similar approach uses Hue， which can create visualizations from SQL queries。 Kibaana。

 a data exploration and visualization web application is limited to Elasticsearch the data provider。

 Finally， Apache superet is a data exploration and visualization web application。



![](img/4d8872522b37b73326239bfd265ac03e_17.png)

Model deployment is extremely important Once you've created a machine learning model capable of predicting some key aspects of the future。

 you should make that model consumable by other developers and turn it into an API。

 Apache prediction I O currently only supports Apache Spark M L models for deployment。

 but support for all sorts of other libraries is on the roadmap。

 Seldon is an interesting product since it supports nearly every framework。

 including Tensorflow Apache Spark M L R and Psitt Learn。

 Seldon can run on top of Kubernetes and Red Ha Openshift。 Another way to deploy Spark M L models。

 is using M leapap。😊。

![](img/4d8872522b37b73326239bfd265ac03e_19.png)

![](img/4d8872522b37b73326239bfd265ac03e_20.png)

![](img/4d8872522b37b73326239bfd265ac03e_21.png)

![](img/4d8872522b37b73326239bfd265ac03e_22.png)

![](img/4d8872522b37b73326239bfd265ac03e_23.png)

Finally， Tensorflowlow can serve any of its models using the Tensorflow service。

 You can deploy to an embedded device like a raspberry Pi or a smartphone using Tensorflowlow light and even deploy to a web browser using Tensorflow。

 Js。😊。

![](img/4d8872522b37b73326239bfd265ac03e_25.png)

![](img/4d8872522b37b73326239bfd265ac03e_26.png)

![](img/4d8872522b37b73326239bfd265ac03e_27.png)

Model monitoring is another crucial step。 Once you've deployed a machine learning model。

 you need to keep track of its prediction performance as new data arrives in order to maintain outdated models。

 Following are some examples of model monitoring tools。



![](img/4d8872522b37b73326239bfd265ac03e_29.png)

![](img/4d8872522b37b73326239bfd265ac03e_30.png)

![](img/4d8872522b37b73326239bfd265ac03e_31.png)

Model DB is a machine model meta databasease where information about the models are stored and can be queried。

 it natively supports Apache Spark ML pipelines and Psyit Learn。



![](img/4d8872522b37b73326239bfd265ac03e_33.png)

A generic multipurpose tool called Prometheus is also widely used for machine learning model monitoring。

 although it's not specifically made for this purpose。



![](img/4d8872522b37b73326239bfd265ac03e_35.png)

Model performance is not exclusively measured through accuracy。

 Model bias against protected groups like gender or race is also important。

 The IBM AI Fairness 360 open source toolkit does exactly this。

 It detects and mitigates against bias in machine learning models。



![](img/4d8872522b37b73326239bfd265ac03e_37.png)

![](img/4d8872522b37b73326239bfd265ac03e_38.png)

Machine learning models， especially neural network based deep learning models。

 can be subject to adversarial attacks， where an attacker tries to fool the model with manipulated data or by manipulating the model itself。

 The IBM adversarial robustness 360 toolbox can be used to detect vulnerability to adversarial attacks and help make the model more robust。



![](img/4d8872522b37b73326239bfd265ac03e_40.png)

![](img/4d8872522b37b73326239bfd265ac03e_41.png)

![](img/4d8872522b37b73326239bfd265ac03e_42.png)

Machine learning models often considered to be a black box that apply some mysterious magic。

 The IBM AI explainplainability 360 toolkit makes the machine learning process more understandable by finding similar examples within a data set that can be presented to a user for manual comparison。

😊。

![](img/4d8872522b37b73326239bfd265ac03e_44.png)

![](img/4d8872522b37b73326239bfd265ac03e_45.png)

![](img/4d8872522b37b73326239bfd265ac03e_46.png)

![](img/4d8872522b37b73326239bfd265ac03e_47.png)

The IBM AI explainplainability 360 toolkit can also illustrate training for a simpler machine learning model by explaining how different input variables affect the final decision of the model。



![](img/4d8872522b37b73326239bfd265ac03e_49.png)

![](img/4d8872522b37b73326239bfd265ac03e_50.png)

Options for code asset management tools have been greatly simplified for code asset management。

 also referred to as version management or version control。 Git is now the standard。



![](img/4d8872522b37b73326239bfd265ac03e_52.png)

Multiple services have emerged to support Git with the most prominent being Gitthub。

 which provides hosting for software development version management。

 The runner up is definitely Git Lab， which has the advantage of being a fully open source platform that you can host and manage yourself。

 Another choice is Bi bucket。😊。

![](img/4d8872522b37b73326239bfd265ac03e_54.png)

Data asset management， also known as data governance or data lineage。

 is another crucial part of enterprise grade data science。

 Data has to be versioned and annotated with metadata。

 Apache Atlas is a tool that supports this task。

![](img/4d8872522b37b73326239bfd265ac03e_56.png)

Another interesting project， ODPI Igeria， is managed through the Linux Foundation and is an open ecosystem。



![](img/4d8872522b37b73326239bfd265ac03e_58.png)

It offers a set of open APIs， types， and interchange protocols that metadata repositories use to share and exchange data。



![](img/4d8872522b37b73326239bfd265ac03e_60.png)

Finally， KO is an open source data lake management software platform that provides extensive support for a wide range of data asset management tasks。



![](img/4d8872522b37b73326239bfd265ac03e_62.png)

![](img/4d8872522b37b73326239bfd265ac03e_63.png)

![](img/4d8872522b37b73326239bfd265ac03e_64.png)

This concludes part one of this two part series。 Let's move on to part2。



![](img/4d8872522b37b73326239bfd265ac03e_66.png)