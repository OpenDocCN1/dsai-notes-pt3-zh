# 吴恩达《机器学习》｜machine-learning（中英字幕-deepseek翻译） - P4：04_01_02_监督学习第一部分.zh_en - GPT中英字幕课程资源 - BV1MN4y1S7DE

Machine learning is creating tremendous economic value today。



![](img/86323ecda54f4fb6d49caa951c492a0b_1.png)

I think 99% of the economic value created by machine learning today is through one type of machine learning。

 which is called supervised learning， let's take a look at what that means。

Supervised machine learning or more commonly supervised learning refers to algorithms that learn X to Y or input to output mappings the key characteristic of supervised learning is that you give your learning algorithm examples to learn from that include the right answers where by right answer。

 I mean the correct label Y for given input X。And is by seeing correct pairs of input X and desired output label Y that the learning algorithm eventually learns to take just the input alone without the output label and gives a reasonably accurate prediction or guess of the output。

Let's look at some examples。If the input X is an email and the output Y。

 is this email spam or not spam？This gives you your spam filter。Or if the input is an audio clip。

And the algorithms job is to output the text transcript。Then this is speech recognition。

Or if you want to input English and have it output the corresponding Spanish， Arabic， Hindi， Chinese。

 Japanese， or something else translation。Then， that's machine translation。

Or the most lucrative form of supervised learning today is probably used in online advertising。

Nearly all the large online ad platforms have a learning algorithm that inputs some information about an ad and some information about you。

And then tries to figure out if you will click on that ad or not。

 because by showing you ads that you're slightly more likely to click on for these large online ad platforms。

 every click is revenue， this actually drives a lot of revenue for these companies。

This is something I once done a lot of work on， maybe not the most inspiring application。

 but it serve has a significant economic impact in some companies today。

 or if you want to build a self driving car，The learning algorithm would take as input an image and some information from other sensors such as a radar or other things。

 and then try to output the position of， say other cars so that your self driving car can safely drive around the other cars。

Or take manufacturing I've actually done a lot of work in this sector at landing AI。

You can have a learning algorithm， takes this input， a picture of a manufactured product。

 say a cell phone that just rolled off the production line and have the learning algorithm output whether or not there is a scratch Dent or other defect in the product。

 This is called visual inspection and is helping manufacturers reduce or prevent defects in their products。



![](img/86323ecda54f4fb6d49caa951c492a0b_3.png)

In all of these applications， you would first train your model with examples of input X and the right answers that is the labels Y。

After the model has learned from these input output or x and Y pairs。

 it can then take a brand new input X， something has never seen before and try to produce the appropriate corresponding output Y。

Let's dive more deeply into one specific example。Say you want to predict housing prices based on the size of thehu。

You've collected some data and say you plot the data and it looks like this。

Here on the horizontal axis is the size of the house in square feet， and yes。

 I live in the United States where we still use square feet。

 I know most of the world uses square meters。And here on the vertical axis is the price of thehu in。

 say， thousands of dollars。So with this data， let's say a friend wants to know what's the price for their 750 square foothu How can the learning algorithm help you？

One thing a learning algorithm might be able to do is say fit the straight line to the data。

And reading off the straight line， it looks like your friend's house could be sold for， maybe about。

 I don't know，$150，000。But fitting a straightray line isn't the only learningarrow you can use。

 there are others that could work better for this application。For example。

 routed in fitting a straight line， you might decide that it's better to fit a curve。

 a function that's slightly more complicated or more complex than a straight line。

If you do that and make a prediction here， then it looks like， well。

 your friend'shus could be sold for closer to $200，000。

One of the things you see later in this class is how you can decide whether to fit a straight line。

 a curve or another function that is even more complex to the data。

Now it doesn't seem appropriate to pick the one that gives your friend the best price。

 but one thing you see is how to get an algorithm to systematically choose the most appropriate line or curve or other thing to fit to this data。

What you've seen in this slide is an example of supervised learning because we gave thearrow a data set in which the so-cal right answer that is the label or the correct price Y is given for every house on the plot。

And to task of the learning algorithm is to produce more of these right answers。

 specifically predicting what is the likely price for other houses like your friend's house。

That's why this is supervised learning。To define a little bit more terminology。

 this housing price prediction is a particular type of supervised learning called regression。

 and by regression， I mean we're trying to predict a number from infinitely many possible numbers such as the house prices in our example。

 which could be 150，000 or 70，000 or 183，000 or any other number in between。



![](img/86323ecda54f4fb6d49caa951c492a0b_5.png)

So that's supervised learning， learning input， output or X to Y mappings。

 and you saw in this video an example of regression where it tasks is to predict a number。

But there's also a second major type of supervised learning problem called classification。

 let's take a look at what that means in the next video。

