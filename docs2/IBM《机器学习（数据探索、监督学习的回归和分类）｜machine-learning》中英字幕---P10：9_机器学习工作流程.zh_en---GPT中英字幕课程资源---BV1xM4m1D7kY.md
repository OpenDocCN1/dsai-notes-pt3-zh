# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P10：9_机器学习工作流程.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

In this final section， we're going to go over the basic vocabulary and workflow for machine learning。

So let's talk about the learning goals for this next action before getting into our next course we'd like to go through some fundamental concepts We'll go over the basic background and tools we'll be using throughout the course。



![](img/934197a2a2815215ececa7675e346804_1.png)

In this section， we'll also introduce the typical machine learning workflow。



![](img/934197a2a2815215ececa7675e346804_3.png)

We also review some basic machine learning vocabulary that all practitioners should be aware of。

 and all this will come into play for our next course when we discuss exploratory data analysis。

 data cleansing， as well as basic statistical inference。



![](img/934197a2a2815215ececa7675e346804_5.png)

So in this course， we're going to assume familiarity with Python libraries， for example。

 nuumpy or pandas。Working with Jupiter notebooks will also assume familiarity with basic statistics。

 including probability， calculating moments and Bayes rule。

 I do want to emphasize the importance here of having a background in basic statistics。

 as well as one in linear algebra， as it is very common that people skip over this foundation and tend to misinterpret and misuse many of the models that will be discussing moving forward。



![](img/934197a2a2815215ececa7675e346804_7.png)

![](img/934197a2a2815215ececa7675e346804_8.png)

Our examples will use i Python， generally using our Jupyter notebooks。

 and we'll be using the following libraries。Numpy for numerical analysis， pandas。

 for which we're going to actually read in our data into panda's data frames。

 matpotlib and seaborn for visualization， psychic learn for machine learning and then Tensorflow and cars for deep learning specifically。

 and we'll get more familiar with each of these libraries as we work through the course。



![](img/934197a2a2815215ececa7675e346804_10.png)

![](img/934197a2a2815215ececa7675e346804_11.png)

So let's dive into what our typical machine learning workflow will be。

So our first step is going to be the problem statement。 What problem are you trying to solve。

 So think with image recognition， it will be the ability to classify different objects。

 such as different breeds of dogs。

![](img/934197a2a2815215ececa7675e346804_13.png)

Then it's going to be data collection， what data do you need to solve it。

 for the example we just posed， we would need more than a single picture of each breed。

 but tons of label data for pictures and different lighting from different angles that are all correctly labeled。



![](img/934197a2a2815215ececa7675e346804_15.png)

Then we do our data exploration and preprocessing How should you clean your data so your model can use it So again with the image classification example。

 we then want to dive into our data， look at the distribution of our counts。

 look at heat maps of the densest points in regards to our pixels also for planning to use deep learning we'll want to convert our pixels to multidimensional arrays。

 giving the scale for each color。

![](img/934197a2a2815215ececa7675e346804_17.png)

![](img/934197a2a2815215ececa7675e346804_18.png)

![](img/934197a2a2815215ececa7675e346804_19.png)

![](img/934197a2a2815215ececa7675e346804_20.png)

Then we're going to go about actually modeling。 So we're going to want to build a model to solve our problem。

 We can try our model now， probably start with some basic baseline model。



![](img/934197a2a2815215ececa7675e346804_22.png)

![](img/934197a2a2815215ececa7675e346804_23.png)

Then we're going to validate。 Did we solve the problem， We would check with a holdout set。

 so we'd have a set of pictures that we haven't actually trained our model on and see how well we were able to classify that image。

 given the labels that we have。

![](img/934197a2a2815215ececa7675e346804_25.png)

![](img/934197a2a2815215ececa7675e346804_26.png)

Then comes decision making and deployment， So assuming that you did a good job in getting a certain range of accuracy。

 you would then move forward with communicating stakeholders in regards to how to put this in production or actually just move forward in putting it into production。



