# 谷歌《用Python进行IT自动化办公3、4、5、6课（Git、debug、云端、实践）Google IT Automation with Python》中英字 - P132：15_负载均衡.zh_en - GPT中英字幕课程资源 - BV1LW4y1F7XW

![](img/8dd0302e42aa6bacdf643df3ef6d76db_0.png)

In earlier videos， we saw a bunch of different reasons why we might want more than one machine or container running our service。

 For example， we might want to horizontally scale our service to handle more work。

 distribute instances geographically to get closer to our users or have backup instances to keep the service running。

 if one or more of the instances fail。 no matter the reason we use orchestration tools and techniques to make sure that the instances are repeatable。

And once we've set up replicated machines， we'll want to distribute the requests across instances。

We called out earlier that this is where load balancing comes into play。

 Let's take a closer look at the different load balancing methods that we can use。

 A pretty common load balancing technique is round Robbin DNS。

Round Robbin is a really common method for distributing tasks。

 Imagine you're giving out treats at a party。 First。

 you make sure that each of your friends gets one cookie。

Then you give everyone a second serving and so on until all of the treats are gone or your guests say。

 thank you。 they're full。That's the round robin approach to eating all the cookies。Now。

 if we want to translate a URL like Myservice。example。com into an IP address。

 we use the DNS protocol or domain name system。In the simplest configuration。

 the URL always gets translated into exactly the same IP address。

 but when we configure our DNS to use round Robin， it'll give each client asking for the translation a group of IP addresses in a different order。

 The clients will then pick one of the addresses to try to reach the service。If an attempt fails。

 the client will jump to another address on the list。

This load balancing method is super easy to set up。

 you just need to make sure that the Is of all machines in the pool are configured in your DNS server。

 but it has some limitations。First， you can't control which addresses get picked by the clients even if a server is overloaded。

 you can't stop the clients from reaching out to it。On top of that。

 DNS records are cached by the clients and other servers。

 so if you need to change the list of addresses for the instances。

 you'll have to wait until all of the DNS records that were cached by the clients expire。

It's got to be a better way， right， Well， there sure is to have more control over how the loads distributed and to make faster changes。

 we can set up a server as a dedicated load balancer。

This is a machine that acts as a proxy between the clients and the servers。

It receives the requests and based on the rules that we provide。

 it directs them to the selected backend server。Load balances can be super simple or super complex。

 depending on the service needs， say your service needs to keep track of the actions that a user has taken up till now。

In this case， you'll want your load balancer to use sticky sessions。

Using sticky sessions means all requests from the same client always go to the same backend server。

This can be really useful for services that need it。

 but can also cause headaches when migrating or maintaining your service。

 So you need to use it only if you really need it。 Otherwise。

 you'll end up in a really sticky situation。 Another cool feature of load balancers is that you can configure them to check the health of the back end servers。

 Typically， we do this by making a simple query to the servers and checking that the reply matches the expected reply。

😊，If a back end server is unhealthy， the load balancer will stop sending new requests to it to keep only healthy servers in the pool。

 As we've called out a few times already， a cool feature of cloud infrastructure is how easily we can add or remove machines from a pool of servers。

 providing a service。 If we have a load balancer controlling the load of the machines。

 adding a new machine to the pool is as easy as creating the instance and then letting the load balancer know that it can now route traffic to it。

 We can do this by manually creating and adding the instance or when our services under heavy load。

 we can just let the auto scaling feature do it for us。😊，Cool， right， Okay。

 so imagine that you've built out your service with load balancers and you're receiving requests from all over the world。

😊，How do you make sure that clients connect to the servers that are closest to them？

You can use GDNS and GOIP。 These are DNS configurations that will direct your clients to the closest geographical load balancer the mechanism used to route the traffic relies on how the DNS servers respond to requests。

For example， for machines hosted in North America， a DNS server in North America might be configured to respond with the I in。

 you guessed it。 North America， It can be tricky to set this up on your own。

 but most cloud providers offer it as part of their services。

 making it much easier to have a geographically distributed service。

 Let's take this one step further。 There are some providers dedicated to bringing the contents of your services as close to the user as possible。

These are the content delivery networks or CDNs。They make up a network of physical hosts that are geographically located as close to the end user as possible。

This means that CN servers are often in the same data center as the user's Internet service provider。

 CdNs work by cash and content super close to the user。 When a user requests， say a cat video。

 It's stored in the closest CN server that way， when a second user in the same region requests the same cat video。

 it's already cache in a server that's pretty close and it can be downloaded extra fast。

Because no one should have to wait for their cat videos to load。



![](img/8dd0302e42aa6bacdf643df3ef6d76db_2.png)

You now know a lot of stuff about load balancing。Up next。

 we'll talk about another aspect of dealing with cloud services。

 how to deploy changes safely to our cloud service。

