# CMU《机器学习实践｜17-691 Machine Learning in Practice 2023》中英字幕 p09 [P9]Recitation 02_2.zh_en [BV18TUQBJEfH_p9]

![](img/ce38838bd1264b152b88a78816a035e9_1.png)

![](img/ce38838bd1264b152b88a78816a035e9_3.png)

![](img/ce38838bd1264b152b88a78816a035e9_5.png)

## Docker Composeose：容器编排与Airflow应用

在本节课中，我们将学习如何使用Docker Composeose进行容器编排，并探讨Airflow在机器学习产品中的应用。

### 1. 容器编排与微服务

Docker容器代表应用程序中的单个组件。当这些组件协同工作时，我们称之为容器编排。管理层确保这些服务可以相互通信，就像它们是一个应用程序一样。API网关提供应用程序的接口，而服务则通过服务网格进行通信。

![](img/ce38838bd1264b152b88a78816a035e9_7.png)

**公式**：容器编排 = 容器 + 管理层 + 通信

![](img/ce38838bd1264b152b88a78816a035e9_9.png)

![](img/ce38838bd1264b152b88a78816a035e9_10.png)

![](img/ce38838bd1264b152b88a78816a035e9_12.png)

### 2. Airflow：数据管道编排工具

Airflow是一个开源平台，用于部署、调度和监控数据管道。它支持批处理工作流程，具有直观的用户界面和简单的学习曲线。

![](img/ce38838bd1264b152b88a78816a035e9_14.png)

**代码**：pip install airflow

### 3. Airflow应用示例

本节课中，我们将使用Airflow创建一个简单的数据管道，该管道从API获取数据，并打印出来。

![](img/ce38838bd1264b152b88a78816a035e9_16.png)

**步骤**：

![](img/ce38838bd1264b152b88a78816a035e9_18.png)

1. 创建Docker容器，包括数据库、Redis、Jupyter Lab、Web服务器、调度器、工作进程、触发器和初始化容器。
2. 使用Docker Composeose启动应用程序。
3. 在Airflow中创建DAG，定义数据管道的步骤。
4. 运行DAG并查看日志。

### 4. Airflow与Python

Airflow支持使用Python编写DAG，这使得数据管道的创建和修改变得非常简单。

![](img/ce38838bd1264b152b88a78816a035e9_20.png)

**代码**：

![](img/ce38838bd1264b152b88a78816a035e9_22.png)

![](img/ce38838bd1264b152b88a78816a035e9_24.png)

```python
from airflow import DAG
from airflow.operators.python_operator import PythonOperator

![](img/ce38838bd1264b152b88a78816a035e9_26.png)

dag = DAG('my_dag', start_date=datetime(2023, 1, 1))

def fetch_data():
    # 获取数据
    pass

def process_data():
    # 处理数据
    pass

![](img/ce38838bd1264b152b88a78816a035e9_28.png)

task1 = PythonOperator(
    task_id='fetch_data',
    python_callable=fetch_data,
    dag=dag
)

![](img/ce38838bd1264b152b88a78816a035e9_30.png)

task2 = PythonOperator(
    task_id='process_data',
    python_callable=process_data,
    dag=dag
)

![](img/ce38838bd1264b152b88a78816a035e9_32.png)

![](img/ce38838bd1264b152b88a78816a035e9_34.png)

task1 >> task2
```

![](img/ce38838bd1264b152b88a78816a035e9_36.png)

![](img/ce38838bd1264b152b88a78816a035e9_38.png)

### 5. Airflow与依赖管理

![](img/ce38838bd1264b152b88a78816a035e9_40.png)

如果DAG需要额外的依赖项，可以使用Dockerfile创建自定义镜像。

**代码**：

```Dockerfile
FROM airflow:latest
RUN pip install scikit-learn
```

![](img/ce38838bd1264b152b88a78816a035e9_42.png)

### 总结

![](img/ce38838bd1264b152b88a78816a035e9_44.png)

![](img/ce38838bd1264b152b88a78816a035e9_46.png)

![](img/ce38838bd1264b152b88a78816a035e9_48.png)

本节课中，我们学习了如何使用Docker Composeose进行容器编排，并探讨了Airflow在机器学习产品中的应用。通过Airflow，我们可以轻松创建、部署和监控数据管道，从而提高机器学习产品的效率和质量。