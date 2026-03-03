# Vizuara【中英⚡机器学习：实践教学｜Machine Learning： Teach by Doing】 p21 P21 Lecture 21： Linear Regression Introduction [BV1RusDz1EXd_p21]

Hello， everyone。Welcome to the day 21 of the machine learning Tea by Do project。Up till now。

 we have very extensively looked at one type of an ML technique， which is called as classification。

From today orward。We are going to spend a lot of time on looking at another very popular ML technique。

Which is called as regression。So in today's lecture we have two main agenda points。

 the first is we will really conceptually understand linear regression。

 the applications which it has and why it has become such a popular ML framework。And， secondly。

We will set up regression as an emella problem。Tomorrow we will look at the main hypothesis itself and how to find the solution of the regression problem。

 but today we will set up the regression problem。So let's get started。First。

 I want to mention that any ML course which you take。

 whether it's the MIT course or the Microsoft's machine learning course。



![](img/3aaca6edd4151508b92be61fdfa414e4_1.png)

![](img/3aaca6edd4151508b92be61fdfa414e4_2.png)

Every course has a section on regression and every course has a section on near regression。However。

 what many of these courses lack is an inspiration for where these techniques are used in the first place and the motivation behind the regression problem itself。

So when I went through the lecture notes of all these courses， they were quite good。Technically。

But they did not convey away to me。Parteg。As a concept。And why it has become so popular。

 So today I'm just going to try to bridge that gap。



![](img/3aaca6edd4151508b92be61fdfa414e4_4.png)

Okay， so first of all， the main idea behind regression is this。The main idea is that。

Very similar to classification， we have the data sets like this。



![](img/3aaca6edd4151508b92be61fdfa414e4_6.png)

Where we have x and y pairs， input and output pairs。So， your。The X， I。



![](img/3aaca6edd4151508b92be61fdfa414e4_8.png)

Is my input and this can be in any dimension space， it can be one dimension。

 two dimension or even higher dimensions and the y high is my output。

The difference from the case of classification is that this output value in the case of regression。

Takes a continuous value。Remember in a classification。

 the output value always took discrete either of one or two values， either plus 1， minus 1，10， etc。



![](img/3aaca6edd4151508b92be61fdfa414e4_10.png)

![](img/3aaca6edd4151508b92be61fdfa414e4_11.png)

In the regression， the output value takes continuous value。



![](img/3aaca6edd4151508b92be61fdfa414e4_13.png)

And one more thing which is very important is instead of classifying。

Which we did in the classification algorithms。The main word which we will use again and again in the regressioncurion task is that we will predict。



![](img/3aaca6edd4151508b92be61fdfa414e4_15.png)

Prediction is the main key and is the main function of regression methods。

 and that's why they have gained so much popularity。



![](img/3aaca6edd4151508b92be61fdfa414e4_17.png)

If you think all around you。Prediction tasks are everywhere。

 so weather forecasting requires you to predict what the weather of the future days would look like then stock price is a perfect example of predicting whether the stock will grow or the stock will fall。



![](img/3aaca6edd4151508b92be61fdfa414e4_19.png)

![](img/3aaca6edd4151508b92be61fdfa414e4_20.png)

Then。Let's say consider all the delivery apps such as Zmatoto， B， Swiggie， etc。

You need to forecast the demands of the customer， you need to forecast the need of the customer and you need to allocate resources accordingly。

 so demand forecasting。Is a very crucial task which need to be done in the supply chain industry for that regression models are extremely useful。

 in fact every way which you look all the sectors。ML has really enabled us to predict outcomes。

 to predict results， and that's why regression has become so popular。😊。

So all of these are the applications of regression。



![](img/3aaca6edd4151508b92be61fdfa414e4_22.png)

Okay， now before going into setting up the regression as a machine learning framework。



![](img/3aaca6edd4151508b92be61fdfa414e4_24.png)

![](img/3aaca6edd4151508b92be61fdfa414e4_25.png)

I want to conceptually explain to you where the idea of regression essentially comes from。



![](img/3aaca6edd4151508b92be61fdfa414e4_27.png)

So to do that I will take a case study which we ourselves have encountered so we typically visit schools to teach machine learning to teachers right and this is the case study where we taught a regression to teachers。

So this case study is based on our own experience of visiting schools and looking at the marks of the students and then one school wanted us to come up with an MLL model where we can predict the marks of student based on some parameters which they gave us。



![](img/3aaca6edd4151508b92be61fdfa414e4_29.png)

![](img/3aaca6edd4151508b92be61fdfa414e4_30.png)

So in this case today， we just narrowed down that problem to a very simple case and we presented it to teachers。

And we wanted to understand their reaction。But this also serves like a great way to understand the motor regression in the first place。



![](img/3aaca6edd4151508b92be61fdfa414e4_32.png)

Okay， so here is the problem itself。Imagine that you have a bunch of students and you are collecting their marks。

 okay？

![](img/3aaca6edd4151508b92be61fdfa414e4_34.png)

