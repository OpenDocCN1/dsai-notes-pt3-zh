# 华盛顿大学《机器学习（基础篇，第1课／共4课）｜Machine Learning》中英字幕 - P105：104_使用深度特征训练并评估分类器.zh_en - GPT中英字幕课程资源 - BV1zw4m1e7Zh

。

![](img/654085ebba2a33fb122fd8ff413c6d5e_1.png)

So the question here is。Can we improve。The model using deep features。 Remember。

 we talked about deep features。 We explored those quite a bit in the。And the deep learning module。

 how deep features using technical transfer learning can be trained on one domain。

 then applied to images in another domain domain to learn。😊。

Something with even a small amount of label data。 So in this case。

 let's just take a look at the length of our。Train data。Just to geoensor we have。

 we only have 2000 images。 so this is a pretty small data set。

We can we can go ahead and see what we can do with just 000 training0 images about using some deep features。

 So this is the steps that you take。 So we're going to load deep learning。😊，呃。Learning。

Model that was pre trained。 and so here you can use Graphlab dot。loadad model。To load a model。

 and I have a model that was trained on the imageNe data。 it's over here， So it's called INe。Moel。

And this model is trained with 1。5 million images， 1000 different categories， a different data set。

 1。5 million images， it was where we discussed the AlexNet model。

 they got really amazing actress in 2012 image net competition so I pretrained that model and then you can use that model to create。

In our image train， a new column called deep featuress。And in this new column features。

 what I'm going to do is take this deep learning model that we just loaded。😊，Deep。Learning model。

 And I'm going to。Apply a function called extracttract。Features and what extract features does。

Is extract those deep features， so does it transfer learning。

 taking features of learning one domain and applies to a data set in a different domain。

 So this data set here is my image train data。So these are the two commands that you have to do pretty simple actually let me decrease the font size so that it will be a little bit more visible。

 the two commands that you have to do to do the transfer learning so take the imageNe train neural network and apply it to this CFR 10 dataset now this computing features takes a few minutes and so I'm not going to do this right now。

😊，Instead， I'm just going to tell you that our deep mode if I show you the image train data。

What I did was if I just show you the head， the first few lines。

 what you'll see is that you have an image ID。You have an image which we've been looking at。

 you have the label and you have a column for deep features so I precomputed that and I saved it inside S frame so it's already saved and precomputed and it also has another column image array that has the raw pixelos that we use to train the raw pixelix model。

 So the deep features are already in there but if you run those two commands you'll be computing them on yourself on this data or any data that you want。

 So let's go ahead。😊，And now that we have the deep features， let's train a deep model。

Given the deep features。Let's dream。A classifier。So now we're going to train a simple classifier using the deep features。

 I'm going to call this deep。😊，Features。Model instead of the raw pixel model and the D model is also going to be just calling logistic regression。

So dot create and if you remember from lecture， we discussed that you can take those little features and plug in a simple classifier at the end in this case we'll just plug in logistic regression so as input I'm going to give it the image train data。

😊，And。For features。Instead of using the rough pixel， I'm going to use the deep features。And finally。

 I'm going to tell it that the label， sorry， the target。

The thing that I'm trying to predict here is given by the label column。And there you go。

 So now we're learning a classifier and it's done here using on those 2000 images only using data from using features completed in this deep neural network that won the 2012 deep learning computation。

 So now let's let's first explore the model just applied for some data。 So I'm going to。😊。

We're going apply。The deep。Features model to。The first few images of test set。

 just like we did with the raw pixelix model， we're going to apply it in this case。

 so remember we took the image test data and we looked at the first three images。

So zero1 and two and here's what those images look like and I'm going to type To show and just remind you that we have a cat。

A cat， a car， and another cat。And。Let's go ahead。And just run the deep model to see what we predict。

 So I'm going to take my deep feature model， and I'm going to。😊，Predict。On this three images。

 so image test。Of0 through 3。And Remer cut cut and it says CAt automobile card。

 so basically it got those three exactly right which is exciting。

 so something that sucked really really did badly using the raw pixels now using these deep features does well on those three points it gets exactly right。

 but let's actually evaluate the deep model。😊，More formally。So we're going to do next is compute。

The test。Data accuracy。嗯。The deep features。我的。And here we go， so how we're going to do that。

 we're just going to do deep features model dot evaluate just like we did with the raw pixelix model here we do dot evaluate and as input we're going to give it the test data so image test。

And remember， the rep of all about 46% accuracy was bad。Here by using deep features。

 we now get 78% accuracy， which is quite good it's close to the state of the art。

 even if you learn more data， it's quite good compared to that 46%。

 so the deep features provide you with a great tool for taking just a little bit small piece of data。

 running for the deep features and get quite good accuracy essay doing image classification task here。

😊。

![](img/654085ebba2a33fb122fd8ff413c6d5e_3.png)