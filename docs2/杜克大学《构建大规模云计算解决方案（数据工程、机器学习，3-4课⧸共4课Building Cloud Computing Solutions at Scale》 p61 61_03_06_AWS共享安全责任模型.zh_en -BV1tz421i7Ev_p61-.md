# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p61 61_03_06_AWS共享安全责任模型.zh_en -BV1tz421i7Ev_p61-

![](img/664d9b4af4ac3a1425e96b0bfd4c84a8_0.png)

AWS Cloud security operations are one of the things that's easy to forget about it's in fact。

 though one of the most important things to think about。

 there's been a lot of high profile incidents recently Capital One comes to mind where people weren't actually doing exactly what they needed to do to secure their cloud infrastructure。

 so we're going to talk about that in this next section。To start off with。

 let's talk about something called the shared security model。

 what this is is it's a way of allowing a customer and AWS together to work towards securing their application so at the top here what we have。

Is we have the customer aspect of the cloud security。

 This could be anything from the data or it could be the operating system and then in terms of this line here you have what AWS is responsible for So this would be where the AWS foundational services would be kept so this would be compute storage and all these infrastructure pieces as well。

 things like the regions or maybe the availability zones So what's happening here is that there's a partnership where each one is going to be responsible for where a certain component it's really going to be impossible for AWS to completely decide in the case of let's say customer data here。

How to actually make that secure the operator of the cloud has to work along with AWBS likewise。

 in this case over here， things like the foundational services。

 it's going to be impossible for you to go out and go to the AWS data center and make sure that no one's breaking into it and it's got proper security credentials so these are really a partnership type model。

So let's go to the actual security of the cloud itself。

 so some of the things that AWS is responsible for is the physical security so they're actually going through and making sure that physical access to the data centers are controlled and need-based they're also making sure that the hardware is secure so theyre buying hardware that has the correct configuration also the network configuration that's another thing that AWS is responsible for and then also the virtualization so they're making sure that that is set up in a way that is secure so under this shared security model AWS is operating and managing and controlling these components and this goes all the way from the host OS to the virtualization layer to the physical security of the facilities so a few examples here would be physical security of data would be needbased access 247 security guards two factor。

auuthentation， hardware infrastructure would be things like servers。

 storage devices and other applications， software infrastructure would be the host operating systems。

 the network would be routers， switches， load balancers， firewalls， cabling。

 and then in terms of virtualization， it's making sure that this is actually isolated。

Right that you're not able to access another person's account。

 so this infrastructure is what AWS is responsible for and then in terms of some of these higher level managed services as well。

 that's another component of what AWS can actually manage in these managed services it could be things like the regions。

 the availability zones， the edge edge access the operating systems of firewall configuration。

 so services like the relational database service RDS。

 they're managing the patches on the operating system and so a few different things to consider about this is a managed service like let's say dynamo DB or Redshift or EMR。

Those services， AWS is going to handle a basic security task like the OS and database patching。

 the firewall configuration， disaster recovery。 and then the customers don't have to worry about that。

 So that's actually part of the partnership that you' you're buying into when you're buying this relational and database service。

 for example， and so a few different examples though， is that in terms of patch management。

The AWS is responsible for that， but the customers。

 it's their responsibility to make sure that their guest operating system is patched up right in a virtualization environment for configuration。

 AWS is going to manage the configuration， but customers are going to be responsible again for a guest operating system。

And then in terms of customer specific controls， these would be things like how the application is actually deployed。

 So let's dig into that。 let's go to this next section here and talk about the security of the data in the cloud for the customer。

 So what are some of the things that are responsible So in terms of an application right if you're building an application。

Inside the AWS cloud， you're going to be responsible to make sure that you've defined the passwords correctly and that you have the right roles that access that application。

 likewise that you've had account management that you've set up so that there's a difference between the production environment and let's say the development environment。

And this would be the principle of least privilege。

 so in a cloud infrastructure that's secured by AWS the customers are responsible for anything that they put into the cloud。

 so this would be things like data applications and so a few other things to consider in this is that customers are going to retain the control of the security they choose to implement their own data and operating systems。

 and this really means that this shared security model depends on what AWS services a customer is going to actually use So let's look at an example here of how this could work。

 so let's say that in this example here we've got some accounts and credentials here。

We'll put the accounts up here， and then we've got maybe the ecosystem of you have S3。

You have EC2 instance。And then inside of this EC2 instance as well。

 maybe you have some kind of a database to a DB right here。

 so this is all going to be something that the customer needs to make sure that they secure and so this is going to be things like the application and the security groups right so who has access to the ports that could be exposed in S3 EC2。

And then what are the accountss that actually can access that And then in terms of the global infrastructure。

 So we'll just call this G。 This would be where AWS is going to have the responsibility。

 So this would be the data center。 They're going to control that。

 They're going to make sure that the network is secure。

They're also going to make sure that the virtualization layer is secure as well so these are the breakdown of the different customer responsibilities。

 so the customer is responsible for managing a guest OS， the applications， the security groups。

 but AWS in summary is responsible for protecting that global infrastructure and also it's a best practice for customers to protect the AWS credentials and set up individual accounts so that the principle of least privilege is used。



![](img/664d9b4af4ac3a1425e96b0bfd4c84a8_2.png)

![](img/664d9b4af4ac3a1425e96b0bfd4c84a8_3.png)