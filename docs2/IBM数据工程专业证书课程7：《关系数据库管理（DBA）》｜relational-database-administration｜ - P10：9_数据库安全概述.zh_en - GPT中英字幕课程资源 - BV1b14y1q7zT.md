# IBM数据工程专业证书课程7：《关系数据库管理（DBA）》｜relational-database-administration｜ - P10：9_数据库安全概述.zh_en - GPT中英字幕课程资源 - BV1b14y1q7zT

![](img/7f3e5bd13a57c2be1796c7757c350a2e_0.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_1.png)

Welcome to the overview of database security After watching this video。

 you will be able to describe different levels of database security。

 explain the difference between authentication and authorization。

 identify the granularity of security on objects in a database。

 and describe how auditing encryption and application security can enhance your database security。



![](img/7f3e5bd13a57c2be1796c7757c350a2e_3.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_4.png)

Ensuring the security of the data stored in your systems is an essential part of the database management role it involves identifying the potential risks to your data and mitigating those risks by applying security measures and controls at all levels of a system。

 even though the actual implementation of the measures at some levels may not be your direct responsibility。

 it is imperative that you evaluate that they are adequate for the data you store or access there。



![](img/7f3e5bd13a57c2be1796c7757c350a2e_6.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_7.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_8.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_9.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_10.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_11.png)

First， you need to make sure that the actual servers in your system are physically secure for unpremised servers。

 you should assess who has access to server location and the security measures in place if you are using a managed cloud environment。

 your provider will be responsible for the security at this level。



![](img/7f3e5bd13a57c2be1796c7757c350a2e_13.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_14.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_15.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_16.png)

Next， you should consider the operating system hosting your database。

 you should ensure that it is regularly patched with the latest tested updates。

 that it is hardened using a known configuration to reduce vulnerabilities。

 and that it is continuously monitored for any unauthorized access。



![](img/7f3e5bd13a57c2be1796c7757c350a2e_18.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_19.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_20.png)

You should take similar measures on your RDBMS to those for your operating system。

 you should regularly apply the latest tested updates。

 you should review and use all security features and configuration options available in the system。

 and also you should ensure that only a small set of trusted users have administrative privileges。



![](img/7f3e5bd13a57c2be1796c7757c350a2e_22.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_23.png)

Users and client applications need to be permitted to access a server or database and the objects in it First。

 users need to be authenticated on the server or database to enable them to access it。

 and then they need to be granted permissions on individual objects or groups of objects in the database to interact with them。



![](img/7f3e5bd13a57c2be1796c7757c350a2e_25.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_26.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_27.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_28.png)

Database authentication is similar to the authentication you use when using a pin or fingerprint to access your cell phone or a password to access your computer。

 it is a process of verifying that the user is who they claim to be， for example。

 by validating credentials such as username and password。



![](img/7f3e5bd13a57c2be1796c7757c350a2e_30.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_31.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_32.png)

Some database systems enable you to use operating system or other credentials to authenticate against a database for example。

 you can use external authentication methods such as Pgable authentication moduleule or PAM。

 Windows login IDs， lightweight Directory Access Pro， LDAP， or Kbs。

Even when a user is authenticated on a database， they still need to be authorized to access the objects and data in the database you authorize users by giving them permissions or privileges to access objects and data because groups of users often need the same access privileges in most RDBMSSs。

 you can grant privileges to a group of users who undertake a specific role in that database。



![](img/7f3e5bd13a57c2be1796c7757c350a2e_34.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_35.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_36.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_37.png)

Assigning privileges will vary depending on the object you are working with， for example。

 on a table you can allow users to select。

![](img/7f3e5bd13a57c2be1796c7757c350a2e_39.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_40.png)

Insert。update。

![](img/7f3e5bd13a57c2be1796c7757c350a2e_42.png)

Or delete data。Or to alter the structure of the table。



![](img/7f3e5bd13a57c2be1796c7757c350a2e_44.png)

In some RDBMSs， you can narrow this down even further to assign privileges on a columnar basis。

 you should always use the principle of least privilege， that is。

 only allow users to access the least amount of data that they need to succeed in their tasks。



![](img/7f3e5bd13a57c2be1796c7757c350a2e_46.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_47.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_48.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_49.png)

In addition to restricting users to only access the information and objects that their role requires。

 you should also consider monitoring and auditing database activity。

 you should track which users access a server or database and the actions that they perform。

 analyzing this information against your security plan can alert you to gaps in it。



![](img/7f3e5bd13a57c2be1796c7757c350a2e_51.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_52.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_53.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_54.png)

As well as securing your systems and data and auditing access to it。

 you could consider using encryption to add another layer to your security system if an intruder does manage to access the data。

 they also have to decrypt the data to make any use of it certain industry regulations and regions。

 legislate the use of specific levels of encryption for sensitive data it is important to check such regulations for algorithm and key management requirements when planning your database security Do remember though that encrypting and decrypting data can be a time and resource intensive operation so you will need to consider the impact this will have on your operations and whether you need to upgrade your hardware accordingly。



![](img/7f3e5bd13a57c2be1796c7757c350a2e_56.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_57.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_58.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_59.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_60.png)

Even the most secure combination of operating system and RDBMS can be compromised by LAX application security。

 such as SQL injection strings and insecure code； therefore it is important that you test and monitor the security of any applications interacting with your data and databases。



![](img/7f3e5bd13a57c2be1796c7757c350a2e_62.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_63.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_64.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_65.png)

In this video you learned that when securing a database。

 you need to consider the security of the server and operating system as well as the database and data users need to be authenticated on the server or database to access it users need to be authorized that is given permissions or privileges to access the objects and data in the database you should use the principle of least privilege to reduce access to data Mon and auditing database activity can alert you to threats and security gaps encryptryion can strengthen your data security by making it harder to read any compromised data and data security includes securing your applications。



![](img/7f3e5bd13a57c2be1796c7757c350a2e_67.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_68.png)

![](img/7f3e5bd13a57c2be1796c7757c350a2e_69.png)