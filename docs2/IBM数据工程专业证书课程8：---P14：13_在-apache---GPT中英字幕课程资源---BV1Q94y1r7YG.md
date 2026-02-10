# IBM数据工程专业证书课程8：《使用Shell、Airflow和Kafka的ETL和数据管道课程（IBM）》｜etl-and-data-pipelines - P14：13_在 apache airflow 中使用数据流水线作为 dags 的优势.zh_en - GPT中英字幕课程资源 - BV1Q94y1r7YG

![](img/f02780fed08073a7bad0a03e33513511_0.png)

![](img/f02780fed08073a7bad0a03e33513511_1.png)

Welcome to advantages of representing data pipelines as DAGs in Apache airflow After watching this video。

 you will be able to define what a directed acyclic graph or DAG is。

 describe workflows as daAGs of tasks and dependencies。

 outline the components of a DAG definition file， describe how Apache airflow scheduler executes tasks on an array of workers。

 and list key advantages of defining workflows as code。



![](img/f02780fed08073a7bad0a03e33513511_3.png)

![](img/f02780fed08073a7bad0a03e33513511_4.png)

![](img/f02780fed08073a7bad0a03e33513511_5.png)

A De is a special kind of graph called a directed acyclic graph。

 A simple graph consists of nodes and edges like this Here， the circles are called nodes。

 and the lines connecting pairs of nodes are called edges。 A directed graph is also a graph。

 but it has more structure。 As you can see here， Each edge has a specified direction。

 It connects a starting node with another node。 And lastly。

 the acyclic part means there are no loops or sequences of directed edges that return to a node in the chain。

 such as the red cycle shown here。😊。

![](img/f02780fed08073a7bad0a03e33513511_7.png)

![](img/f02780fed08073a7bad0a03e33513511_8.png)

![](img/f02780fed08073a7bad0a03e33513511_9.png)

![](img/f02780fed08073a7bad0a03e33513511_10.png)

Let's take a look at a few examples of dagGs。 The simplest nontrivial dag has a single directed edge and looks like this。

 It has a single root node which is connected to a single terminal node。



![](img/f02780fed08073a7bad0a03e33513511_12.png)

![](img/f02780fed08073a7bad0a03e33513511_13.png)

![](img/f02780fed08073a7bad0a03e33513511_14.png)

Here's another dag which we've already seen， it also has single root and terminal nodes。



![](img/f02780fed08073a7bad0a03e33513511_16.png)

Here's an example of a tree， which is a commonly used graph for representing family trees or directory structures。

 All trees are dags， but not all dags are trees。 For example。

 this tagg is not a tree since it has more than one root node。

 A dag doesn't impose those restrictions， So a single node can have multiple parents and there may be multiple nodes with no parents。



![](img/f02780fed08073a7bad0a03e33513511_18.png)

![](img/f02780fed08073a7bad0a03e33513511_19.png)

![](img/f02780fed08073a7bad0a03e33513511_20.png)

![](img/f02780fed08073a7bad0a03e33513511_21.png)

Dags are used to represent workflows or pipelines in Apache airflow。

 Each task performed by your data pipeline is represented as a node in a daAg while each of the dependencies between two tasks in your pipeline are represented as a directed edge in the Dg。

 In other words， edges define the order in which the two tasks should run。 Thus。

 daAgs are used in airflow to define what tasks should run and in what sequence they should run。

 A dag is defined in a Python script， which represents the DAg structure。 Thus。

 the tasks and their dependencies are defined as code。 Also。

 scheduling instructions are specified as code in the Dg script。



![](img/f02780fed08073a7bad0a03e33513511_23.png)

![](img/f02780fed08073a7bad0a03e33513511_24.png)

![](img/f02780fed08073a7bad0a03e33513511_25.png)

![](img/f02780fed08073a7bad0a03e33513511_26.png)

![](img/f02780fed08073a7bad0a03e33513511_27.png)

Let's take a closer look at the nodes or tasks in a Dg， just like the Dg itself。

 each task performed within your Dg is also written in Python。 Each task implements an operator。

 for example， a Python operator is used to deploy some Python code。

 A SQL operator to run a SQL query and a bash operator can be used to run a bash command。

 Operaators are used to define what each task in your Dg does。

 Senors are a class of operators which are used to pull for a certain time or condition to be met。

 For example， you can use a sensor to check every 30 seconds whether a file exists or whether another dag has finished running。