![](img/934197a2a2815215ececa7675e346804_28.png)

![](img/934197a2a2815215ececa7675e346804_29.png)

So let's get started with machine learning vocabulary。

 we'll start here with our target variable and that's going to be the target or value that we are trying to predict。



![](img/934197a2a2815215ececa7675e346804_31.png)

![](img/934197a2a2815215ececa7675e346804_32.png)

Now it'll be easier to think of each of these terms。

 each of these vocabulary terms that we go over in the context of a spreadsheet。



![](img/934197a2a2815215ececa7675e346804_34.png)

So here we're going to revisit the spreadsheet containing the wellknow data set on different Irish flower species。

 and we see here for each entry the length and the width for the sepel as well as the length and the width for the petal。

 and then we also have a label for which of the three species that entry belongs to。



![](img/934197a2a2815215ececa7675e346804_36.png)

![](img/934197a2a2815215ececa7675e346804_37.png)

And the idea being here that wed be trying to predict later on this species without having that available to us。

 So the value that we're trying to predict。

![](img/934197a2a2815215ececa7675e346804_39.png)

Our target variable， which we just discussed， would be the species in this example。

 The next popular term that you will want to be familiar with are your features or your explanatory variables。

 and those will be the other columns besides a target variable that you will use in order to predict your target variable。

 So later on down the line when you're doing machine learning when you don't have a label for your data set。

 All you will have are the features。

![](img/934197a2a2815215ececa7675e346804_41.png)

![](img/934197a2a2815215ececa7675e346804_42.png)

In the context of our spreadsheet， the features are going to be all of the columns besides that target column。



![](img/934197a2a2815215ececa7675e346804_44.png)

![](img/934197a2a2815215ececa7675e346804_45.png)

So for the IIS data set， there are four features， the Sepel length， the Sepel width。

 the pedal length， and the pedal width， and those are going to be what are used in order to predict our target variable。



![](img/934197a2a2815215ececa7675e346804_47.png)

![](img/934197a2a2815215ececa7675e346804_48.png)

Another term that you're going to want to be familiar with is going to be an example or an observation。

 and that's just going to refer to a single row within your data set。



![](img/934197a2a2815215ececa7675e346804_50.png)

So let's jump back into our I data set and think about what is an example within this spreadsheet。



![](img/934197a2a2815215ececa7675e346804_52.png)

![](img/934197a2a2815215ececa7675e346804_53.png)

There are many examples in this IRA data set and all of them are used to try to train and optimize the right parameters for a machine learning model。

 so we see here one row， which is one example or another terms one observation and you'll be hearing those terms interchangeably as you reference a single row。



![](img/934197a2a2815215ececa7675e346804_55.png)

![](img/934197a2a2815215ececa7675e346804_56.png)

Now we introduce the label and the label is just going to be the value for your target variable。

 so when we talked about an observation or an example， we were talking about the entire row。

The label is just going to be just that one data point that refers to your target variable。



![](img/934197a2a2815215ececa7675e346804_58.png)

For a label within our data。

![](img/934197a2a2815215ececa7675e346804_60.png)

All that is is a single example of our target variables。

 so here versa color would be an example of just a single label within our target variables。



![](img/934197a2a2815215ececa7675e346804_62.png)

So just to recap， hopefully now you have a basic understanding of the following。



![](img/934197a2a2815215ececa7675e346804_64.png)

You have your background knowledge and the tools that you'll need to ensure success in this course。



![](img/934197a2a2815215ececa7675e346804_66.png)

You have the basic machine learning workflow from problem statements up until deployment。



![](img/934197a2a2815215ececa7675e346804_68.png)

And you learn some of the basic machine learning vocabulary that you should be familiar with。

 such as targets， features， examples or observations， and labels。



![](img/934197a2a2815215ececa7675e346804_70.png)

![](img/934197a2a2815215ececa7675e346804_71.png)