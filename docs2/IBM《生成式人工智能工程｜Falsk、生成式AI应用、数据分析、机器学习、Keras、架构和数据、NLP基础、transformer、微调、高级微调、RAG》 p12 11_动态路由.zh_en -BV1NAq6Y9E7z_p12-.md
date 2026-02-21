# IBM《生成式人工智能工程｜Falsk、生成式AI应用、数据分析、机器学习、Keras、架构和数据、NLP基础、transformer、微调、高级微调、RAG》 p12 11_动态路由.zh_en -BV1NAq6Y9E7z_p12-

Welcome to Dynamic Routes。After watching this video。

 you will be able to describe how to call an external API in Flask and describe how to pass parameters to routes in Flask。



![](img/a340d947f491c24ab6874605b1f9e155_1.png)

![](img/a340d947f491c24ab6874605b1f9e155_2.png)

Let's look at an example of how you might call an external API in flask。 Now。

 the easiest way is to use the Python requestquests library。

 You can return the Jason from the external API to your client。 However。

 you can also process the results before sending them back to your client。 Here is an example。 First。

 you import flask and request modules。 The code here assumes you have already installed the request library。

 You can define your route next。 use the requests library to request the open library API and search for information for the author。

 Michael Creightton。 Now， store the response in a variable called Res。

 Then check if the response status code from the open library API is 200。 If the response is 200。

 you return the Jason to the client。 If the response happens to be 404。

 you send a message something went。

![](img/a340d947f491c24ab6874605b1f9e155_4.png)

Wrong。And finally， in this hypothetical case， if the response is anything else。

 you return with a status of 500 and a message server error。



![](img/a340d947f491c24ab6874605b1f9e155_6.png)

When developing REful APIs， you can send some resource ID as part of the request URL For example。

 you want to create an endpoint that returns book information by International Standard Book number or ISBN。

 but instead of hard coding the ISBN， you want the client to send it as part of the URL Flask provides dynamic routing for this purpose。



![](img/a340d947f491c24ab6874605b1f9e155_8.png)

Now let's look at a concrete example， add the variable called ISBN as a dynamic part of the URL。

 then pass this variable to the Open Library API， the result is then sent back to the client。



![](img/a340d947f491c24ab6874605b1f9e155_10.png)

Faskask also allows you to set the parameter type The framework uses this information to validate incoming requests。

 For example， you can create an endpoint of terminals and SFO to get the number of terminals at the San Francisco airport this route decorator triggers if the user sends a string at the end of the URL Similarlyly。

 in the previous example， you can give ISBN to be a number。



![](img/a340d947f491c24ab6874605b1f9e155_12.png)

Here are some other examples of parameter types in flask。While string。

 int and float are simple parameters， you can also use complex ones like PA to indicate a webpath or a folder path。

 or universal unique Ientifier or UUID to indicate a unique ID like globally unique identifier or GUID。



![](img/a340d947f491c24ab6874605b1f9e155_14.png)

Here is an example of UUI。

![](img/a340d947f491c24ab6874605b1f9e155_16.png)

You can create an endpoint network that has a specific UUI to get information about the network。

 You can write this code where the route expects a variable UUID of type UUID。

 the UUI is passed to the method as an argument and you return a success message if the UUI is found。

 otherwise， you return an error code with an appropriate message。



![](img/a340d947f491c24ab6874605b1f9e155_18.png)

In this video you learned that you can parse the request object to get query parameters。

 body and other arguments， you can set status on response objects before sending a response back to the client。

 and you can use dynamic routes to create restful end points。



![](img/a340d947f491c24ab6874605b1f9e155_20.png)

。

![](img/a340d947f491c24ab6874605b1f9e155_22.png)