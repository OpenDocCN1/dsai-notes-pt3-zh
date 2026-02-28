# 杜克大学《应用Python数据工程（3课全）｜Applied Python Data Engineering》中英字幕 p12 12_02_04_Snowflake架构层.zh_en -BV1nz421i7KP_p12-

![](img/090cebcb090e2952c6b66ba8ece7cf6d_0.png)

Snowflake is designed into three layers。There's the cloud services layer on top。

There's a compute layer。And then a database storage layer。

 Each of these layers can be scaled separately from the others。

 So you only pay for the scaling you need for your usage。

 The database storage layer is fully managed by snowflake。So the size of files。

 the type of encryption， the layout， this is all managed on the snowflake side。

 you don't have any visibility into this directly。stored in an optimized column format。

And all of the data is compressed and encrypted。 The only way to access the data is using Snowflake SQL in the compute layer。

 the main item you'll interact with virtual warehouses。

A virtual warehouse is a cluster of nodes allocated by snowflake from a cloud provider。

These nodes are isolated between warehouses， so there's no performance effect between one warehouse and another。

And these warehouses can be scaled horizontally or vertically。So， horizontally。

Would be adding additional clusters of nodes to the warehouse and vertically would be adding larger or more powerful nodes。

Both of these scalings can be done with a warehouse while it's live。

And these warehouses are also designed to auto to stop， and auto to resume。

So you're only paying for the warehouse while it's up and running。 There's two type of warehouses。

 the standard warehouse and the newer snow Park warehouse。

The snowpar warehouse is designed for jobs that need a large amount of memory。

 such as machine learning task。 Cloud services layer is the layer you'll interact with to interface with all the other layers。

 It's where security， authentication and authorization are handled。

 And it's also where query optimization takes place。

 So every query you send into snowflake will go through the cloud services layer before it goes to the compute layer。



![](img/090cebcb090e2952c6b66ba8ece7cf6d_2.png)