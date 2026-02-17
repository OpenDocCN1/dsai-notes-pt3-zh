# IBM《生成式人工智能工程（AI入门、生成式AI入门、提示工程、Python）｜IBM Generative AI Engineering》中英字幕 - P71：17_简单API（第1部分）.zh_en - GPT中英字幕课程资源 - BV1MfqzY4Eyg

![](img/5f90714cbd2e73566aa0b15e6b5b04d0_0.png)

In this video we will discuss application program interfaces or APIs for short。

 specifically we will discuss what an API is API libraries and rest APIs including request and response and an example with Pycoin Gego。

 an API lets two pieces of software talk to each other， for example。

 you have your program you have some data and you have other software components。

 You use the API to communicate with other software via inputs and outputs。

 just like a function you don't have to know how the API works。

 just its inputs and outputs Padas is actually a set of software components。

 much of which are not even written in Python You have some data you have a set of software components。

 We use the pandas API to process the data by communicating with the other software components。



![](img/5f90714cbd2e73566aa0b15e6b5b04d0_2.png)

![](img/5f90714cbd2e73566aa0b15e6b5b04d0_3.png)

![](img/5f90714cbd2e73566aa0b15e6b5b04d0_4.png)

![](img/5f90714cbd2e73566aa0b15e6b5b04d0_5.png)

![](img/5f90714cbd2e73566aa0b15e6b5b04d0_6.png)

Let us clean up the diagram when you create a dictionary。

 then create a panda's object with the data frame constructor in API lingo this is an instance the data in the dictionary is passed along to the panda's API you then use the data frame to communicate with the API When you call the method head the data frame communicates with the API display the first few rows of the data frame When you call the method mean the API will calculate the mean and return the values。



![](img/5f90714cbd2e73566aa0b15e6b5b04d0_8.png)

Rest APIpis are another popular type of API。 They allow you to communicate through the internet。

 letting you take advantage of resources like storage， access more data。

 artificial intelligence algorithms and much more。 The R stands for representational The S for state and T for transfer。

 in rest APIpis， your program is called the client The API communicates with a web service you call through the Internet。

 There is a set of rules regarding communication input or request and output or response。

 Here are some common terms。 you or your code can be thought of as a client。

 The Web service is referred to as a resource。 The client finds the service via an endpoint。

 We will review this more in the next section。 The client sends requests to the resource and the resource Web service sends a response to the client H TTP methods are a way of transmitting data over the Internet。



![](img/5f90714cbd2e73566aa0b15e6b5b04d0_10.png)

![](img/5f90714cbd2e73566aa0b15e6b5b04d0_11.png)

![](img/5f90714cbd2e73566aa0b15e6b5b04d0_12.png)

Tell the rest APIs what to do by sending a request The request is usually communicated via an HTTP message the HTTP message usually contains a file This contains instructions for what operation we would like the service to perform This operation is transmitted to the web service via the Internet and the service performs the operation in a similar manner the web service returns a response via an HTTP message where the information is usually returned via a file and this information is transmitted back to the client cryptocurrency data is excellent to use in an API because it is constantly updated and is vital to cryptocurrency trading We will use the Pcoin Ge Python client or raper for the Co Ge API updated every minute bycoin Ge We use the wrappper or client because it is easy to use so you can focus on the task of collecting data We will also introduce panda's time series。



![](img/5f90714cbd2e73566aa0b15e6b5b04d0_14.png)

![](img/5f90714cbd2e73566aa0b15e6b5b04d0_15.png)

Functions for dealing with time series data using Pycoin Gecho to collect data is simple。

 All we need is to install and import the library， then create a client object。

 and finally use a function to request our data In this function we are getting data on Bitcoincoin in US dollars for the past 30 days In this case。

 our response is adjacent file expressed as a python dictionary of nested lists， including price。

 market cap and total volumes which contain the Unix timestamp and the price at the time。

 We are only interested in price So that is what we will select using the key price to make things simple。

 we can convert our nested list to a data frame with the columns timestamp and price。

 It is difficult to understand the column timestamp We will convert it to a more readable format using the pandas function to underscore date time using this to underscore date time function。



![](img/5f90714cbd2e73566aa0b15e6b5b04d0_17.png)

![](img/5f90714cbd2e73566aa0b15e6b5b04d0_18.png)

Create readable time data。 The input is the timestamp column unit of time is set to milliseconds。

 We append the output to the new column date。 Now we want to create a candlestick plot to get the data for the daily candlesticks。

 We will group by the date to find the minimum maximum first and last price of each day。 Finally。

 we will use plotly to create the candlestick chart and plot it。 Now。

 we can view the candlestick chart by opening the HTML file and clicking trust HTML in the top left of the tab。

 It should look something like this。

![](img/5f90714cbd2e73566aa0b15e6b5b04d0_20.png)

![](img/5f90714cbd2e73566aa0b15e6b5b04d0_21.png)

![](img/5f90714cbd2e73566aa0b15e6b5b04d0_22.png)

![](img/5f90714cbd2e73566aa0b15e6b5b04d0_23.png)