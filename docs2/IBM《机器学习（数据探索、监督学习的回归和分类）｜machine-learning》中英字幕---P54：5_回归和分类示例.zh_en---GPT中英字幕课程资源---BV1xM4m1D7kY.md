# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P54：5_回归和分类示例.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

InThis next section， we will cover the breakdown of supervised machine learning into two classes。

 regression and classification。Now let's go over the learning goals for this section in this section we're going to cover。



![](img/35cc9e1e1832ba8b1ef278338b802f07_1.png)

The two types of supervised learning， classification and regression。

 and we will show some different examples of regression and classification problems。



![](img/35cc9e1e1832ba8b1ef278338b802f07_3.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_4.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_5.png)

When we're talking about regression， we are talking about the outcome being continuous。

 a continuous number that can be box office revenue。

 that can be housing prizes that can be the number of attendees we'll have in a certain audience。



![](img/35cc9e1e1832ba8b1ef278338b802f07_7.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_8.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_9.png)

And then when we talk about classification， we're trying to predict a categorical outcome。

 and that'll be customer churn， whether or not we have a fraudulent charge or whether a certain person will be a Democrat or Republican given certain characteristics。



![](img/35cc9e1e1832ba8b1ef278338b802f07_11.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_12.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_13.png)

Now let's start with an overview of how supervised learning works。



![](img/35cc9e1e1832ba8b1ef278338b802f07_15.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_16.png)

So as we discussed， we'll have for our supervised learning data with outcomes。

 so that'll come with the data set。

![](img/35cc9e1e1832ba8b1ef278338b802f07_18.png)

We then also start off with a specific model， so we have the model already， it just has not been。

 the parameters have not been learned yet。

![](img/35cc9e1e1832ba8b1ef278338b802f07_20.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_21.png)

During our fitting process， we take our data with the outcomes。We fit our model。

 and then we end up with this new model out to the right。

 which has the parameters tuned in order to optimize how well our data is able to predict a certain outcome。



![](img/35cc9e1e1832ba8b1ef278338b802f07_23.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_24.png)

Then we take data without outcomes。

![](img/35cc9e1e1832ba8b1ef278338b802f07_26.png)

We add on that learned bottle with the learned parameters。



![](img/35cc9e1e1832ba8b1ef278338b802f07_28.png)

And we can use that in order to predict。What the outcome variables should be given what we've seen in the past。



![](img/35cc9e1e1832ba8b1ef278338b802f07_30.png)

So let's think about this with numeric predicting， we're going to use an example of movie revenue。



![](img/35cc9e1e1832ba8b1ef278338b802f07_32.png)

We start off with movie data with known revenue。 So a bunch of data， whether that's marketing budget。

 cast budget and so on。

![](img/35cc9e1e1832ba8b1ef278338b802f07_34.png)

We model according to the data that we have with the known revenue。



![](img/35cc9e1e1832ba8b1ef278338b802f07_36.png)

Once we fit that model， we learn the parameters in order to look at all these different features and predict a。



![](img/35cc9e1e1832ba8b1ef278338b802f07_38.png)

Alcome variable here being the known revenue。

![](img/35cc9e1e1832ba8b1ef278338b802f07_40.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_41.png)

So now we have that model fit with the parameters。We can run that on a movie data with unknown revenue and use that new model in order to predict what the predicted revenues will be for this next movie。



![](img/35cc9e1e1832ba8b1ef278338b802f07_43.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_44.png)

Now， in regards to classification， we will have categorical answers rather than numeric answers。



![](img/35cc9e1e1832ba8b1ef278338b802f07_46.png)

And the process will be very similar。 Instead of having the outcome variable being some type of numeric value。

 it will be some type of labeling， such as with our customer churn。

 do they churn or do they not churn。

![](img/35cc9e1e1832ba8b1ef278338b802f07_48.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_49.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_50.png)

We have a specified model。

![](img/35cc9e1e1832ba8b1ef278338b802f07_52.png)

Which has not been fit。 The parameters have not been fit yet。

But we're able to fit it because we're able to use our input variables。



![](img/35cc9e1e1832ba8b1ef278338b802f07_54.png)

Align that with our outcome variabless and see what type of parameters for the model chosen will come up with the best model。

 and then we have our fitted model。

