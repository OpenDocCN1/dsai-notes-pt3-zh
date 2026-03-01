# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p64 64_03_09_静态与传输加密.zh_en -BV1tz421i7Ev_p64-

![](img/e53a3c51d43458c52b4c89c4b02bd492_0.png)

Let's talk through an important set of concepts regarding encryption First there's transit this is one of the more important concepts in encryption in that if you're a user and you're accessing a website let's say it's a bank or your communications between your personal computer and the bank's website protected and so if someone intercepts that let's say you're at a cafe and you're logging in via your laptop to the wireless network if the communication between the bank and your personal laptop or encrypted。

 it doesn't matter if someone intercepts your network traffic so that's what it stands for when you talk about in transit encryption and this is really like a fundamental of encryption is that all communication between one service and another should be encrypted so that the information between that pipe isn't able to be intercepted。

you'll typically see this with websites with mobile apps， in general。

 this is another thing that you'll see is called HTTPS。

That means that the webbased website is encrypted from your laptop to， let's say the public URL。

 Now the second concept is at rest。 So what does this mean well。

 let's say that the data does get to the website and it gets stored somewhere in the cloud Well what about that storage mechanism is the data itself encrypted and let's say that later someone breaks in and they get access to this file and and they steal it。

 they're running away with it， the bad guy is is stealing the data， if the data has been encrypted。

 it doesn't matter。 it's like a safe that's been locked and there's no way to open up the safe。

 the data is been encrypted at rest and so this is why this is the second industry best practice here which is not only do you need to encrypted in transit but when it's stored somewhere and needs to be encrypted so that if there is an accident in a leak of the data you can rest。

that there isn't a way to get to decrypt the data。 Now， the third mechanism。

That's a little bit subtle that's often not talked about is this idea of encryption keys and so just like in the case of the file that's stored somewhere and it's accidentally or intentionally stolen。

Well， what happens with encryption keys is that they are the only way to unencrypt the data。

 And so this is really important for an organization that's looking at doing encryption。

 is that you may feel like， hey， I've got the first one done。 we always use HTTPS。

' we're doing industry best practice。 And then maybe you're also doing you know the second one here。

 know you're always doing encrypting the data， But there's a hidden secret here。

 which is who has the keys to encrypt the data and who has the keys to unencrypt the data。

 And if you're not using the concept of principle of least privilege。

Where only the people that should have access to the data have access to it。

 and to the encryption keys， then you could also be exposing yourself to loss。

 so you may think just because it's encrypted that you're safe。

 but it also depends on who are the people that have access to the keys。

 and so these also need to be very important considerations when you're using encryption in an organization。



![](img/e53a3c51d43458c52b4c89c4b02bd492_2.png)

![](img/e53a3c51d43458c52b4c89c4b02bd492_3.png)