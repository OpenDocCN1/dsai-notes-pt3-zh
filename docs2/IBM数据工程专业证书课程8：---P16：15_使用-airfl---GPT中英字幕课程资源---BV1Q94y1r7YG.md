# IBM数据工程专业证书课程8：《使用Shell、Airflow和Kafka的ETL和数据管道课程（IBM）》｜etl-and-data-pipelines - P16：15_使用 airflow 构建 dag.zh_en - GPT中英字幕课程资源 - BV1Q94y1r7YG

![](img/9b863525c968314fe4f9d5135bbb2e23_0.png)

![](img/9b863525c968314fe4f9d5135bbb2e23_1.png)

Welcome to Build aDg usinging airflow。

![](img/9b863525c968314fe4f9d5135bbb2e23_3.png)

After watching this video， you will be able to interpret an airflow pipeline as a Python script that defines an airflow dag object。

 list the key components of a DAG definition file， create tasks by instantiating operators in your DAG definition file。

 and set up dependencies amongst tasks。An Apache airflow dag is a Python script which consists of the following logical blocks。

 Python library imports， DAG argument specification， the DAG definition or instantiation。

 individual task definitions which are the nodes of the DAG， and finally， the task pipeline。

 which specifies the dependencies between tasks。

![](img/9b863525c968314fe4f9d5135bbb2e23_5.png)

![](img/9b863525c968314fe4f9d5135bbb2e23_6.png)

![](img/9b863525c968314fe4f9d5135bbb2e23_7.png)

Let's implement a simple Apache airflow pipeline by writing a DAG definition script。

 we will create a very simple pipeline called simple example Dg。

pi that prints a greeting and then prints the current date and time we will also schedule it to repeat the process every five seconds。



![](img/9b863525c968314fe4f9d5135bbb2e23_9.png)

![](img/9b863525c968314fe4f9d5135bbb2e23_10.png)

![](img/9b863525c968314fe4f9d5135bbb2e23_11.png)

![](img/9b863525c968314fe4f9d5135bbb2e23_12.png)

Let's go through the list of logical blocks one by one begin by importing the Python libraries you will need for your DAG here。

 start by importing the DAG class from the airflowat library。

 then the Bsh operator which you will use to create the two print tasks and the date time module。

 which you will need for specifying several time related parameters。



![](img/9b863525c968314fe4f9d5135bbb2e23_14.png)

![](img/9b863525c968314fe4f9d5135bbb2e23_15.png)

![](img/9b863525c968314fe4f9d5135bbb2e23_16.png)

![](img/9b863525c968314fe4f9d5135bbb2e23_17.png)

The next block is for specifying the default dag arguments。

 noticeice that they are specified as a Python diict。

 which is just a collection of key value pairs enclosed by curly braces These are used to specify such things as the owner of the dag。

 which is you and its start date in this case， July 28，2021。

 the number of times it should keep trying if it is failing here only once if it does fail and the retri delay or the time to wait between subsequent tries。

 which in this case is five minutes。

![](img/9b863525c968314fe4f9d5135bbb2e23_19.png)

![](img/9b863525c968314fe4f9d5135bbb2e23_20.png)

![](img/9b863525c968314fe4f9d5135bbb2e23_21.png)

![](img/9b863525c968314fe4f9d5135bbb2e23_22.png)

![](img/9b863525c968314fe4f9d5135bbb2e23_23.png)

This next block is used for instantiating your workflow as a DAg object Here you can specify things like the name of your Dg。

 simpleple example， a description of your workflow。 for example， a simple example Dg。

 the default arguments to apply to your Dg， which in this case are specified by the default ag stick you already defined above and finally。

 scheduling instructions。 In this case， the Dg will run repeatedly on a schedule interval of5 seconds once it is deployed。



![](img/9b863525c968314fe4f9d5135bbb2e23_25.png)

![](img/9b863525c968314fe4f9d5135bbb2e23_26.png)

![](img/9b863525c968314fe4f9d5135bbb2e23_27.png)

![](img/9b863525c968314fe4f9d5135bbb2e23_28.png)

![](img/9b863525c968314fe4f9d5135bbb2e23_29.png)

![](img/9b863525c968314fe4f9d5135bbb2e23_30.png)

![](img/9b863525c968314fe4f9d5135bbb2e23_31.png)

Next comes the task definition block Here we define two tasks， T1 and Task2。

 both of which are bash operators， their respective IDs are specified as print Hello and print date they each call a bash command where the first task will echo greetings。

 the date and time R， and the second task will print the current date and time using the bash command date。



![](img/9b863525c968314fe4f9d5135bbb2e23_33.png)

![](img/9b863525c968314fe4f9d5135bbb2e23_34.png)

![](img/9b863525c968314fe4f9d5135bbb2e23_35.png)

![](img/9b863525c968314fe4f9d5135bbb2e23_36.png)

Finally， each task is assigned to the DAG you instantiated in the DAG definition block above。



![](img/9b863525c968314fe4f9d5135bbb2e23_38.png)

The final block is where you specify the dependencies for your workflow like this here。

 the double greater than notation specifies that task2 is downstream from task 1。

 This means the task1， which we named print Ho will run first。

 and once print Hello runs successfully， task2 or print date will run。

 This completes the creation of your airflow da， and you now have a good idea of the general pattern。



![](img/9b863525c968314fe4f9d5135bbb2e23_40.png)

![](img/9b863525c968314fe4f9d5135bbb2e23_41.png)

In this video you learned that an airflow pipeline is a Python script that instantiates an airflow DAG object key components of a DAG definition file are library imports DAG arguments DAG and task definitions and the task pipeline specification you can specify a schedule interval in your DAG definition if you want it to run repeatedly by setting the Sch interval parameter。

 and finally， tasks are instantiated operators imported from the Apache airflow operators' module。



![](img/9b863525c968314fe4f9d5135bbb2e23_43.png)

![](img/9b863525c968314fe4f9d5135bbb2e23_44.png)