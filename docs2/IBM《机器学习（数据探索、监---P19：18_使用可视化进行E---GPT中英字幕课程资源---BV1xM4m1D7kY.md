# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P19：18_使用可视化进行EDA.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Okay， now let's briefly talk about some of the data visualization libraries that are available to us。



![](img/40f7feec54126eb5b698b4c92e293d35_1.png)

![](img/40f7feec54126eb5b698b4c92e293d35_2.png)

We have MatpllootLib， which will be the main library used to create plots and graphs in Python。

 and it has a lot of flexibility and features that you can tweak and definitely very useful in the foundation for doing visualizations within Python。



![](img/40f7feec54126eb5b698b4c92e293d35_4.png)

![](img/40f7feec54126eb5b698b4c92e293d35_5.png)

![](img/40f7feec54126eb5b698b4c92e293d35_6.png)

Now， pandas， which we've seen so far， actually offers a convenient wrapper function around the Matplotlib library。

 so plots can be created pretty easily on the fly compared to working with the raw version of Matpllootlib。

 and it's very convenient but it's less flexible and less powerful compared to working with the original version of Matplotlib。

 but often it's good enough。

![](img/40f7feec54126eb5b698b4c92e293d35_8.png)

![](img/40f7feec54126eb5b698b4c92e293d35_9.png)

![](img/40f7feec54126eb5b698b4c92e293d35_10.png)

![](img/40f7feec54126eb5b698b4c92e293d35_11.png)

Then finally， Seabornoure is a library built on top of matteplotlib as well。

 and it creates very pretty plots， has shorthand methods， create statistically interesting plots。

 such as linear model plots， pairwise correlation plots and many others。

 which would otherwise take a long time using just matteplotlib。



![](img/40f7feec54126eb5b698b4c92e293d35_13.png)

![](img/40f7feec54126eb5b698b4c92e293d35_14.png)

![](img/40f7feec54126eb5b698b4c92e293d35_15.png)

![](img/40f7feec54126eb5b698b4c92e293d35_16.png)

Also， once important， once imported， seaboard's preferences are incorporated by that thoughtlib。

 so if you import seaborn and then go back to using that thoughtlib。

 it would look like you're still within the pretty visualization format that seaborn has。



![](img/40f7feec54126eb5b698b4c92e293d35_18.png)

![](img/40f7feec54126eb5b698b4c92e293d35_19.png)

![](img/40f7feec54126eb5b698b4c92e293d35_20.png)

Now let's dive into actually creating some of these plots。

 we'll start off here with a basic scatterplot with Matpllootlib When we're working with Matplotlib。

 we're going to actually probably importing Matpllootlib do Piplot and we're going to bring that in SP PLT this submodule Pipl。



![](img/40f7feec54126eb5b698b4c92e293d35_22.png)

![](img/40f7feec54126eb5b698b4c92e293d35_23.png)

![](img/40f7feec54126eb5b698b4c92e293d35_24.png)

![](img/40f7feec54126eb5b698b4c92e293d35_25.png)

And。Whenever we want to use matplotlibb in our Jupyter notebooks。

 something to note which often trips people up is that before you start doing any plotting for those plots to actually show up in your notebook。

 Yet have the call a line， which we'll see in our notebooks that we run percentage mattepllib space in line。

 and that will allow for the plots to actually show。



![](img/40f7feec54126eb5b698b4c92e293d35_27.png)

![](img/40f7feec54126eb5b698b4c92e293d35_28.png)

![](img/40f7feec54126eb5b698b4c92e293d35_29.png)

![](img/40f7feec54126eb5b698b4c92e293d35_30.png)

So here we've imported mappotlib。 Pi plotot as PLT。

 we're then going to run PLT dot plot and what do we want to plot we want to plot the sepple length。

 so we're pulling in that column Sepple length。

![](img/40f7feec54126eb5b698b4c92e293d35_32.png)

![](img/40f7feec54126eb5b698b4c92e293d35_33.png)

![](img/40f7feec54126eb5b698b4c92e293d35_34.png)

And we are also pulling in sepple width。 remember we're using a scatterpl。

 So we're looking at the relationship between the two。 LS here is going to stand for line style。

 and we want there to be no lines。 So we set it equal to blank and our marker equals。

 We're making this an O， which is just a circular dot as other options such as the carrot will be triangle。

 x will be x's and so on。

![](img/40f7feec54126eb5b698b4c92e293d35_36.png)

![](img/40f7feec54126eb5b698b4c92e293d35_37.png)

![](img/40f7feec54126eb5b698b4c92e293d35_38.png)

![](img/40f7feec54126eb5b698b4c92e293d35_39.png)

And this is what our output will look like given the code that we see here on the left。

 so we see the scatter plot between sbel length and seple width。



![](img/40f7feec54126eb5b698b4c92e293d35_41.png)

Now， what about working with scatter plots with multiple layers。

 maybe want to differentiate it by color？

