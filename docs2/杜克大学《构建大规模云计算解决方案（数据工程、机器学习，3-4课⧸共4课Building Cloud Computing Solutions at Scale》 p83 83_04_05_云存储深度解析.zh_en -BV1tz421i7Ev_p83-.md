# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p83 83_04_05_云存储深度解析.zh_en -BV1tz421i7Ev_p83-

![](img/8a454d4616b1116291fc5f73367f1050_0.png)

So to start with today， I wanted to talk about cloud storage and in particular。

 Cloud storage is a very fascinating topic because of the capabilities that are available when you use cloud providers。

And probably the number one way to think about cloud storage is this concept of infinity。

 And it means that you have CPU that's effectively infinite。 You have the disko。

 that's effectively infinite。And then you also have the storage that's effectively infinite。

 and so as a result， you can build really sophisticated solutions by using cloud companies。

In particular， probably the central component to all cloud companies is their data lake。

And in the data lake， this is where you would build， let's say， a machine learning pipeline。

We could build a ML pipeline inside of a data lake。

 we also could build out just storage for maybe data engineering。

If you're going to build maybe a business analytics pipeline。You also could do。Maybe web hosting。

 that's another thing you can do with a data lake is you could put a statically hosted website。

 maybe using a technology like Hugo， which is a really good static hosting technology。

And all of this can be done automatically。These pipelines can be set up because of the fact that things will really grow up and down according to the requests。

And as a result， it's flexible so you you can think of it as something that's always there。

 you can build out lots of different services with it and the other great thing about cloud storage is in the case of AWS as one example there are 11 nines of reliability So if this means in practice is that it's probably around I think10 milliseconds of downtime per year so really the information that's available here is always going to be available because of how much redundancy a few other things that are probably good to point out as well。

If you take most of the cloud providers， they also have different pricing as well。

 so in terms of pricing。What you'll see is that if you wanted something that had。

Maybe infrequently access data， so I'll just say IA。

You can pay less money for certain pieces of storage。

 so it's almost like putting your personal possessions into a storage container somewhere。

 it'll be less money because you don't have access to it more frequently it's the same thing with data you can put it into these different bins and even as well。

What you can do is you can actually archive it in the case of 80WS。

 they have something called Glacier and you can archive the data。

 so really the way that you build complex systems or globally available social networks or machine learning companies or AI companies is to first start with the data lake and starts to build these capabilities on top of it。

The next component of cloud storage that I'll talk about are some of the things that are available in terms of cloud storage。

 so what are some of the offerings。A really good example of this would be AWS。

 they probably have the most offerings。And they have object storage。

And that's really the backbone of what the data lake is。And in terms of object storage。

 what you would do is put in files and pictures and things like that， so we'll just say file。Maybe。

A image， videos。And then another offering they have is databases and they have many different types of databases as well。

Which can be confusing at first， but what is useful about having so many different databases is that you can pick maybe several databases for your project so you could pick。

 let's say， a traditional relational database。Or you could pick a key value database。

A good example of that would be dynamoDB， is there a key value database。

 and I'll show that in a little bit how useful it is to build things with dynamoDB。

Another option could be a graph database， many problems fit a graph database really nicely。

 so for example social network analysis can work really well in a graph database there's also search engines。

 they have elastic search on AWS so there's many different types of database offerings and you can in many cases pick several of them and use them at once on a particular project Another thing they have is ML platforms。

And so the ML platforms。Are really designed to sit on top of the data lake and also version assets。

 and so they'll version the model itself。And also the data that was used so you can detect things like。

Data drift。Additional to that。Another thing you can do。With in terms of the storage offerings。Is。

Use these ETL systems。And an ETL stands for extract。呃。Tran transferfer and load。

And what this means is that you can actually take some kind of a pipeline and build it。

To do operations in a company。 And this is really a common。Workflow。

 if you were going to build something for business analytics or for maybe a data engineering aspect of a company is to automatically clean the data。

Put it into a format that can be useful and on in particular， let's say the AWS platform。

 they have Quicksite。Whi is a visualization tool that works with ETL products。

 they also have glue and glue is a automatic ETL pipeline。And then there's also。

A tool called Athena and Athena can query the。The catalogs that are created by glue。

 so it can go into， let's say， Amazon S3。Keep track of everything that's in there， and then Athena。

 you can write SQL queries and get access to it。So。

Not only are there the low levell primitives in the cloud。

 but there's lots of different offerings that are available。

 and I guess the other two big ones that aren't on here yet are in terms of the servers themselves。

 so let's just take EC2 for example， on EC2 there's really a couple primary types of storage。

That you would use， one is called EBS。And EBS stands for Elastic block storage and elasticastic block storage you can actually tell it you want to have a specific amount of iOs and what's useful about that is that you can do high performance computing by specifically mounting a volume and telling it。

 let's say you want to have 10，000 iOs per second so you can。

Unlike a laptop or a workstation where you have a fixed capacity of disk IOs。

 you can have almost an unlimited amount of disk IOs using their block storage system。Now。

 the block storage system won't be able to be accessed by a second virtual machine。

 So the other solution that's available is something called EFS and EFS is really useful in that。

You can mount。This shared network file system on multiple machines and these multiple machines can can do things like have a common。

source code that they use to distribute work， it could also share data between jobs。

 it can grow the discoo as well according to the size。So in terms of offerings in the cloud。

 I think EFS is one of the more interesting ones， and so let me just dive into that briefly and talk about a particular workflow that you could use with the elasticastic file system。

So the elastic file system。Is been。It's really a rebranding of the word NFS， and NFS。

 the network file system has been around for quite some time。And I believe it was created by the Sun。

Company which used to have an operating system。That was called Ceris and the tagline at the time。

 I believe was called the network is the computer。So we'll say the network is the computer。

And what was neat about this？Is that。With something like a network operating system。

 you can do some really powerful workflows and one example of this would be that you could have this network file system that again could go up in the storage automatically。

And it also can automatically get faster because as you grow more storage。

 it'll increase the diskcoo to accommodate that， and then also it can auto archive。

Filees that aren't used frequently。 So you'll pay less money for it。

 So it has these really advanced capabilities to it。 And then what it。

 what it means is in terms of a workflow is if you launch a spot instance， for example。On AWS。

What can what you can do is actually mount centrally， we'll just say these are spot instances。

 you could have lots of them。A cluster， maybe you could have 1。

000 spot instances launched to do some work， and then all of them have the same mountpoint and then because they have the same mount point。

 this really simplifies many things that simplifies the deployment of software。

 there really is no deployment necessary because of the fact that you just mount， let's say。

 a script directory here。And then inside of that script directory， you can actually run。You know。

 whatever it is that you need to do， lets let's say it's a computer vision job or a machine learning job or some other operation。

 you can do that automatically because the code' is always available。

 likewise when the job is complete， the data can also be written to this network file system。

This can be really useful in that there isn't some other process like。

A big data system that has to be spun up。 It's all implicit to this system。

 So the EFs really is or the the network file system。

Really is a useful feature that is becoming more and more prevalent inside of workflows in the cloud。

 and in particular， there's a new workflow。Besides just spot instances。

 you can also tell serverless machines now， I believe this is a new component on AWS that they can mount the same file storage system as well。

 so what's helpful about that is that you can have these stateless functions that can write their data transparently to elastic file system。



![](img/8a454d4616b1116291fc5f73367f1050_2.png)

![](img/8a454d4616b1116291fc5f73367f1050_3.png)