![](img/35cc9e1e1832ba8b1ef278338b802f07_56.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_57.png)

We take that fitted model。

![](img/35cc9e1e1832ba8b1ef278338b802f07_59.png)

And then we use that fitted model on unlabeled data。And with that， we are able to predict。



![](img/35cc9e1e1832ba8b1ef278338b802f07_61.png)

What the label will be for this unlabeled data。

![](img/35cc9e1e1832ba8b1ef278338b802f07_63.png)

So an example of this with classification would be predicting spam emails。

 We start off with emails that are already labeled as spam versus not spam。



![](img/35cc9e1e1832ba8b1ef278338b802f07_65.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_66.png)

And then we come up with a model， and that model doesn't have any of the parameters defined yet。

 but it'll look at maybe all of the different words that are in a spam email versus a not spam email and figure out which words are most likely to be in spam versus which ones are most likely to be in not spam and fit that model parameters accordingly。

 Now we have our model up to the right。

![](img/35cc9e1e1832ba8b1ef278338b802f07_68.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_69.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_70.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_71.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_72.png)

And then we can take unlabeled emails， such as the emails we are constantly getting in every day。



![](img/35cc9e1e1832ba8b1ef278338b802f07_74.png)

Use that model that was learned on emails that were already labeled spam versus not spam。

 so that model with the parameters fit。

![](img/35cc9e1e1832ba8b1ef278338b802f07_76.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_77.png)

And then we can predict whether or not the unlabeled emails are spam or not spam and send them to the appropriate folders automatically。



![](img/35cc9e1e1832ba8b1ef278338b802f07_79.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_80.png)

Now， I want to make clear we just went through some very simple examples with the movie revenue。

 as well as with the spam versus not spam。 Now， this is just to highlight the framework of how any one of your business machine learning problems will actually work。

 You will have that set of data。 with labels And you'll take those labels or the numeric values that you're trying to predict。

 And then you will fit according to those inputs and the outcome variables you're trying to predict and use those fitted models。

 with their parameters， in order to predict the new values coming in。

 And that's going to be the basic for machine learning for business， no matter what your problem is。

😊。

![](img/35cc9e1e1832ba8b1ef278338b802f07_82.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_83.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_84.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_85.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_86.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_87.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_88.png)

Now， let's dive in a little bit deeper into how we would actually。



![](img/35cc9e1e1832ba8b1ef278338b802f07_90.png)

Do classification and what we need to do classification will'll need features that can be quantified。



![](img/35cc9e1e1832ba8b1ef278338b802f07_92.png)

So we had in our spam versus not spam， all of our features were actually words。

 So we'd have to actually encode that， as we saw in the past course。

 probably using something like one hot encoding in order to quantify those features。



![](img/35cc9e1e1832ba8b1ef278338b802f07_94.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_95.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_96.png)

We also need labels that are known， we need to find a way to get a list。

 a data set that actually has labels for spam versus not spam。

 and often that could be hard to accumulate because that's going to take some human type of labeling and you have to take into account that extra amount of effort that will come into play when trying to come up with labels for your data。



![](img/35cc9e1e1832ba8b1ef278338b802f07_98.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_99.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_100.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_101.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_102.png)

Then we also need a way to measure the similarity between a new record and the ones we learn from。

 so we have to have some type of similarity metric between the words that we saw in one email and the words we saw in our new labeled unlabeled dataset set coming in。



![](img/35cc9e1e1832ba8b1ef278338b802f07_104.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_105.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_106.png)

So quick recap in this section， we discuss the types of supervised learning。

 namely regression versus classification。

![](img/35cc9e1e1832ba8b1ef278338b802f07_108.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_109.png)

And then we also showed some examples of regression and classification in order to really make clear how we first fit our models。

 and then once we have our fit with our parameters， we can use that to predict on unlabeled data。



![](img/35cc9e1e1832ba8b1ef278338b802f07_111.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_112.png)

Thank you and in the next section we'll get started with our first model of linear regression。

 see there。

![](img/35cc9e1e1832ba8b1ef278338b802f07_114.png)

![](img/35cc9e1e1832ba8b1ef278338b802f07_115.png)