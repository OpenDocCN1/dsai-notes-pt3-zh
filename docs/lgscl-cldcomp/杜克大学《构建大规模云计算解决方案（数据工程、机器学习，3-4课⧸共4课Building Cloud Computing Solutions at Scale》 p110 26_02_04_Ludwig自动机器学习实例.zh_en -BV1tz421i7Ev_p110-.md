# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p110 26_02_04_Ludwig自动机器学习实例.zh_en -BV1tz421i7Ev_p110-

![](img/f45472a4ba79ae7a77cc75c7d921a547_0.png)

Let's go ahead and get started with Ludwig and do some AutottawoM so I'm going to take a data that's found here。

 this is this Boston CMU data here and what it does is it has the ability to look at a data that has newswire data so in this case there'll be 21。

000 records and there'll be six different categories and so if we go through here I can go ahead and open up this coab notebook。



![](img/f45472a4ba79ae7a77cc75c7d921a547_2.png)

And kind of get started here so first up what I would do is I would do a PIip install of Ludwig so we'll go through and do that and notice I put the dashQ flag here so that it doesn't give me a ton of output which can be pretty extensive so once I do this the next step is that I will go through and download a config file which will contain the information necessary for Ludwig to train and then also the raw data set。

 so let's go ahead and do that。

![](img/f45472a4ba79ae7a77cc75c7d921a547_4.png)

There we go， great， and notice that what I could do as well is go through here and just do a quick exploratory data analysis so I could say you know import pandas as PD。

 again， not necessary， but maybe an interesting thing to try out real quick， and I'll say PD。

read CSsv。And then I'll put in this data set here， right， And so if we do this。I can read this data。

And then maybe do like a head operation to just see what's inside so you can see here here's the class negative positive negative and then the text inside so so we have some basic text information that we're gonna classify we're going to train it to learn about these particular categories Okay great next up here all I need to do is also look at this configuration file and let's go ahead and take a look at that real quick so if I make another code cell here I can say cat config yaml。

And let's go ahead and do that。There we go so you can see that the input is text type is text level is word does a parallel CNN and then the output is class in category so we're training this thing to understand how to classify text into these different categories great now to do this it's just a Luwig experiment command and I say DG data and I pass in the data that I'm training it on and then I again pass in that config file So notice here when I run this that what it will do is it will do a tensorflowbased training and you can see here that this is all the information that it's putting inside so it' it's giving these inputs。

 these output features putting all the configuration data that we would need in there for me。

And then now we're going through a training run and this training run。

 this is EpoC1 and you can see that it's done you approximately 30% and it's going to go through and eventually create a model so I already have a training run here that I can just look at since this will take a little bit of time so if I go back here。

 you'll see what it did is that once it's complete。

 you can see here's the last training run here on epoC2。

Is that it was able to under the training set， the validation set and the test set we're able to come up with a 0。

02 loss 0。35 for validation and 0。27 for the test set so we're able to actually figure out what the best validation model set combination is here and then also what the model loss is here and then if we want to go into the actual metrics here for classification。

 we can see that it shows that the average F1 score is 0。93 and the average CAappa score is 0。

89 so there's all these really specific classification metrics here and also it will go through and show us things like know false positive rates。

 false negative rates so in a nutshell you really what this tool does is allows。

a developer or maybe a data scientist to kind of focus more on getting models created versus making boilerplate code and my prediction is that we're going to see a lot of these tools and the next 10 years get developed where maybe you could do this on your own by training your own neural network。

 but why if you can just pass in a configuration file and tell the machine itself to do the majority of the work。



![](img/f45472a4ba79ae7a77cc75c7d921a547_6.png)