# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p123 39_03_03_MLOps深入解析.zh_en -BV1tz421i7Ev_p123-

![](img/bbf6334808d598f27dcf107c20a0efc0_0.png)

So what is this MLOs workflow here in a nutshell it's the combination of machine learning。

Development and operational best practices， and this is what makes it interesting and also a little bit complex is。

Typically， a data scientist would be focused on， let's say modeling or training and they would make sure that the model has explainability and it's able to accurately do a prediction。

 and it may even involve things like looking at the AUC or area under the curve going back to the domain expert and verifying that that the model is actually accurately doing what it's supposed to do。

But beyond just that modeling phase， there's more to the story to put this into production and that's really what MLOs is about is can I put this into production so in order to do that there needs to be a development component and that's when the MLOs practitioner would go in and use a framework like let's say Python flask or look at the cloud architecture potentially with AWS go through and build a data lake build a pipeline that goes through and moves the data back and forth。

 all of those architectural pieces of getting the system flowing like almost like a water system in a town that's a critical component of the development part of MLOs now when you get into operations this is where let's say the model' has been developed the framework's been developed so it's able to do a prediction but then。

Are you able to。Repeatedly deploy that model into production and are you able to tell if things like data drift are occurring right where you know you're able to you know look and double check the last time I trained the model there was maybe three months ago and things have dramatically change what can I do to fix it so this is about a feedback loop and this is really what MLOs is it's the combination of。

These three core competencies， machine learning。Development and operations into a feedback loop that always is running。

 It isn't static where you did it once and then you can walk away。

 there needs to be a living organism that is constantly looking through and making sure that you're able to keep this model in production。

 So a good example would be for example， creating revenue for a company if if you're selling timely products。

 let's say it's movies the movies go stale after a while if everyone's watched the movie you're not gonna to make as much money as it did when it first came out。

 And so you'll need to find the next movie to give to people through let's say a streaming service So that's a feedback loop is this constant feedback loop but your feedback loop is only as good as each of these three things in combination So MLops is a an emerging field and behaviorally's。

Something that's important for an organization to take seriously。



![](img/bbf6334808d598f27dcf107c20a0efc0_2.png)

![](img/bbf6334808d598f27dcf107c20a0efc0_3.png)