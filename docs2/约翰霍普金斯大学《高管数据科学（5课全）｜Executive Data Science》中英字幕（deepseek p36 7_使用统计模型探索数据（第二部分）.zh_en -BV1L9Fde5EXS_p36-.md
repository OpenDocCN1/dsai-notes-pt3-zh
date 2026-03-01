# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p36 7_使用统计模型探索数据（第二部分）.zh_en -BV1L9Fde5EXS_p36-

This lecture here is just another quick example of how to use statistical models to explore your data and to develop a sketch of your solution。



![](img/9c13d6a49e5bccdb5444797056376a25_1.png)

![](img/9c13d6a49e5bccdb5444797056376a25_2.png)

So this example looks at fitting a linear model to some data and the data that we're going to use is ozone and temperature data from New York City for the years 1999 this data comes from the national morbidity and mortality air pollution study which is an air pollution study that I was heavily involved with so the data that we've got here is just daily levels of 24 hour average temperature and 24 hour average ozone levels for the year 1999 in New York and the basic question that we're interested in asking here is how our ambient temperature levels related to ambient ozone levels in New York City now just a couple things about how ozone works first of all the development of ozone in the air depends a lot on the amount of sunlight that's available so with lots of sunlight have higher temperatures and then otherwise similar days with lower temperatures and so similarly cloudy days tend to have lower temperature and less ozone so the basic idea is that we expect days with higher temperature to have higher ozone levels。



![](img/9c13d6a49e5bccdb5444797056376a25_4.png)

![](img/9c13d6a49e5bccdb5444797056376a25_5.png)

But this is kind of an indirect relationship。 What we're really doing is we're using temperature as a proxy for the amount of sunlight that's available because we don't really actually have any data on sunlight Okay so we're expecting this kind of positive correlation between temperature and ozone in New York City Now the simplest model that we can use to describe this relationship that we expect is a linear model right So now the question we should be asking right now is what does a linear model look like So remember we want to set expectations before we start looking at the data So the easiest way to do that is to draw a fake picture。

😊。

![](img/9c13d6a49e5bccdb5444797056376a25_7.png)

So this picture shows two simulated variables with the linear relationship。

 Okay there's no actual data here。 We just simulated it on the computer so you can see that the data increased from the left to the right like a line。

 but with some scatter around it。 And furthermore， if you choose any point on the blue line there are roughly the same number of points above the line as they are below it so so we think of the line is being kind of unbiased right so there's going to be a deviation from the line is equally likely to be above or below it。

 So this is the picture that we expect to see when we look at the data。

 So it's important that we kind of set these expectations before we look at the data So we know whether we'rere kind of right or wrong or far off or pretty close to the mark。

So here's the actual data for New York in 1999 with the fitted linear regression line overlaid on top so the first question you want to ask yourself was how does it compare to what we were expecting from the previous picture now one thing that we can see is that temperature and ozone are in fact increasing together when temperature is higher at ozone does tend to be higher and when temperatures lower ozone tends to be lower but there are some deviations from what we might expect from what we saw in the previous picture in particularly if you look at around 85 degrees in temperature if you look at where the blue line is around that point。

 you'll see that most of the data points happen to be above the line there aren't that many data points below the line right around that neighborhood then again if you look at the temperature 70 degrees and where the blue line is there。

 you'll see that most of the points are below the line actually and there aren't that many points above the line So at around 85 degrees what we see is that that the blue line are model。

 the linear model is kind of biased downwards and at 70 degree point mark。

Your model is actually biased upwards。 We we're tending to kind of predict too high for what the ozone level actually is。

 So what we see is that the model kind of captures the general trend of kind of increasing temperature and increasing ozone。

 but it tends to be biased in certain within certain ranges of temperature。

 So it's not clearly not a perfect model。

![](img/9c13d6a49e5bccdb5444797056376a25_9.png)

So the observed pattern from the data seems to suggest that the relationship between ozone and temperature is actually kind of flat up until about the point where we hit like 70 degrees 72。

73 degrees。 then there's a sharp increase in ozone with every additional degree of temperature and so this suggests that maybe the relationship is nonlinearar and so we can revise our expectation for what the relationship should look like look like to be this kind of nonlinearar rather than our original expectation of a linear relationship and so the way that we can check that is by using a nonlinearar smoother。

 here's some data with the low S smoother， which is a flexible smoother that can kind of capture a lot of different kinds of smooth trends so what we can see here is that from the blue line there's a sharp increase in ozone after about 75 degrees and then maybe around 85 degrees or so there's some suggestion of leveling off of the relationship。

😊。

![](img/9c13d6a49e5bccdb5444797056376a25_11.png)

So there's a suggestion of a classic kind of S shapeped curve here where there's a kind of roughly flat relationship。

 then there's a sharp increasing one and then kind of leveling off Now these smoothers like low S are very useful for capturing these kinds of nonlinear trends。

 but they usually don't tell you much about how things work underneath so we may want to revise our original linear model based on kind of what we found here to think to try to capture these trends and to learn more about what's going on underneath。



![](img/9c13d6a49e5bccdb5444797056376a25_13.png)

![](img/9c13d6a49e5bccdb5444797056376a25_14.png)