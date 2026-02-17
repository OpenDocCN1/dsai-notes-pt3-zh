# 大型语言模型实践（高级数据工程、AWS、Databricks和本地LLM）：P28：28_02_02：引言_4

在本节课中，我们将学习有向无环图（DAGs）的基本概念。我们将从最简单的实现方法开始，逐步了解其组成部分、构建方式，并实践使用Python和相关依赖来创建一个DAG。我们还将探索用户界面（仪表板）以监控任务执行，最后理解“回填”操作的含义与实施方法。

## 什么是有向无环图（DAGs）？

有向无环图，简称DAGs，是一种由节点和有向边组成的数据结构。其中，边表示节点间的依赖关系，并且整个图不允许出现循环。这意味着任务只能沿着一个方向执行，不会形成闭环。

上一节我们介绍了DAGs的基本定义，本节中我们来看看如何构建一个最简单的DAG。

## 使用Python构建基础DAG

我们将从最基础的案例开始，使用Python来构建一个DAG。这通常需要安装任务可能依赖的特定Python库。

以下是构建一个简单DAG的基本步骤：

1.  **导入必要的库**：首先，需要导入用于定义和调度DAG的框架库，例如Apache Airflow的核心模块。
2.  **定义DAG对象**：创建一个DAG实例，并设置其基本属性，如唯一标识符、开始日期和调度间隔。
    ```python
    from airflow import DAG
    from datetime import datetime

    dag = DAG(
        dag_id='my_simple_dag',
        start_date=datetime(2023, 1, 1),
        schedule_interval='@daily'
    )
    ```
3.  **定义任务（Operators）**：在DAG中，每个节点代表一个任务。我们需要使用特定的“操作符”来定义这些任务。
    ```python
    from airflow.operators.python_operator import PythonOperator

    def print_hello():
        print("Hello from the DAG!")

    hello_task = PythonOperator(
        task_id='hello_task',
        python_callable=print_hello,
        dag=dag
    )
    ```
4.  **设置任务依赖关系**：通过定义任务执行的先后顺序来构建DAG的边。例如，如果存在多个任务，可以使用 `>>` 运算符设置依赖。
    ```python
    # 假设有另一个任务 goodbye_task
    hello_task >> goodbye_task
    ```

## 探索用户界面（仪表板）

在定义并部署DAG之后，我们可以通过用户界面（通常是一个Web仪表板）来监控和管理它。仪表板允许我们直观地查看DAG的运行状态、触发任务执行、检查日志以及分析任务执行的历史记录。

通过操作仪表板，我们可以实时反思刚刚被触发的任务动作，确认其是否按预期执行。

## 理解并执行回填操作

最后，我们将探讨“回填”的概念。回填是指针对过去某个时间段内的数据，重新执行DAG中的任务。这在以下场景中非常有用：当添加了新任务、修改了数据处理逻辑，或者需要补全历史数据时。

回填操作意味着调度器会根据DAG的定义，为指定的历史日期范围创建并运行任务实例，而不是仅仅等待未来的调度时间点触发。

![](img/489e5c4bfc9fdea90c6c70f003d3e7f3_1.png)

本节课中我们一起学习了有向无环图（DAGs）的核心概念。我们从最简单的Python实现入手，了解了DAG的组成部分和构建流程。随后，我们探索了如何通过用户界面监控任务执行。最后，我们掌握了回填操作的含义及其应用场景。通过这些步骤，你已具备了构建和操作基础数据流水线的初步能力。