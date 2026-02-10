# IBM数据工程专业证书第3课：《Python数据工程项目课程（IBM）》python-project-for-data-engineering - P5：4_可选 rest api http 请求.zh_en - GPT中英字幕课程资源 - BV1xz4y1W7Gb

![](img/6fce607ac09d6e177cf3638bdf4c9575_0.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_1.png)

In this video we will discuss the HTTP protocol using the Requests library。

 a popular method for dealing with the HTTP protocol in Python。

 we will review Python Library requests for working with the HTTP protocols。

 and we will provide an overview of get requests and post requests。



![](img/6fce607ac09d6e177cf3638bdf4c9575_3.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_4.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_5.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_6.png)

Let us review the request module in Python。 This is one of several libraries。

 including HtTP Lib and URL Lib that can work with the HtTP protocol。

 Res is a Python library that allows you to send HtTP s 1。1 requests easily。

 We can import the library as follows。 You can make a get request via the method get to www。

 IBM do com。 We have the response object R。 This has information about the request like the status of the request。

 We can view the status code using the attribute status underscore code， which is 200 for okay。

 You can view the request headers。

![](img/6fce607ac09d6e177cf3638bdf4c9575_8.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_9.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_10.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_11.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_12.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_13.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_14.png)

You can view the request body in the following line as there is no body for a get request。

 we get a nun。 You can view the HTTP response header using the attribute headers。

 This returns a Python dictionary of HTTP response headers。 We can look at the dictionary values。



![](img/6fce607ac09d6e177cf3638bdf4c9575_16.png)

We can obtain the date the request was sent by using the key date。

 The key content type indicates the type of data using the response object R。

 we can also check the encoding。

![](img/6fce607ac09d6e177cf3638bdf4c9575_18.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_19.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_20.png)

As the content type is text or HTML， we can use the attribute text to display the HTML in the body。

 we can review the first 100 characters you can also download other content， see the lab for more。



![](img/6fce607ac09d6e177cf3638bdf4c9575_22.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_23.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_24.png)

You can use the get method to modify the results of your query， for example。

 retrieving data from an API in the lab， we will use httPB。org。

 a simple httP request and response service。

![](img/6fce607ac09d6e177cf3638bdf4c9575_26.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_27.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_28.png)

We send a get request to the server， like before we have the base URL in the route。

 We append slash get。 This indicates we would like to perform a get request。

 This is demonstrated in the following table。

![](img/6fce607ac09d6e177cf3638bdf4c9575_30.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_31.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_32.png)

After get is requested， we have the query string This is part of a uniform resource locator or URL。

 and this sends other information to the web server The start of the query is a question mark followed by a series of parameter and value pairs。

 as shown in the table below。

![](img/6fce607ac09d6e177cf3638bdf4c9575_34.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_35.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_36.png)

The first parameter name is name， and the value is Joseph。



![](img/6fce607ac09d6e177cf3638bdf4c9575_38.png)

The second parameter name is ID， and the value is 1，2，3。

 Each pair parameter and value is separated by an equal sign。

 The series of pairs is separated by the Ampersand。 Let us complete an example in Python。



![](img/6fce607ac09d6e177cf3638bdf4c9575_40.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_41.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_42.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_43.png)

We have the base URL with get appended to the end to create a query string。

 we use the dictionary payload， the keys are the parameter names and the values are the value of the query string。

 then we pass the dictionary payload to the parameter's parameter of the get function。



![](img/6fce607ac09d6e177cf3638bdf4c9575_45.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_46.png)

We can print out the URL and see the name and values。

 we can see the request body as the info is sent in the URL， the body has a value of none。

 we can print out the status code。

![](img/6fce607ac09d6e177cf3638bdf4c9575_48.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_49.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_50.png)

We can view the response as text and we can look at the key content type to look at the content type as the content content type is in the J。

 we format it using the method Jason， It returns a Python dit。

 The key args has the name and values for the query string。 Like a G request。

 a post request is used to send data to a server， but the post request sends the data in a request body。

 not the URL。 in order to send the post request in the URL， we change the route to post。

 This endpoint will expect data， and it is a convenient way to configure an HtTP request to send data to a server。

 We have the payload dictionary to make a post request we use the post function。

 The variable payload is passed to the parameter data。



![](img/6fce607ac09d6e177cf3638bdf4c9575_52.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_53.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_54.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_55.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_56.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_57.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_58.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_59.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_60.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_61.png)

Comparing the URL using the attribute URL from the response object of the get and post request。

 we see the post request has no name or value pairs in its URL。

 We can compare the post and get request body， we see only the post request has a body。

 and we can view the key form to get the payload。

![](img/6fce607ac09d6e177cf3638bdf4c9575_63.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_64.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_65.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_66.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_67.png)

![](img/6fce607ac09d6e177cf3638bdf4c9575_68.png)