![](img/40f7feec54126eb5b698b4c92e293d35_43.png)

We can do them one after the other as long as we don't reinitiate our plot。

 every single plot that we call using a KLT dot plot will plot one and then the next。



![](img/40f7feec54126eb5b698b4c92e293d35_45.png)

![](img/40f7feec54126eb5b698b4c92e293d35_46.png)

So， here we're using。PLT dot plot。 And again， our X values are going to be sepel length。

 our Y values sepel width， our line styles blank again， our markers O。

 And this time we're going to pass in a label and our label here is equal to sppel。

 And then we're going to do the same thing for the pedal length and pedal width。

 passing in those arguments that we mentioned before。 And this time we're labeling it pal。

 it'll automatically come up with different colors。 And if you call PLT dot legend after this。



![](img/40f7feec54126eb5b698b4c92e293d35_48.png)

![](img/40f7feec54126eb5b698b4c92e293d35_49.png)

![](img/40f7feec54126eb5b698b4c92e293d35_50.png)

![](img/40f7feec54126eb5b698b4c92e293d35_51.png)

![](img/40f7feec54126eb5b698b4c92e293d35_52.png)

You will end up with a plot you see here on the right where you have the green is indicating the scatter plot for the petal length and width and the blue indicating the sepple length and the sepel width。



![](img/40f7feec54126eb5b698b4c92e293d35_54.png)

![](img/40f7feec54126eb5b698b4c92e293d35_55.png)

![](img/40f7feec54126eb5b698b4c92e293d35_56.png)

We also have the option of plotting a histogram here we'd only want to pass in one column。

 we can pass in the argument for the number of bins that we'd like。

 and if we run this we'll see the output that we see here on the right that gives the distribution of this actual column。



![](img/40f7feec54126eb5b698b4c92e293d35_58.png)

![](img/40f7feec54126eb5b698b4c92e293d35_59.png)

So some ways that we can customize plots here we're using the PLT dot subplots so that we have fig and act separate。

 This is just a different way that we're able to。

![](img/40f7feec54126eb5b698b4c92e293d35_61.png)

![](img/40f7feec54126eb5b698b4c92e293d35_62.png)

Ploot are difference functions where we have。 this is a more object oriented form where the figure will be or fake here is going to articulate essentially all of the major basics around our plot and X is going to be the actual box itself where we're putting in our plots and generally speaking。

 if we use this fig comma X syntax。 We can replace what we had for PLT with somethings very similar。

 just calling x rather than PLT。 So here we're calling a horizontal bar plot。



![](img/40f7feec54126eb5b698b4c92e293d35_64.png)

![](img/40f7feec54126eb5b698b4c92e293d35_65.png)

![](img/40f7feec54126eb5b698b4c92e293d35_66.png)

![](img/40f7feec54126eb5b698b4c92e293d35_67.png)

And we want it to be values between0 and9， calling NP do range 10。

 and we're going to look at the sepel width just through the first 10 values。

 so we're going to look at the different widths and we're going to have a barn plot to represent each one of those widths。



![](img/40f7feec54126eb5b698b4c92e293d35_69.png)

![](img/40f7feec54126eb5b698b4c92e293d35_70.png)

![](img/40f7feec54126eb5b698b4c92e293d35_71.png)

Now we can put specific。Y ticks specific labels， specific X labels， as we'll see here。

 using the x functionality， we're going to use set underscore yt。

 and we say we want our yt to be between 0。4 and 10。4 counting by one。

 this will allow for each tick to actually be in the middle of the bar rather than calling it 0 through 10。

 which would be the default。

![](img/40f7feec54126eb5b698b4c92e293d35_73.png)

![](img/40f7feec54126eb5b698b4c92e293d35_74.png)

We can call our Y tick labels and we just want those to be the values 1 through 10， right in Python。

 it won't include the last value， but will include the first。



![](img/40f7feec54126eb5b698b4c92e293d35_76.png)

![](img/40f7feec54126eb5b698b4c92e293d35_77.png)

And then we're going to set using X dot set， we can actually pass in a lot more of the arguments similar to ytics and yt labels。

 and we say that with we see that with the X label So we're calling the X label。

 we're actually calling that the string X label， we're calling the Y label the string Y label and our title is title and we see the output here on the right。

 where we have the title like we mentioned Y label and X label values one through 10。

 and each of those representing the different sepel widths for our first10 values。



![](img/40f7feec54126eb5b698b4c92e293d35_79.png)

![](img/40f7feec54126eb5b698b4c92e293d35_80.png)

![](img/40f7feec54126eb5b698b4c92e293d35_81.png)

![](img/40f7feec54126eb5b698b4c92e293d35_82.png)

![](img/40f7feec54126eb5b698b4c92e293d35_83.png)

![](img/40f7feec54126eb5b698b4c92e293d35_84.png)

![](img/40f7feec54126eb5b698b4c92e293d35_85.png)