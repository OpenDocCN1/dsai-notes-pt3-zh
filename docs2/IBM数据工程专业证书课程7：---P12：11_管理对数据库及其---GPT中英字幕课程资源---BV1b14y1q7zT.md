# IBM数据工程专业证书课程7：《关系数据库管理（DBA）》｜relational-database-administration｜ - P12：11_管理对数据库及其对象的访问.zh_en - GPT中英字幕课程资源 - BV1b14y1q7zT

![](img/af6c5e57d95c1f3feef9b884bffe59ae_0.png)

![](img/af6c5e57d95c1f3feef9b884bffe59ae_1.png)

Welcome to Man Access to databases and their Ob。

![](img/af6c5e57d95c1f3feef9b884bffe59ae_3.png)

After watching this video， you will be able to grant access to objects in a database。

 revoke access to objects in a database， and deny access to objects in a database。



![](img/af6c5e57d95c1f3feef9b884bffe59ae_5.png)

![](img/af6c5e57d95c1f3feef9b884bffe59ae_6.png)

After a user is authenticated on a database， they need permissions or privileges to access the objects and data in that database。



![](img/af6c5e57d95c1f3feef9b884bffe59ae_8.png)

![](img/af6c5e57d95c1f3feef9b884bffe59ae_9.png)

Privileges are granted to users and to groups or roles the combination of a user's own personal permissions and those of the groups or roles they belong to defines their overall permissions。



![](img/af6c5e57d95c1f3feef9b884bffe59ae_11.png)

![](img/af6c5e57d95c1f3feef9b884bffe59ae_12.png)

![](img/af6c5e57d95c1f3feef9b884bffe59ae_13.png)

In this video you will see examples of generic SQL statements the RDBMS that you are using may use slightly different syntax to the example shown here and is also likely to provide a graphical interface option to perform these tasks。



![](img/af6c5e57d95c1f3feef9b884bffe59ae_15.png)

![](img/af6c5e57d95c1f3feef9b884bffe59ae_16.png)

![](img/af6c5e57d95c1f3feef9b884bffe59ae_17.png)

In systems where users are authenticated outside the database。

 such as on the operating system or through an external plugin。

 you may also need to grant them access to the databases they will be working with you can use the SQL Grant Connect command to Gr Connect access to a particular database to a particular user group or role。



![](img/af6c5e57d95c1f3feef9b884bffe59ae_19.png)

![](img/af6c5e57d95c1f3feef9b884bffe59ae_20.png)

![](img/af6c5e57d95c1f3feef9b884bffe59ae_21.png)

![](img/af6c5e57d95c1f3feef9b884bffe59ae_22.png)

To grant connection access to an individual user rather than a group or role。

 you simply specify the username in place of the group name。



![](img/af6c5e57d95c1f3feef9b884bffe59ae_24.png)

![](img/af6c5e57d95c1f3feef9b884bffe59ae_25.png)

If your RDBMS provides a guest or public account， you may find that by default it has connect privileges to all databases In this scenario it is a good practice to revoke that permission so that you ensure only users given explicit permission can access your data。



![](img/af6c5e57d95c1f3feef9b884bffe59ae_27.png)

![](img/af6c5e57d95c1f3feef9b884bffe59ae_28.png)

![](img/af6c5e57d95c1f3feef9b884bffe59ae_29.png)

You use the SQL Gr command to grant privileges on tables in a database In this example。

 the sales team group is granted select privileges on the MyT table in the MyDB database。



![](img/af6c5e57d95c1f3feef9b884bffe59ae_31.png)

![](img/af6c5e57d95c1f3feef9b884bffe59ae_32.png)

![](img/af6c5e57d95c1f3feef9b884bffe59ae_33.png)

You can use similar statements to enable users to insert。

 update and delete data by granting them the relevant privileges on a table or tables to provide these privileges to an individual user。

 just replace the sales team group name with the name of that user。



![](img/af6c5e57d95c1f3feef9b884bffe59ae_35.png)

![](img/af6c5e57d95c1f3feef9b884bffe59ae_36.png)

You can also use the grant statement to grant privileges to create objects in a database This example shows how to enable a group or role to create a table。

 and again you can use a similar statement to enable a user to create an object such as a table or stored procedure。



![](img/af6c5e57d95c1f3feef9b884bffe59ae_38.png)

![](img/af6c5e57d95c1f3feef9b884bffe59ae_39.png)

![](img/af6c5e57d95c1f3feef9b884bffe59ae_40.png)

![](img/af6c5e57d95c1f3feef9b884bffe59ae_41.png)

On a procedure or function， you can permit a user or group to view the code。

 this means that they can view the definition of that function or procedure。

 but they will not be able to run it or change it to run the code。

 a user needs the execute permission and to change the definition of a procedure。

 a user needs the al permission。

![](img/af6c5e57d95c1f3feef9b884bffe59ae_43.png)

![](img/af6c5e57d95c1f3feef9b884bffe59ae_44.png)

![](img/af6c5e57d95c1f3feef9b884bffe59ae_45.png)

![](img/af6c5e57d95c1f3feef9b884bffe59ae_46.png)

As well as granting privileges， at times you may want to remove them。

 you can use the Reoke statement to remove granted privileges。

 and most RDBMSss will also provide revoke functionality in the user interface， however。

 because an individual's privileges are a combination of those granted to all the groups or roles they belong to。

 a member of the sales team role may still be able to access this table through their membership of another role。



![](img/af6c5e57d95c1f3feef9b884bffe59ae_48.png)

![](img/af6c5e57d95c1f3feef9b884bffe59ae_49.png)

![](img/af6c5e57d95c1f3feef9b884bffe59ae_50.png)

![](img/af6c5e57d95c1f3feef9b884bffe59ae_51.png)

![](img/af6c5e57d95c1f3feef9b884bffe59ae_52.png)

![](img/af6c5e57d95c1f3feef9b884bffe59ae_53.png)

If you want to ensure that users do not have permission for a certain object or action。

 you can use the Den statement to override any previous grant of that permission。



![](img/af6c5e57d95c1f3feef9b884bffe59ae_55.png)

![](img/af6c5e57d95c1f3feef9b884bffe59ae_56.png)

In this video you learned that you grant permissions to users， groups or roles。

 permissions control access to databases and the objects in them。

 the range of permissions from select to insert， update， delete， create， alter。

 and drop for different types of object， allow for fine tuning of access for users groups and roles。

 you can revoke a previously granted permission， and you deny a permission to override an existing granted permission。



![](img/af6c5e57d95c1f3feef9b884bffe59ae_58.png)

![](img/af6c5e57d95c1f3feef9b884bffe59ae_59.png)