# IBM数据工程专业证书课程7：《关系数据库管理（DBA）》｜relational-database-administration｜ - P14：13_加密数据.zh_en - GPT中英字幕课程资源 - BV1b14y1q7zT

![](img/209d62a5962f073fced12b33046ca805_0.png)

![](img/209d62a5962f073fced12b33046ca805_1.png)

Welcome to Encrypting data。

![](img/209d62a5962f073fced12b33046ca805_3.png)

After watching this video you will be able to explain the advantages of encrypting data。

 describe the encryption algorithms and keys， identify the differences between symmetric and asymmetric encryption。

 explain transparent data encryption， explain customer managed keys。

 list encryption versus performance tradeoffs， and describe how RDBMSs can encrypt data in transit。



![](img/209d62a5962f073fced12b33046ca805_5.png)

Data encryption provides yet another layer in your security system and is often the last line of defense if data is compromised。

 it can help to protect your data at rest and during transmission Some industries such as financial and medical services。

 regions or specific customers may also require that you encrypt certain types of data for example。

 the payment card industry data security standard or PCI DSS requires that all companies that process。

 transmit or store credit card information encrypt that data。



![](img/209d62a5962f073fced12b33046ca805_7.png)

![](img/209d62a5962f073fced12b33046ca805_8.png)

![](img/209d62a5962f073fced12b33046ca805_9.png)

At rest data refers to your data when it is stored or at rest in your RDBMS it is important to encrypt data at rest to ensure that malicious users can directly access the data files bypassing your database security measures Some RDBMSSs provide database level encryption for the entire database This is often termed transparent data encryption or TDE Some provide table or tablespace encryption for individual tables。

 and some provide column level for maximum granularity and flexibility do note though that the flexibility that column level encryption provides is counteracted by performance degradation and complexity of setup。



![](img/209d62a5962f073fced12b33046ca805_11.png)

![](img/209d62a5962f073fced12b33046ca805_12.png)

![](img/209d62a5962f073fced12b33046ca805_13.png)

![](img/209d62a5962f073fced12b33046ca805_14.png)

![](img/209d62a5962f073fced12b33046ca805_15.png)

![](img/209d62a5962f073fced12b33046ca805_16.png)

![](img/209d62a5962f073fced12b33046ca805_17.png)

![](img/209d62a5962f073fced12b33046ca805_18.png)

![](img/209d62a5962f073fced12b33046ca805_19.png)

You encrypt data by using an algorithm to change the data into an unreadable string commonly known ascipher textex。

 these algorithms use a key to ensure that anyone trying to decipher the text can do so without the key。



![](img/209d62a5962f073fced12b33046ca805_21.png)

The simplest form of encryption is symmetric encryption。

 where the same key is used to encrypt and decrypt the data。

 mechanisms such as data encryption standard or DES and advanced encryption standard or AES use symmetric keys when using only one key。

 it must be shared between all parties wanting to access that data so that they can all decrypt it。



![](img/209d62a5962f073fced12b33046ca805_23.png)

![](img/209d62a5962f073fced12b33046ca805_24.png)

![](img/209d62a5962f073fced12b33046ca805_25.png)

![](img/209d62a5962f073fced12b33046ca805_26.png)

Sharing a key increases the likelihood of it being compromised and if the key to the encryption is compromised。

 your data is effectively compromised。Alternatively。

 some databases use asymmetric encryption also known as public key encryption。 This uses two keys。

 a public key and a private key known as a key pair。

 You encrypt the data with the public key and valid users have a unique matching private key to decrypt it。

 Reves Shamir Adelman or RSA and elliptic curve cryptography or ECC are both examples of asymmetric encryption。

 because asymmetric encryption involves the use of multiple private keys。

 It is essential that those keys are held securely。



![](img/209d62a5962f073fced12b33046ca805_28.png)

![](img/209d62a5962f073fced12b33046ca805_29.png)

