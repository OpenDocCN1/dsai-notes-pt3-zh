# 吴恩达《机器学习工程师的生产实践（MLOps）Machine Learning Engineering for Production》中英字幕 - P11：10_关键挑战.zh_en - GPT中英字幕课程资源 - BV1pi4y167g5

![](img/1c4361c4e8c94a44f12b26a98b7a5671_0.png)

What is hard about trading a machine learning model that does well。

 let's look at some key challenges。One framework that I hope you keep in mind when developing machine learning systems is that AI systems and machine learning systems comprise both code。

 meaning the algorithm or the model， as well as data。

There's been a lot of emphasis in the last several decades on how to improve the code。

 in fact a lot of AI research had grown up by researchers downloading datas and trying to find an algorithm model that does well on the data。

 but for many applications you have the flexibility to change the data if you don't like the data。

And so there are many projects where the algorithm or model is basically a solve problem。

 some model you download of GitHub will do well enough and it'd be more efficient to spend a lot of your time improving the data because the data usually has to be much more customized to your problem this is a view that will carry throughout this week and next week's materials。

Diving into more detail， when building a machine learning system。

 you may have an algorithm or a model。 This would be。You cold。And some data。

 and it's by training your algorithm on the data that you then have your machine learning model that can make predictions。

And of course hyperpara are an additional input to this process。

 it is important for many applications to make sure you have a well tuneed learning rate and regular parameter and maybe a few other things。

 the hyperpara are important but because the space of hyperpara is usually relatively limited。

 going to spend more of our time focusing on the code and on。

The data so model development is a highly iterative process usually start off with a model and hyperpara and data train a model。

And then take the model to carry error analysis and use that to help you decide how to improve the model or the hyperparmeter or the data。

 because machine learning is such an empirical process。

 being able to go through this loop many times very quickly is key to improving performance。

 but one of the things that will help you improve performance too， is each time through the loop。

Being able to make good choices about how to modify the data or how to modify the model or how to modify the hyper parameters after you've done this enough times and achieve a good model。

 one last step that's often useful is to carry out a richer error analysis and have your system go through a final audit to make sure that it is working before you push it to a production deployment So why is model development hard when building a model I think there are three key milestones that most projects should aspire to accomplish first is you probably want to make sure you do well at least on the training set So you're predicting housing prices as a function of the size of a house。

Are you at least able to fit a line that fits your training set quite well after you've done well on the training set。

 you then have to ask if your algorithm does well on the development set or the holdout trials validation set and then also the test set。

If your algorithm isn't even doing well on the training set。

 then it's very unlikely to do well on the De set or the test set。

 so I think of step one as something you have to do first as a milestone on your way toward achieving step two and then after you do well on the De set or test set you also have to make sure that your learning algorithm does well according to the business metrics or according to the project goals over the last several decades。

 a lot of machine learning development was driven by the goal of doing well on the depth set or test set。

Unfortunately for many problems having a high testet accuracy is not sufficient for achieving the goals of the project and this has led to a lot of frustration and disagreements between the machine learning team which is very good at doing this and business teams which care more about the business metrics or some other goals of a project so you may be wondering hey Andrew how is it possibly true that achieving low average testet error isn't good enough for a project there are few common patterns that I've seen across many projects where you need something beyond low average test set error and be to spot these issues will help you be more efficient in addressing them let's dive more into this topic in the next video。



![](img/1c4361c4e8c94a44f12b26a98b7a5671_2.png)