![](img/f02780fed08073a7bad0a03e33513511_29.png)

![](img/f02780fed08073a7bad0a03e33513511_30.png)

![](img/f02780fed08073a7bad0a03e33513511_31.png)

![](img/f02780fed08073a7bad0a03e33513511_32.png)

There are many other types of operators， including email and HTTP request operators。

An Apache airflow dag is a Python script consisting of the following logical blocks， library imports。

 DAg arguments， DAg definition， task definitions， and task pipeline。



![](img/f02780fed08073a7bad0a03e33513511_34.png)

![](img/f02780fed08073a7bad0a03e33513511_35.png)

Let's briefly go over an example The first block of your DAG definition script is where you import any Python libraries that you require。

 for example， the from Airflow I DAg command to import the DAG module from the airflow collection。

The next block of code is for specifying default arguments for your DAG。

 such as its default start date Next comes the DAG definition or instantiation block for your DAG which specifies things like your default arguments。

Continuing along with our example DAG code， individual task definitions。

 which are the nodes of the DAG form your DAG's next building block。In this example。

 we have two tasks which happen to be bash operators。Finally。

 the task pipeline specifies the dependencies between your tasks here。

 taskask2 depends on the result of task1， and this forms the last logical block of your DAg script。



![](img/f02780fed08073a7bad0a03e33513511_37.png)

Your new dag has been created， but it hasn't yet been deployed To that end。

 Airflow scheduler is designed to run as a persistent service within the airflow production environment。

 Apache airflow scheduler can be used to deploy your workflow on an array of workers。

 It follows the tasks and dependencies that you specified in your dag。

 Once you start an airflow scheduler instance。 Your dags will start running based on the start date you specified as code in each of your dags。

 After that， the scheduler triggers each subsequent dag run。

 according to the schedule interval that you specified。



![](img/f02780fed08073a7bad0a03e33513511_39.png)

![](img/f02780fed08073a7bad0a03e33513511_40.png)

![](img/f02780fed08073a7bad0a03e33513511_41.png)

![](img/f02780fed08073a7bad0a03e33513511_42.png)

![](img/f02780fed08073a7bad0a03e33513511_43.png)

![](img/f02780fed08073a7bad0a03e33513511_44.png)

One of the key advantages of Apache airflow's approach to representing data pipelines as DAs is the fact that they are expressed as code When workflows are defined as code。

 they become more maintainable developers can follow explicitly what has been specified by reading the code Verable code revisions can easily be tracked by a version control system such as Git Coabor Team of developers can easily collaborate on both development and maintenance of the code for the entire workflow and testable Any revisions can be passed through unit tests to ensure the code still works as intended。



![](img/f02780fed08073a7bad0a03e33513511_46.png)

![](img/f02780fed08073a7bad0a03e33513511_47.png)

![](img/f02780fed08073a7bad0a03e33513511_48.png)

![](img/f02780fed08073a7bad0a03e33513511_49.png)

![](img/f02780fed08073a7bad0a03e33513511_50.png)

![](img/f02780fed08073a7bad0a03e33513511_51.png)

![](img/f02780fed08073a7bad0a03e33513511_52.png)

![](img/f02780fed08073a7bad0a03e33513511_53.png)

In this video you learned that in Apache airflow daAgs are workflows defined as Python code tasksask which are nodes in your DAG are created by implementing airflows built in operators pipelines are specified as dependencies between tasks which are the directed edges between nodes in your DAG airflow scheduler schedules and deploys your DAgs and finally the key advantage of Apache airflow's approach to representing data pipelines as DAGs is the fact that they are expressed as code According it makes your data pipelines more maintainable testable and collaborative。



![](img/f02780fed08073a7bad0a03e33513511_55.png)

![](img/f02780fed08073a7bad0a03e33513511_56.png)

![](img/f02780fed08073a7bad0a03e33513511_57.png)

![](img/f02780fed08073a7bad0a03e33513511_58.png)