So first， let's say you only have one student who has studied for four hours and he or she has obtained 33 percentage marks。

 which has been shown in the graph。

![](img/3aaca6edd4151508b92be61fdfa414e4_36.png)

The question which we ask teachers is that imagine there is another student now who studied for seven hours。

 can you predict their percentage marks？

![](img/3aaca6edd4151508b92be61fdfa414e4_38.png)

We provided no other information to this teacher， to these group of teachers and we just asked this question。

 in fact， even you who are watching this video try to think of the answer。



![](img/3aaca6edd4151508b92be61fdfa414e4_40.png)

Can you predict the percentage mark for another student who has let's say studied for seven hours？



![](img/3aaca6edd4151508b92be61fdfa414e4_42.png)

So here are the predictions made by teachers， they ranged from 50 to 55 to 60 to 90。

 so a big range of predictions。

![](img/3aaca6edd4151508b92be61fdfa414e4_44.png)

It turned out that when we measureded the percentage marks for the student to study for seven hours。

 he had obtained 58 percentage marks。And that is shown as the second data point over here。

Now comes the next question which we ask the teachers consider a third student who studied for eight hours。

Can you predict their percentage marks now you have two data points。

Here you can see the teacher's predictions it still varied from 60 to around 80。

 but many were able to now start visualize things in the plot and able to make predictions。



![](img/3aaca6edd4151508b92be61fdfa414e4_46.png)

So okay， it turned out that the third student who studied for eight hours actually had 67 percentage mark。

 that's fine。

![](img/3aaca6edd4151508b92be61fdfa414e4_48.png)

Now， what we gave to the teachers was now let's say you have five data points as shown in the figure。

Of students who are studied for four， seven， eight。

 five and nine hours and their percentage marks have also been plotted here。



![](img/3aaca6edd4151508b92be61fdfa414e4_50.png)

![](img/3aaca6edd4151508b92be61fdfa414e4_51.png)

Now he told them， consider a six student who studied for 10 hours。



![](img/3aaca6edd4151508b92be61fdfa414e4_53.png)

Can you predict the percentage marks of this student？



![](img/3aaca6edd4151508b92be61fdfa414e4_55.png)

Look at the responses which the teachers gave， all the responses now lie in a closer range right compared to when the teachers had lower data points。



![](img/3aaca6edd4151508b92be61fdfa414e4_57.png)

![](img/3aaca6edd4151508b92be61fdfa414e4_58.png)

All the responses now lie in the range of 82 to 90 which is a much closer range this indicated that the confidence of the teacher's prediction was increasing they were somehow able to look at this graph and predict。



![](img/3aaca6edd4151508b92be61fdfa414e4_60.png)

![](img/3aaca6edd4151508b92be61fdfa414e4_61.png)

![](img/3aaca6edd4151508b92be61fdfa414e4_62.png)

The maps of a student who studied for 10 hours。So it turned out that the six student who studied for 10 hours actually had obtained 83 percentage marks。



![](img/3aaca6edd4151508b92be61fdfa414e4_64.png)

And many teachers were close。

![](img/3aaca6edd4151508b92be61fdfa414e4_66.png)

Actually， very close based on their prediction。Then we ask the final question to the teacher that now imagine you have data points for six students。

And consider a seven student who studied for 12 hours。



![](img/3aaca6edd4151508b92be61fdfa414e4_68.png)

Can you predict the percentage marks of this seven student。

Now look at the responses of these teachers。All the responses were extremely close from a range of 96 to 99。



![](img/3aaca6edd4151508b92be61fdfa414e4_70.png)

Teachers were extremely confident in their predictions and almost everyone got it right。

 the seventh student had actually obtained 100 percentage marks。



![](img/3aaca6edd4151508b92be61fdfa414e4_72.png)

Did you see what was happening as more and more training data was provided to the students？



![](img/3aaca6edd4151508b92be61fdfa414e4_74.png)

or to the teachers rather， as more and more training data was provided to the teachers。

 the accuracy of the teacher's prediction increased with the number of data points。So first of all。

 this explains the importance of training data for any ML model。



![](img/3aaca6edd4151508b92be61fdfa414e4_76.png)

Second， it really illustrates that if you are given。



![](img/3aaca6edd4151508b92be61fdfa414e4_78.png)

6 points somehow mentally our mind does something so that we can predict the percentage。



![](img/3aaca6edd4151508b92be61fdfa414e4_80.png)

For2 for someone who studied for 2rs， in fact， I am quite confident that if you are given these six points as training data。



![](img/3aaca6edd4151508b92be61fdfa414e4_82.png)

You can take any other point and predict the percentage marks of the students。

How is that it is because in your mind you are constructing a model you think that these points are actually arranged in kind of a straight line right so there must be a straight line passing through these points and so if I give you any other input you are able to predict the percentage marks。



![](img/3aaca6edd4151508b92be61fdfa414e4_84.png)

This is exactly what linear regression does。