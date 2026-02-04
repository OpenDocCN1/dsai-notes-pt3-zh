# IBM应用人工智能（从0开始搭建AI机器人）｜IBM Applied AI （中英字幕） - P104：14_动态路由.zh_en - GPT中英字幕课程资源 - BV1p64y1H7LM

![](img/dff7d4f53b7a4f050e60939ae8862dd2_0.png)

Welcome to Dyna Routes。After watching this video， you will be able to describe how to call an external API in Flask and describe how to pass parameters to routes in Flask。



![](img/dff7d4f53b7a4f050e60939ae8862dd2_2.png)

![](img/dff7d4f53b7a4f050e60939ae8862dd2_3.png)

![](img/dff7d4f53b7a4f050e60939ae8862dd2_4.png)

Let's look at an example of how you might call an external API in flask。 Now。

 the easiest way is to use the Python requestquests library。

 You can return the J from the external API to your client。 However。

 you can also process the results before sending them back to your client Here is an example。 First。

 you import flask and request modules。 The code here assumes you have already installed the request library。

 you can define your route next。 Use the requests library to request the open library API and search for information for the author Michael Cightton。

 Now store the response in a variable called Res。 Then check if the response status code from the open library API is 200。

 If the response is 200， you return the Jason to the client If the response happens to be 404。

 you send a message something went。

![](img/dff7d4f53b7a4f050e60939ae8862dd2_6.png)

![](img/dff7d4f53b7a4f050e60939ae8862dd2_7.png)

![](img/dff7d4f53b7a4f050e60939ae8862dd2_8.png)

![](img/dff7d4f53b7a4f050e60939ae8862dd2_9.png)

![](img/dff7d4f53b7a4f050e60939ae8862dd2_10.png)

![](img/dff7d4f53b7a4f050e60939ae8862dd2_11.png)

![](img/dff7d4f53b7a4f050e60939ae8862dd2_12.png)

![](img/dff7d4f53b7a4f050e60939ae8862dd2_13.png)

![](img/dff7d4f53b7a4f050e60939ae8862dd2_14.png)

![](img/dff7d4f53b7a4f050e60939ae8862dd2_15.png)

![](img/dff7d4f53b7a4f050e60939ae8862dd2_16.png)

Wrong。And finally， in this hypothetical case， if the response is anything else。

 you return with a status of 500 and a message server error。



![](img/dff7d4f53b7a4f050e60939ae8862dd2_18.png)

![](img/dff7d4f53b7a4f050e60939ae8862dd2_19.png)

When developing REful APIs， you can send some resource ID as part of the request URL For example。

 you want to create an endpoint that returns book information by international Standard book number or ISBN。

 but instead of hard coding the ISBN， you want the client to send it as part of the URL Flask provides dynamic routing for this purpose。



![](img/dff7d4f53b7a4f050e60939ae8862dd2_21.png)

![](img/dff7d4f53b7a4f050e60939ae8862dd2_22.png)

![](img/dff7d4f53b7a4f050e60939ae8862dd2_23.png)

![](img/dff7d4f53b7a4f050e60939ae8862dd2_24.png)

Now let's look at a concrete example， add the variable called ISBN as a dynamic part of the URL。

 then pass this variable to the Open Library API， the result is then sent back to the client。

Fask also allows you to set the parameter type The framework uses this information to validate incoming requests。

 For example， you can create an endpoint of terminals and SFO to get the number of terminals at the San Francisco airport this route decorator triggers if the user sends a string at the end of the URL Similarlyly in the previous example。

 you can give ISBN to be a number。

![](img/dff7d4f53b7a4f050e60939ae8862dd2_26.png)

![](img/dff7d4f53b7a4f050e60939ae8862dd2_27.png)

![](img/dff7d4f53b7a4f050e60939ae8862dd2_28.png)

![](img/dff7d4f53b7a4f050e60939ae8862dd2_29.png)

![](img/dff7d4f53b7a4f050e60939ae8862dd2_30.png)

Here are some other examples of parameter types in flask。



![](img/dff7d4f53b7a4f050e60939ae8862dd2_32.png)

While string， int， and float are simple parameters。

 you can also use complex ones like PA to indicate a webpath or a folder path。

 or universal unique Ientifier or UUID to indicate a unique ID like globally unique identifier or GU ID。



![](img/dff7d4f53b7a4f050e60939ae8862dd2_34.png)

![](img/dff7d4f53b7a4f050e60939ae8862dd2_35.png)

![](img/dff7d4f53b7a4f050e60939ae8862dd2_36.png)

Here is an example of UUID。 You can create an endpoint network that has a specific UUI to get information about the network。

 You can write this code where the route expects a variable UUID of type UUID The UUI is passed to the method as an argument。

 and you return a success message if the UUI is found， otherwise。

 you return an error code with an appropriate message。



![](img/dff7d4f53b7a4f050e60939ae8862dd2_38.png)

In this video you learned that you can parse the request object to get query parameters。

 body and other arguments， you can set status on response objects before sending a response back to the client。

 and you can use dynamic routes to create restful end points。



![](img/dff7d4f53b7a4f050e60939ae8862dd2_40.png)

![](img/dff7d4f53b7a4f050e60939ae8862dd2_41.png)

![](img/dff7d4f53b7a4f050e60939ae8862dd2_42.png)