Most modern databases take care of the complexity of encryption and key management for you。

 many of them support transparent data encryption or TDE the transparent part of its name alludes to the fact that the encryption and decryption is not visible to your users the database engine encrypts the data before storing it and then decrypts it when the authorized user or application requests information。



![](img/209d62a5962f073fced12b33046ca805_31.png)

![](img/209d62a5962f073fced12b33046ca805_32.png)

![](img/209d62a5962f073fced12b33046ca805_33.png)

![](img/209d62a5962f073fced12b33046ca805_34.png)

![](img/209d62a5962f073fced12b33046ca805_35.png)

Because the database engine is performing the encryption tasks。

 it also encrypts your database backups too。

![](img/209d62a5962f073fced12b33046ca805_37.png)

Although TDE simplifies the process of encrypting your database。

 you may have concerns about storing data in the cloud and relinquishing the key management process to a third party some cloud databases support customer managed keys。

 also known as the B your own key or BYO protocol This provides a separation of responsibility so that your cloud database system is responsible for the encryption process。

 but you retain control of the keys that it uses BYO provides an extra level of protection by ensuring that the cloud platform storing and encrypting your data does not have access to the decryption keys。

 so it cannot access your confidential data It also enables your security admins to manage your corporate keys while your database admins can continue to manage the data and for businesses whose customers require regulatory compliance around key rotation and expiration。



![](img/209d62a5962f073fced12b33046ca805_39.png)

![](img/209d62a5962f073fced12b33046ca805_40.png)

![](img/209d62a5962f073fced12b33046ca805_41.png)

![](img/209d62a5962f073fced12b33046ca805_42.png)

Have complete control over the keys and their life cycle。

Some RDBMSSs support both symmetric and asymmetric encryption and enable you to configure which to use because of the time and effort it takes the algorithm to process the data。

 any type of encryption and decryion will decrease the performance of your database because asymmetric algorithms generally use longer keys。

 they tend to have greater performance impact than symmetric algorithms， therefore。

 unless you specifically require asymmetric encryption。

 it is often best to use the symmetric algorithms such as AES and DES In fact。

 AES is the recommended method for the earlier PCI， DSSS credit card example。



![](img/209d62a5962f073fced12b33046ca805_44.png)

![](img/209d62a5962f073fced12b33046ca805_45.png)

![](img/209d62a5962f073fced12b33046ca805_46.png)

As well as encrypting data at rest， you should also consider encrypting it in transit。

 that is when it is being transmitted across networks or the internet。



![](img/209d62a5962f073fced12b33046ca805_48.png)

![](img/209d62a5962f073fced12b33046ca805_49.png)

![](img/209d62a5962f073fced12b33046ca805_50.png)

As with data at RE encryption， many RDBMSSs provide this functionality for you some cloud databases encrypt data in transit using transport layer security or TLS protocol while others use secure Sockets layerer or SSL protocol some will encrypt your data by default while others use a configuration setting that you can enable and disable。

 and similarly to addR encryption encrypting data in transit will affect the overall performance of your system。



![](img/209d62a5962f073fced12b33046ca805_52.png)

![](img/209d62a5962f073fced12b33046ca805_53.png)

![](img/209d62a5962f073fced12b33046ca805_54.png)

![](img/209d62a5962f073fced12b33046ca805_55.png)

![](img/209d62a5962f073fced12b33046ca805_56.png)

In this video you learned that data encryption helps make any data that is compromised unusable。

 you can encrypt data at rest or in transit， you use algorithms to encrypt and decrypt data symmetric encryption is easier to use but less secure than a symmetric encryption TDE can simplify encryption setup encryptncion decreases database and transport performance。

 and you can use TLS and SSL to protect data in transit。



![](img/209d62a5962f073fced12b33046ca805_58.png)

![](img/209d62a5962f073fced12b33046ca805_59.png)

![](img/209d62a5962f073fced12b33046ca805_60.png)

![](img/209d62a5962f073fced12b33046ca805_61.png)