# 谷歌《用Python进行IT自动化办公3、4、5、6课（Git、debug、云端、实践）Google IT Automation with Python》中英字 - P119：2_云服务概览.zh_en - GPT中英字幕课程资源 - BV1LW4y1F7XW

![](img/ad0ae912121097c9e19cdb432bf8b96c_0.png)

So when we say that a service is running in the cloud， what do we actually mean？

It has nothing to do with those white， fluffy things in the sky。

 It simply means that the service is running somewhere else。

 either in a data center or in other remote servers that we can reach over the Internet。

These data centers house a large variety of machines。

 Different types of machines are used for different services。 For example。

 some machines may have a local solid state drive or SSD for increased performance。

 while others may rely on virtual drives mounted over the network to lower costs。

 Cloud providers typically offer a bunch of different service types。

The ones used most by users are in the software as a service category。

 Software as a service or Saas is when a cloud provider delivers an entire application or program to the customer。

If you choose a cloud email solution like Gmail， a cloud storage solution like Dropbox or a cloud productivity suite like Microsoft Office 365。

 there are only a small number of options for you to select or customize。

 The cloud provider manages everything related to the service for you。

 including deciding where it's hosted， ensuring the service has enough capacity to serve your needs。

 performing backups frequently and reliably and a lot more。

 There's a lot of software being offered as a service by many different cloud providers or other Internet companies。

 But， of course， not all of our needs can be solved by prepackaged software。

 Sometimes we need to develop our own。😊，For some of the components of our software。

 we might choose to use platform as a service platform as a service or pass is when a cloud provider offers a preconfigured platform to the customer。

When we say platform here， it can be a bit confusing because there are lots of different platforms that exist under a pass model。

 Let's check out an example to understand this better。 Say you need an S。

 Q L database to store some of your applications' data。

You could choose to host the database in your own hardware To do this。

 you'd need to install an operating system on that computer and then install the SQL software on top of the chosen OS。

This requires a basic understanding of all these different pieces just to get the database running。

There's a bunch of things that could go wrong。 And even if you can eventually solve all of them。

 it could take a while。 Instead， you could decide to use a cloud provider that offers an SQL database as a service。

That way， you can just focus on writing SQL queries and using the platform。

And let the cloud provider take care of the rest。 There's a bunch of different platforms offered as a service by cloud providers。

 But， of course， they are unlikely to cover all of your needs。

 If you need a high level of control over the software you're running and how it interacts with other pieces in your system。

 you might want to choose infrastructure as a service。

 infrastructure as a service or IAA is when a cloud provider supplies only the barebones computing experience。

Generally， this means a virtual machine environment and any networking components needed to connect virtual machines。

The cloud provider won't care what you're using the VMs for。 you could use them to host a web server。

 a mail server， your own SQL database with your own configuration settings。

 or a whole lot more possibilities running your IT infrastructure on the cloud providers IAA offering is a very popular choice。

And there's a lot of different providers out there。

 big and small that offer a service where you can run virtual machines in their cloud。

Some IAA products include Amazon's EC2， Google Compute Engine， and Microsoft Azure Comp。 Now。

 no matter the service model and the provider you use， when you set up cloud resources。

 you'll need to consider regions。 A region is a geographical location containing a number of data centers。

 regions contain zones and zones can contain one or more physical data centers。

If one of them fails for some reason， the others are still available and services can be migrated without notably affecting users。

 Large cloud providers usually offer their services in lots of different regions around the world。

Generally， the region and zone you select should be closest to your users。

The farther you uses are from the physical data center， the more latency they may experience。

This might sound a bit strange， but imagine if you were on vacation overseas。

 You might notice that your bank website loads a little slower。

That's why it's common practice to locate data centers close to where users actually live， work。

 and bank。Latency isn't the only factor to take into account when selecting a region or zone。

 Some organizations require their data to be stored in specific cities or countries for legal or policy reasons。

And if your service uses other services as dependencies。

 it's a good idea to host the service physically close to its dependencies。 For example。

 if a mail server requires a database server to send an email。

 it makes sense to host the database server and the mail server in the same zone。

 we called out earlier that Quicklabs is a service using cloud infrastructure。😊。



![](img/ad0ae912121097c9e19cdb432bf8b96c_2.png)

So what kind of cloud service does QuickLbs use？QuickClabs uses infrastructure as a service。

The VMs get provisioned with just the OS， and the lab automation then deploys any additional files and software into the OS。

 Up next， we'll talk about how we can use the services offered by cloud providers to help us scale our applications。

