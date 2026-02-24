# 图宾根大学《概率和统计机器学习｜Tubingen Probabilistic and Statistical Machine Learning 2020》中英 p57 -57-Part 54 - ML pipeline_ data, preprocessing, learning.zh_en -BV1gso5YGE4s_p57-

In the last part of the lecture， we spend a lot of time trying to look at particular machine learning algorithms。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_1.png)

In a reasonably artificial scenario and the scenario was always assumed we are given this very nicely collected data set。

 it consists of points X I， Y， I I from1 to n sample IID from our underlying distribution All is nice。

 and now we need to solve this particular classification problem and then we are done。😊，Now。

 in real life， machine learning looks very differently。Typically。

 data doesn't arrive in such a clean fashion。 You， first of all， need to record it。

 You need to think about how to record it， what to record， what kind of biases you have。

 You need to figure out which machine learning algorithm to use。

 You need to figure out how to evaluate it。 And then data on also what you're supposed to do with your results and whether they are really good or bad。

In this and the next lectures， I want to go through at least some aspects of this。

 what I call the processing chain。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_3.png)

From raw machine learning from data to sorry from raw data to machine learning。

 and I guess what's missing in the caption is even and beyond。😊，And post processing。

And first of I want to give you a little overview over what are some of the steps and then I'm going to dive into some of these steps and for none of these steps I do a complete treatment I just highlight certain aspects that might go well or might go wrong。

 things that you might want to consider。😊，And keep in mind。

 this is all just in this very restricted framework of the algorithms that we've considered in this lecture。

 the statistical approach to machine learning， things would again look different if you work on deep learning or probabilistic models or reinforcement learning。

 So this is particularly tailored to what we've been discussing in this lecture。😊。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_5.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_6.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_7.png)

Let us maybe first of all， look at what are the high level steps that you can imagine or that you could expect when you want to solve a machine learning problem。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_9.png)

And maybe for the sake of making an explicit， put yourself into a position of a scientist who wants to use machine learning。

 say you're a geoscientist and you want to use machine learning to make a certain prediction about a certain property of a soil in a particular place。

😊。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_11.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_12.png)

Now there could be this scenario that you can freely collect your data as you want。

 there might be lots of restrictions。 Maybe you can you're not allowed to dig holes in the ground at every particular place you would like and digging holes is also expensive。

 so maybe you have lots of restrictions in the sense。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_14.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_15.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_16.png)

So data collection is complicated， and then you want to use machine learning。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_18.png)

Maybe to solve a prediction problem， but this is an aspect of a much larger problem。

 namely you want to solve a scientific problem， you want to understand something。

 you want to learn something new in neuros scientificent domain。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_20.png)

The other application field， you might want to look at this。😊，I's an industrial application。

 say your boss comes and says， you are supposed to build this machine learning system that helps improve their customer satisfaction for his online job。

😊，Then again， you have lots of different requirement， maybe your data， you can't collect it。

 there is some data in the background。 it has never really been collected for the purpose that you are supposed to use it for。

 and that brings lots of different kind of complications。

 So whenever we now go through these in the next lectures， please keep in mind。

 maybe from time to time ask yourself in which way would it apply to this either scientific application or maybe this application or in industry。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_22.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_23.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_24.png)

So whenever you do this machine learning， there are a couple of steps that typically come up。

 And here， I first of all，ll give you a high level overview。 and then we are going to dive into it。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_26.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_27.png)

So the first step， of course， is the gathering data。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_29.png)

And it could be that you can gather data on purpose。

 It could be that you just need to use some data that is lying around that has never been collected for this particular purpose。

 but now you want to reuse it。No matter how you do it。

 typically it is going to contain lots of sampling biases。

 it might also consider biases with respect to fairness， as we've seen in the lectures on fairness。

 it might consider lots and lots of distortions， there might be missing values。

 there are many aspects about this data collection which are already difficult。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_31.png)

Then you need to pre processces the data。 That's the second step。

This means you might need to clean your data。 There might be some data points that are completely wrong。

 Your devices have failed。 Custom have answered random questions or given random random answers to your questions。

 They might be missing values。 You need to standardize。 You might want to compress your data。

 maybe just subsle your data， because it's too much。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_33.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_34.png)

You might want to use clustering to sort of split your dataset set into different parts。

 which are being treated separately。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_36.png)

Reducing dimensionality， all these kind of aspects are what typically is meant by preprosing。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_38.png)

Then you need to set up the learning problem。 And first of all。

 this means you really need to ask the question that you want to solve the learning algorithm to solve。

 So what is really the classification problem that you want to set up。😊。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_40.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_41.png)

What are the labels often there are many different ways in which you can set up such a problem。

 So what is the target variable that you actually use that the algorithm is supposed to predict。😊。

Which loss function are you going to use， Which algorithm， Which similarity function。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_43.png)

What else do I have， Oh yes， How do you incorporate prior knowledge you might have like in a scientific context。

 for example， you might have， I don't know， know something about differential equations that describe how the earth is going to move in a certain place。

😊。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_45.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_46.png)

You might also want to consider the inductive bias of your learning algorithm and see whether for example。

 if you apply a learning algorithm with respect to sparsity that has a sparsity。

 inductive bias is your data really sparse does it makes sense？😊。

These are questions that you need to ask。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_48.png)

Then you need to evaluate your results。This means obviously you might want to compare it to a by baseline and see whether your learning algorithm does something useful at all。

 you also need to get a feeling for the numbers。 So if the accuracy is 70% is this high or low given your current context。

 what would be random guessing， what would be another by baseline。

 How much wouldn't the accuracy need to be such that the application would give you some benefit rather than not using it or doing something very simple。

😊。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_50.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_51.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_52.png)

嗯。And this not only concerns accuracy accuracy， but this might concern many other dimensions as well。

 For example， you might want to evaluate your algorithm with respect to fairness of machine learning and。

 and the outcome of your algorithm。 And there might be many other criteria that you might want to look at when you evaluate your algorithm。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_54.png)

And of course， there are also many different tools by which you can do that you can look at the Cur here。

 you can look at the ROC curve。 there are many tools that we're going to discuss。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_56.png)

And then finally， comes the post processing phase。For example， in a scientific context。

 you might want to interpret youricide because for a scientist。

 it's never like the end goal is never to sort of predict the amount of， I don't know。

 carbon dioxide at this particular place in the rainforest。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_58.png)

This is just an indicator that you later aren going to use for something else。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_60.png)

So the question is now。Given now the outcome of your machine learning results。

 is there something that you can learn from from a scientific perspective？😊。

AndAlso post processingcess concerns the fact that if you want like in an industrial or like even if you're in a social context it doesn't even need to be industry。

 you have some kind of government agency and you want to deploy a machine learning algorithm in practice。

 what would be the consequences if you deploy this algorithm， what would be the social impacts。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_62.png)

What are all the side effects of using this new tool that you might not have foreseen。

 but you might want to think about at least hard？😊。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_64.png)

About the side effects that at least you come up with。And then finally。

 all this is not a linear procedure。 It's not like you collect your data once you prepro it once you apply machine learning and you evaluate。

 this is sort of a loop。 And this loop can take very， very long。

 It is not like you can solve each machine learning problem within a week or so。

 So it might be you go back and first， you play here， you play there。😊。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_66.png)

嗯。So all this is not really simple。At least if your problem is not straightforward。

 and this is the case for most problems。So what I want to do now is I want to dig into each of these steps。

 and by no means， I am going to give you a comprehensive list of things that can be done。

 I just started to list some aspects that came to my mind。

 But then you might also want to consider that I am not really a machine learning practitioner。

 I'm a theory person。😊，So I don't have industrial experience with setting up large scale machine learning problems。

 So these are the things that come into my minds， and this is simply meant as an encouragement to think about the issues in your particular machine learning application that maybe there might be additional things that you would need to consider that maybe are not on my slide so this is not a comprehensive list。

 It is just a list that shows that there are lots of things that need to be done。😊。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_68.png)

So let us start with the aspect of preparing the data。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_70.png)

Data acquisition and the difference between train and test distribution。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_72.png)

The， the key point here is machine learning as I said， Start with acquiring good data。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_74.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_75.png)

And the results of your algorithm obviously can only be as good as your data is so far， so clear。😊。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_77.png)

Now， typically when you start collecting data for a machine learning application。

 often the phase when you collect the data is not the same as as to which you apply the data。😊。

For example， what you might want to ask yourself is are the potential test cases really covered in the training data with all the variety？

😊。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_79.png)

So if you want to classify digts。😊。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_81.png)

Are all digits really upright in your digit classification。

 so you want to use 1written digit recognition via the postal service in my training set。

 all the images are really nice and upright figures Dits。

 I this going to be the same in my test data。😊。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_83.png)

If not， you might add some digits with different orientations。

Is your training set representative for the test cases。

 So is the distribution of your training input roughly the same as the distribution of your test inputs。

And this is often not the case。 So， for example， if you want to protect whether certain customers like a certain project product。

And you do a questionnaire with students。 And， of course， you haven't covered all your customers。

S a simple different situation for assembling bias， like in the midterm。

 we typically do the evaluation for the lectures， you get all the questionnaireers。

 we collect opinions like in most cases， they are not really bad。😊。

But maybe that is not so surprising because the students who really didn't like the lecture by the midterm have already left。

So theres a strong sampling bias towards positive evaluations。At least， I mean。

 at least there's a biasson we can now start abating astrons and where it hurts us。

 And if you now were supposed to make a prediction， for example。

 for the dropout rate for a class based on this midterm evaluation。

 maybe it's not so easy to solve this problem because you you lost half of your data already。😊。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_85.png)

Much more subtle a credit scoring rules， here's yet another example。

 and I think we might have mentioned this in the in the lecture on the social impact， but if not。

 maybe you might want to listen to this example once more。😊。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_87.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_88.png)

So credits scoring rules， as I guess all of you know， like typically banks apply these rules。

 a customer comes and asks for a credit for a house and then the bank needs to decide whether the bank is going to give the credit to the customer or not。

😊，So the bank is supposed like internally， the bank wants to predict whether the customer is going to be able to pay back the credit or not。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_90.png)

AndNow， of course， what is the training data they can train your algorithm on and they can only train their algorithm on the customers to which they have given the credit。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_92.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_93.png)

So here is an image of this situation， So we have all potential customers。😊。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_95.png)

This is the green set here。 These are all the customers for which we want to make a prediction whether they are worthy to credit or not。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_97.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_98.png)

Now， how did now the problem is we don't really have collected data on all potential customers。

 What is the data the bank has。Like in the past， the bank decided for certain customers that they get the credit。

 This is the top arrow here。And and for those customers。

 the bank knows whether they paid back the credit or not。However。

 there's this large group of customers who did not get the credit in the first place。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_100.png)

And for those customers， that the bank doesn't have any data。

 They don't know maybe some of these customers would very well have paid back their credit。

 whereas some others also wouldn't have paid it back， as the bank believed。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_102.png)

So if we now train our machine learning algorithms just on this threat population here。😊。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_104.png)

There's a very， very strong bias in this population towards the people that the bank in the first place in the historic data found worthy of a credit。

 And by no means it's a representative sample。So as a machine at this point。

 you need to ask yourself how can you counteract this particular effect。

 there might be no very many different approaches， and I don't want to discuss。

 you could try to collect additional data you could try to run randomized experiments you could try to try to post process your data and correct for these effects。

 I mean， there are many different things， but you at least should be aware of the fact that this data is not representative。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_106.png)

Now， the next step is typically once you have your raw data。

 you need to convert it to what we would call the training data。😊。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_108.png)

And typically， there is a considerable amount of decisions that go into that。For example， here。

 I have an example for face detection and images。So when you use face detect， like it's not about。

 So the question is simply here's an image。 And the question is。

 the question the machine learning algorithm is supposed to answer。

 is there a face on this image or not。And now you have cat training data。

 you have images with faces on them or not。 But what exactly do you now use as training data。

 Do you use the whole images。Or do you use sort of little parts of your images in a sliding window of fashion。

 so you always look at small parts and you rather classify is does this small part contain a piece of an image or not？

😊，How large are these patch supposed to be？Which representation of the image do you use。

 Do you use sort of a pixel based representation， Which colour space， Which resolution， I mean。

 there are millions and millions of choices that you have to make。

 And these are definitely going to influence your your learning algorithm。

 What do you do with different brightnesses。 So some figures。

 some pictures might have been taken in the evening。

 some in the morning or in full sunlight around noon。They have very different characteristics。

 Do you want to have all of them in your training set and are all of them in in the test as well。

 or is the test maybe different。Lots of design decision。The next step， data cleaning， missing values。

 outliers。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_110.png)

So data often contains outliers。 And here is a definition。 Well， it's a pseudo definition。

 maybe an outlier an observation which devs so much from the other observations as to arouse suspicions that it was generated by a different mechanism。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_112.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_113.png)

It could be like if you're in physics and you have a measurement device。

 maybe the device was broken and for some reason didn't really recall the correct result。

Or you ask people， you do a mechanical turk experiment and you want to know whether people are randomly clicking or not。

 So there might be an outli if someone is just randomly clicking。And there might be many。

 many reasons for which a measurement might fail。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_115.png)

But many of the machine learning algorithms are influenced heavily by by outliers。 I mean。

 just consider， I don't know。 Pri component analysis。 If you have some outlier points。

 your result looks very different than if you don't have outliers。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_117.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_118.png)

And now the question is， do we want to remove the outliers or what do we do about them？



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_120.png)

So you might， in some cases， you might want to remove the outliers。

 and there are millions of algorithms for outlier detection。

 And I don't want to recommend any particular one because it would really depend on your data。

 But here are some。Just keywords the classical statistics or a model based approach what you do is you fit say like in particular。

 if you have measurement from a physical device， for example you could say I mean my measurement error is normally distributed so what you do is you fit a mixture of gas to your data。

😊。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_122.png)

And then outliers are points which have a low， very low probability under this model。

 So say you fit a normal distribution and the points sits here。 It is so， so。

 so unlikely that this normal distribution generated this data point that you would say this data point is an outlier。

 and you might want to remove it。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_124.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_125.png)

However， for machine learning， this typically doesn't work because we， as you know。

 we don't work with， at least typically， we don't work with probabilistic assumptions in our data。

 at least not in our lecture。 There are other lectures where you discuss it， but not in our ones。

So typically， what you would do is a model free approach where you say。

I sort of want to fit a set to my data and the set contains most of my dataset set and everything now that's out of the set。

 I simply consider it as an outlier。So formally， you want to fit a set S that is as small as possible。

 but contains most of your data points。And then you have to find such a set S and again。

 there are many， many different approaches which you could use， and this defines outliers。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_127.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_128.png)

I mean， just one example， the one class support vector machine and like in the context of the algorithm that we have seen。

 but there are many， many more。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_130.png)

What is really important here is that there is no right or wrong when you talk about outlier detection and outli like removing outliers。

And I mean， first of all， depending on the different different definitions。

 points are considered an outline in one definition and not an outline in and a different definition。

 So it's not there's not the unique way to say something is an outlier。嗯。

The other thing to observe is that outlays are not always bad and undesired。

Sometimes these outlets are also the points that are really important。 and that by all means。

 you should not remove。For example， in a medical example。

 there might be sort of a group of patients and all of them react sort of similarly that's sort of the main group of patients。

 And then there's this one patient who react completely different。 Now you can of course say， well。

 he's an out。 I'm not going to consider him anymore。

 but maybe this is really an important case that you haven't observed so far。

 And this would be something you should definitely watch out for very carefully and decide what you need to do like what is is specific about this patient why the treatment。

 for example， didn't really work。😊，And if you throw out the outliers in the beginning and even in particular。

 if you do it blindly， then this information is completely gone。 And in particular。

 in the medical domain say you want to test a new a new。I don't know vaccine。

 say COVID vaccination while we're at it， and someone dies。

 he might be an outlier because all the other 10，000 people have not died。

 but this is the person you are really interested in because you might want to know how many people die if they get this vaccination。

Okay， and here's sort of a general piece of advice。

 be suspicious if people generously remove outliers。😊，And often， well， if。

 if there are things that are obvious outliers go ahead， but if not。

 maybe try to carefully try to design your algorithm。Maybe run it once with outliers。

 once without outliers to really make sure that you know what you're doing here。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_132.png)

The next issue that will always come up missing values。 So in many cases， the data is not complete。

And now the question is， what do you do？And there are two different cases that are typically being distinguished also in statistics or economy or wherever you look at these kind of problems。

There might be。Data that is missing at random。 So from time to time。

 the measurement devices and error， the data is missing。

 and it simply hasn't been recorded for some reason。 But this is sort of randomly happens。

Maybe that's not such a big deal。But then there might be this data which is missing not at random。

 so where values systematically are not in your dataset。For example， just it's a stupid example。

 but assume you run a population survey and then there's a question how much do you earn？

And some people simply might want not want to say how much they earn Maybe either they earn so much that they that they don't want to put it in the questionnaire or theyre ashamed because they don't they earn so little that they also don't want to put it in the questionnaire。

 And then maybe people in the medium range。We put the numbers。

But the two extremes are going to be missing。 And this is not at random。 So you can't simply。

 And if you now would say you impute the values by sort of taking the average value of this intermediate regime。

 Of course， you do something that's completely stupid。And again。

 there is no standard recipe what you can do。 Of course。

 you can try to throw away entries that are corrupted。If these are only few entries。Again。

 still asking yourself whether what you throw away is important is， in fact。

 an important piece of evidence。You could try to impute the missing values。 There are many ways。

 and some of the algorithms can， in fact， also deal with the fact that some values are missing。

 You might also want to use one of those algorithms。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_134.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_135.png)

So the next thing you might you need to do is you need to define like feature similarity functions。

 distance functions and all these things。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_137.png)

So features， I mean， the general rule of sum that I've also mentioned maybe several times during the lectures。

 Like if you， if you say you have a feature based abroad， you want to classify。Fruits。

 according to whether they taste well or don't taste well。Simply include many， many features。

 All the features that you can come up with and then see what the algorithm is going to make out of it。

 So this is my second point。 here， don't be shy， including features。 If， in doubt。

 include the question number feature and many supervised algorithms like support vector machines are good at finding out which are the features that are really important。

😊，Often， but not always， of course。Also， make sure that the features you choose are not completely stupid。

 so if you want to classify text into different topics。😊，If you use a bag of words。

 that's definitely something where we would say yes。

 it makes perfect sense like if a text is about sports。

 it contains different words than if a text is about politics。😊。

But a back of letters would not be reasonable if you say this text has so many A's and so many B's。

 So the important information is not encoded here。And while this is obvious for texts and words and letters。

 this is often not so obvious in other applications。😊，Choosing features can be a very tough problem。

And in the past， like before deep neural networks came up。

 the whole computer vision community was busy with trying to construct very good features for objective detection。

😊，So they so the question there was， of course， like typically you can't like object detection was not successful at least at that time。

 when you would feed the raw pixel values into your algorithm。

 you would need to construct all these features that extract edges， for example。

 or si features there are lots of different statistics， local statistics that people try to extract。

😊，Which was。Which， which went beyond simple the， the。

 the natural features that you would come up with。 like。

 if you just think about the problem for 10 minutes。I mean， by now this is not like for images。

 this is not so important anymore because deep networks do very differently and they work on the raw figures with raw images。

 but at that time。😊，really， there was， a whole community busy。With trying to identify good features。

An important topic is also to deal with categorial features。 So sometimes， so， for example。

 coming back to this example of the fruits and whether they take taste nice or not， you can。

 of course， have lots of numerical features like how large is the food。

 How much does what's the weight of the food and so on。 So these are sort of real valued numbers。

But then you might also have discrete discrete features like。

 does it grow on a tree or does it does it not grow on a tree， or I don't know。And here， for example。

 here， I have like the example I have here。 you might also have discrete categories like for books。

 It's a detective story and of a children's book。So these are discrete features。

 but not the continuous numbers。 And if you have both of these things。😊。

Then it's often important how to encode it。And in this particular example that I have here on the slide about the books。

 the native， like if you would do it naively without thinking about it， you would say， well。

 I simply give a number to each of these categories。 Detective story is one。 novel is two。

 children's book is three and so on。😊，However， what is going to happen now is really bad。Because。

Like if you have a machine learning algorithm and， for example， you。

 you have this feature vector that encodes these features in this way。 and。

 and then you use like a kernel algorithm。 It is going to， to compute the similarity。 sorry。

The similarity between different vectors， according to the distance of the features。

And so according to this distance function， a detective story is closer to a novel than a detective story is to a children's book。

😊，But this was not what you wanted to encode when you simply gave random numbers to all these kind of categories。

嗯。And but the machine learning algorithm is going to interpret these distances。

So this is really not a good idea。So what you typically do is use binary incodings and for each of the categories you introduce one yes no feature So you say is it a detective story。

 yes oh no0 or1 I it an novel0 or1 is it a children's book01 and then at least so you have like your vector gets very long then and it's a very sparse because maybe you have 20 different categories and 19 of them are0 and one has a one in each of these vectors but at least they are treated in the same symmetric way。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_139.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_140.png)

Sometimes like the next thing is， what do you do when when your feature vectors are very sparse。

 This is also something that might might run where you might run into problems because。I mean。

 you can simply observe that most of your vector is empty and then there are a few nonze entries for many algorithms this is a problem。

But obviously， the future vector is sparse very often。 For example。

 if we have a bag of birds approach。😊，For text analysis， we have say，10000 birds in our dictionary。

 but the text only has 300 w。 Then this feature vector is going to be sparse。Now。

 there are many different things that you can do。 You could， for example， first of all。

 reduce the dimensionality use principle component analysis or SVD， something like that。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_142.png)

You could also try to reduce the number of features by building these junctive features of a number of features。

So you for example， you can replace two features by one feature that contains the sum of the two or the logical disjunction or conjunction of two features。

But and then there are also fancy approaches， but I don't think this approach this particular one is very popular。

 but you could sort of try to find some hash function like apply a hash function first and then you have like hash you a very long vector of a sparse feature vector to some much shorter vector that is not sparse anymore and then use machine running on this shorter vector。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_144.png)

Once you have your features out there， you might want to define a similarity or a kernel or distance function。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_146.png)

And this， again， is sort of one of the keys where machine learning can very often go wrong。😊。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_148.png)

So essentially all machine learning algorithms use the principle。😊。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_150.png)

That points which are similar in the input space should also get a similar label in the output space or should end up in the same cluster in the output space。

So so this encoding of similarity really has a lot of influence。嗯。

This is also the place where you can provide prior knowledge to your machine learning algorithm。

For example， if you want to classify proteins， maybe it' is not such a good idea to use as a distance function sort of the distance between the amino acid strings。

😊。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_152.png)

Because this is not really what determines the chemical function of a protein。

 you need to describe the protein maybe in the three dimensional structure in some complicated way and then compute distance between two proteins because this is going to express sort of what is important for the functionality of a certain protein。

So this is really crucial and this is where the expert knowledge domain knowledge needs to go into and if you are a machine learner you need to talk to the domain experts to find out what are really the important things。

 the features to take into account and the similarity functions to use to include what the domains would consider is a good similarity function。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_154.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_155.png)

嗯。Okay， I think this is， I mean， I've already mentioned this in a kernel approach or distance a similarity based approach you can build in knowledge and you need to make sure that similar points in the input space get a similar output。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_157.png)

Here's the example of bioinformatics once more if you want to classify a protein as dgable or not drugable sort of the two- dimensionsal structure is not important。

 you need to look at sort of these pockets something you have in the three dimensionsal shape of a protein and you need to describe this little pocket and you need to find out whether this other molecule。

😊。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_159.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_160.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_161.png)

The drug can bind to this particular pocket of the protein。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_163.png)

I I think I've mentioned this already。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_165.png)

Another thing， I mean， this sounds stupid， but these things always happen all the time。

 If you want to define the similarity between 20written0 digits。

 the color of the pen in which the digit has been written is not important。

 whether this is green or red or blue， it does't matter。

 What matters is like which of these pickles have color on them and which don't have color on them。

 So by all means you need to make sure that this distance function does not spit out a large distance。

 if you have two like similar similar digits， but written in a different color。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_167.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_168.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_169.png)

The next question， should I reduce the number of training points。

Sometimes the data set that you have is too big， so if you want to use a kernel approach and you have millions of data points and your approach would be to compute the kernel matrix of a million to a million data points。

 good luck， this is not going to end up at least not on your laptop and you can now spend a lot of effort trying to sort of try to put this on a cluster in a distributed fashion like putting different parts of your matrix in different nodes and so on。

 this is going to be really complicated。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_171.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_172.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_173.png)

Sometimes it's a good idea to simply subs samplele your data because it the data might be strong enough。

 even if you work on a smaller data set。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_175.png)

And typically there are a number of approaches you can use subseling。

 so you randomly select a subset of the points from your original data。

You might want to repeat this a couple of times。 but the good thing about this approach is that the distribution of the data。

 at least。Its the same as the one of the original dataset set。However。

 you might have lost some outliers you might have lost also like if you have small groups in your data set。

 like minorityator populations， for example， they might get lost if you if you use this particular approach。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_177.png)

The other approach that typically is done is some kind of vector quantization here you。😊。

Where you do something like you run an algorithm to select representative points from your dataset and typically use K means。

 you have your data， you use K means with a large number of k。

 So you have a million dataset sets and you now want to select 1000 representative customers。

 So you you run K means with1000。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_179.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_180.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_181.png)

For1 thousand0 clusters。嗯。And then you work on the new data， on the， on the representatives。

What happens here is， and this is something you can prove。

 and we have also looked at this in some past paper of mine。

This approach is going to introduce distortion the to the distribution。

 so the distribution is not the same。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_183.png)

Like the data distribution is not the same after applying cames。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_185.png)

Because what happens is you put more。More weight towards outliers because Kmin is still going like if there' is an outlinelier and a data set K means will put a center on it。

 So in the extreme case， say you have a lot of data points which are sort of somewhere centered say say in a Gaussian distribution close to the origin and then you have a couple of outliers now if you run Kmin with k equals 1000。

 probably all these outliers are going to get a center。

Because the cost for Kmins to not giving them a center would be really high because this outlier distance is going to enter the cost function。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_187.png)

So what this algorithm does is more weights is going to be shifted in regions of the space where you tend to where you originally had less weight。

😊，This is also something to be aware of， but still it's an approach that is taken very often。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_189.png)

Now， what you can do is you can use dimensionality to reduction。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_191.png)

We have seen many approaches for dimensionality reduction。Typically， I mean。

 you can use unsupervised dimension other2 reduction。

Which is what we have already discussed in the lecture in the past。

 and it's going to be summarized on the next slide。

 but we can also use supervised dimensionality reduction， which is in fact， called feature selection。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_193.png)

So unsupervised dimensionality reduction is something like PCA or SVD and or kernel PC， if you like。

 this is sort of Z approach that is used by like。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_195.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_196.png)

In many， in many data sets， people simply out of the box use PCA to get rid of some of your data imagess。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_198.png)

You can also use something like ISOmap or Johnson Lyinton Charles random projections and so on。

 these are not so popular I mean in theory they are always really nice in practice they are not extremely popular at least as far as I know。

😊，Again， there are many， many methods out there you might want to play with them in particular if you know something about the structure of your dataset。

 for example， the structure of your dataset is such that PCA doesn't really make sense then maybe better not use it。

嗯。This dimensionality reduction is always like it's a step that often helps。

 but it can also hurt considerably because it might destroy the structure that is in your data。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_200.png)

Data standardization， I think we've mentioned this， it is very common to use data standardization。

 at least if youre in a feature based approach to center and normalize your data and it typically does not hurt。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_202.png)

In， there might be different algorithms where this data standardization is not so simple。

As we have also seen in Car PC A。 So then you need to consider whether you really want to do it or not。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_204.png)

Clluing。Cling for glassing， they exist two purposes。

1 I've already mentioned this is this kind of vector quantization approach。😊，The other one is。

 you might want to split your data into meaningful subgroups。

Because you maybe think you are in a medical domain and you think there are different subgroups of patients and all the analysis that you're going to run in the future should be a different one for the different subgroups of patients。

😊。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_206.png)

So then it might make sense to first of all cluster the data。That you have。The advantages， of course。

 within each of these groups also I mean it's more coherent and there are less data points in each of these groups。

 so this might be of advantage for lots of machine learning methods。😊，嗯。And then again。

 the question is like what is sort of the number of clusters。

 are we looking for five clusters then you can sort of apply a machine learning algorithm。

 try to look at the data sets and very carefully try to select it。😊。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_208.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_209.png)

If you're going to select 500 clusters， maybe it' is not so crucial which exactly kind of clusters you use。

😊。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_211.png)

Then you can do something by K means。Okay， the next thing we need to set up the learning program。

 we need to choose a loss function。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_213.png)

嗯。The default function for loss function for classification is01 loss。

 but there are many many cases where you need to be a bit careful about。

The first and very common thing is unbalanced classes。

 So if you're in this medical domain and you have， I don't know。

 this group of patients and this other group of patients and in this group of patients。

 you have 100 people in Hehen have only 10。Then you need to be really careful。

Because and these 10 maybe be， like if you in the N just look at the average error of your classifier。

 these 10 don't really count。 So the algorithm is going to make sure that the classification is being correct on the majority of the patients and these other 10。

 maybe they get lost。嗯。So to circumvent this problem。

 you have to rer the loss function such as the training errors of these minority class get much。

 much more weight than the training errors that happen on this majority class here。😊。

So you could just use a like in the simplest case， you can try to introduce a factor in your loss function where you just say depending on whether the true label is -1 or plus one。

 you use a different value in the loss function。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_215.png)

You could also look at the importance weighted classification。😊。

Where you care much more about a certain class of customers than others， for example， good customers。

 Again， you are going to introduce a weight。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_217.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_218.png)

Cost sensitive classification in many applications。

 the kind of errors that we make are not symmetric。

 and the prime example here is spm detection or a spam classification。

 If there is an email that is a spam email， but it ends up in your inbox。

 well it's annoying but not really bad， but if there this important email that gets filtered out before you see it。

 and this was sort of a very important email that you've been waiting for this damage can be considerable。

😊，So then again， you might want to to adapt your loss function to this particular scenario。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_220.png)

Typically， there is also like like in at least in classification。

 the standard loss function are discrete， and this is typically hard to optimize。

 and we have seen that many machine learning algorithms use different kind of loss functions like the hinge loss or the exponential loss or whatever。

😊。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_222.png)

And these are called surrogate loss function。And again。

 there's a whole theory of surrogate loss functions。

Where the main key is how different are the results going to be if I apply this surrogate loss function instead of the loss function that I actually want to look at。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_224.png)

If you want to go that way， I mean， the first thing you might want to look for is whether a surrogate loss function is convex。

 at least in this traditional kind of machine learning setting in deep networks。

 it's different and in probabilistic learning is also different。 but here in our domain。

We make our life easier if the loss function is convex， because otherwise， I mean。

 we still have a problem of， of trying to optimize。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_226.png)

Then you might want to check with them。Los functions are proper and classification calibrated these are。

Two slightly different definitions， but they try to ensure that that the minimum that you are going to find by minimizing a loss function is sort of the same。

 So here we see an example where we have this red， which is the original loss function。

 which is not convex， which is being replaced by this blue loss function。

 and you don't really care whether these two functions are closed or not as long as the minimum occurs at the same kind of place。

😊。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_228.png)

嗯。Okay， and this is like this this field of research about different loss functions that also there is still lots of recent work going on in this field you can try to check the publication and Bob Williams and Peter Bart。

 there are many more people in this field who work on this particular field of research。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_230.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_231.png)

Training。In very few cases， your classification problem is a binary classification problem。 In many。

 many other cases， in applications， you have problems which are multiclass problems。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_233.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_234.png)

Now， if you have extreme classification problems where you have one versus 5 million other classes。

 then there is something you need to do about it and I'm not going to discuss that here you need to do something that is much more involved。

😊，But for sort of normal procedures in a medical domain， maybe you have five different outcomes。

 and there are two different approaches that you need to be aware of。😊。

When you have multiple classes， the one versus all and the one versus one approach the one versus like is in both approaches。

 what you do is you boil down your problem to binary classification problems。

And in the one versus all problem， you always try test or you try to classify。

 is it in this class or in any of the other classes， so for example。

 if you have 10 digit recognitions we have 10 digits and we train 10 classifiers。😊。

The first classifier says is it a one or not， the second one says。

 is it a two or is it something else， is it a three or something else and so on。

 so you train 10 classifiers and then you choose the one which is most certain about the classification of its own digit。

😊，That's one versus all。The one versus  one is where you do this in a binary fashion。

 So if you have k classes in the first in the one versus all class case。

 you end up with training K class first in the one versus one， you train。😊。

K times k classifierifies or K times K times k minus-1 half。 if you want。

 you train each classifier against each other each class against each other class。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_236.png)

And then you do some kind of majority board。In theory。

 there's not much that distinction between the two approaches， like in theory。

 both of them tend to work。😊。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_238.png)

In practice， of course， the computational resources are very different from each other and。

As I said here， this is an active field of research in particular。

 if the number of classes is really high。😊。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_240.png)

Cross validation， we have covered cross validationation in the lecture already。

 so I can skip most of the slides here。😊。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_242.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_243.png)

嗯。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_245.png)

However， I want to mention one thing or one study that has been come out last year in Europes which is about a meta study of whether cross validation really works or not。

If you remember cross validation， I think the key point that I also mentioned in my lecture is that you're not supposed。

To train and test on the same data。 So if you train your data。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_247.png)

You classify on a data， you test it， you're not satisfied and go back。

 then this training this testing set is spoil。😊，Of course， I mean。

 that's nice from a theoreticaloretic point。 if in practice is that that is what happens all the time。

 I mean， you just have a finite amount of training set。

 you don't have like independently arbitrarily many different training sets。 So in particular。

 if you need to retrain your algorithm to tune parameters and so on， this happens very often。😊。

And the question that has been asked in this recent line of work was whether this really hurts or not。

And I want to simply discuss one paper about this question， which was in Europe's 2019。

 and it was called a meta analysis of overfitting in machine learning。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_249.png)

And so essentially， what the authors did is they looked at past k competitions and tried to find out whether overfitting happened due to this kind of tests that we use。

😊。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_251.png)

So what they did is， I mean。I hope everybody knows what Ka is。

 It's this platform where you can post machine running competitions。 So， for example， if you have a。

 if you have a company and you're interested in finding out what is the best algorithm to classify my customers。

 you can put some training data on there。 you put some evaluation procedure。 And then you say。

 I give the person who gets the best result gets 1000 bucks。

 And then you sort of let it go and wait for the best result。😊。

And the point is that lots of data on this k platforms is available and you can use it as a as。

 as a data data set to ask this meta question about overfitting。

So the authors looked at the cattle competitions， and。

Now you need to look a bit more closely into how that works。😊。

Like typically in such a competition you can test your results on a public test set。😊。

And these are also the resultss that are being announced constantly on the leaderboard。

 so typically there's a leaderboard that says， oh currently this group is better and than this other group。

 but the competition maybe runs for two more weeks and then you can always check on the leaderboard where you are。

😊，And then after this competition time is over， they close it and then the results are being evaluated on a private test set once and finally。

 and this test set has not been seen to anybody before。😊。

It ended sort of the people who set up the competition keep that in secret until the final。

 final final test。And so now this difference in the public and private test errors can serve as some kind of at least approximation to estimate the effect of overfitting because if the public testing error is much。

 much lower than the one that we have in the end， it means people have overfitted to the public training set。

😊，And in particular， one might expect that overfitting happens if people resubmit very。

 very often and really try hard to win the competitions， as it， for example。

 was the case in this Netflix Netflix competition like 10 years ago or 15 years ago。

 where people could win  euro 1 millions， I guess， it's prize money。😊，And essentially， the result。

 which was， I guess， also a bit surprising to the authors because I think they suspected something else was that overfitting does not seem to be such a big problem as one might consider。

😊。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_253.png)

In most， but not in all the studies， there was a surprisingly small difference between the public and the private training set I tested。

 sorry。😊，This is a really cool paper。 I recommend you read it if you want to find out more。

 I don't want to go into any more details here。😊。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_255.png)

Yes， I think I've discussed the advantages of disadvantages of cross validation。 and already。

 it's computationally expensive。From a theoretical statement， it's also annoying， but in the end。

 there' is nothing else you can really do。 So when you want to set parameters。

 you need to to use cross validation because there's no other principle procedure that is going to achieve similarly good resultss。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_257.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_258.png)

So， this was。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_260.png)

Like one aspect of feature selection。 Now， there's this other aspect of feature selection。

 which is the more active approach where you try to。

 to select features like you have a set of of a million features and you want to select the first 20 features that gives the best results for your machine learning albums。

 Again， there's lots of literature here。 You can look at it。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_262.png)

Just let me give you the brief insight so we assume we assume we have a very high dimensional data vector and we want to reduce that dimensionality。

😊。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_264.png)

And we don't want to use， obviously， classification accuracy。And there might be reasons。

 might because of dimensionality， computational reasons。

 or maybe also because explainability we want to understand or classify。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_266.png)

So now， of course， the theoretically optimal approach would be we take all possible subsets of features。

 train， say a support vector machine， test it and then choose the set of features。

 which gives us the best test result。😊，This obviously is not a good idea。

 And I hope that all of you see immediately why， If not， please think about it for a second。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_268.png)

And now there are two different approaches which at least have been advocated in the past for future selection。

 which is filter and wrap approaches in a filter approach。

 the the approach is the first the following， you take the training data and by training data I mean points and the labels。

😊，And you try to identify good features just based on this data the and then you train your classifiers with the good features only。

嗯。And for example， like in the simplest case， you can look at the correlation between sort of the training label and the feature。

 and then you just include features which have a high correlation。I mean。

 this is just the simplest approach。 There are many more approaches out there。The other approach。

They are fast。Faster than the wrap approaches that we're going to see in a minute。Interally。

 they are also less prone to overfitting， but of course。

 this also has a disadvantage that we don't even take into account which kind of classifier we use in the end。

 so maybe a feature is very correlated with the outcome but depending on the classifier or the similarity of the kernel function that we use。

 choosing different features might have been better。😊。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_270.png)

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_271.png)

And typically what the way this works and the filter method is you try to compute some kind of dependency store a score。

😊，嗯。Between features and labels。 So what is important to understand here is that this kind of feature selection is supervised because we use the label information to select the features。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_273.png)

So， this is different。As other methods where we randomly select certain features， for example。

 without looking at the labels。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_275.png)

Okay， and then you there are lots of scores which you can use。 You can look at correlation。

 Fs information， other information Theoretic measures。 There's a wide variety out of， of。

 of scores that you can compute。

![](img/5a5d0c1ee86ef27f59165bd066ca08d0_277.png)

And typically you do this in a very straightforward way， you start with an empty set。

 then you add the best of the remaining features and you do this as long as you are satisfied with a number of features。

😊，What is bad is about this is that。Because you treat features individually。

 sometimes it's the case that two features are jointly important。 So， for example。

 it might be that for some medical situation， it is important to have two particular genes。

Each of these genes is not indicative for a certain disease。

 but the combination of the two genes might be indicative。

 and this is something you might not be able to find here。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_279.png)

The other thing that you can do are wrap methods which also involves the classification algorithm。

 so typically what you do is the following your train and class with different sets of features to computer consolidation error and then to select the final set of features you use the smallest feature set that was still good enough to produce a good result。

😊，The advantage is that we only select features that are really important also with respect to our learning algorithm that we use。

 but computationally， of course， this is really might be a disaster because you can't just reach any algorithm millions of times。

 at least if you have many features， this is really expensive。

And it is also very prone to overfitting。 so it could be that the feature selection。😊，嗯。

Method is sort of， I mean。From a theoretical point of view。

 we can interpret it as a large blow up of the hypothesis space because now not only do you have to do say you classify as a projector machine you have hyperplans。

 but now you have hyperplans。😊，As a combination with all the different feature sets。

 So the the space of different hypotheses explodes。

 and then maybe also the capacity of your function class gets too large so you can easily overfi here。

😊，Which is not what can at least in the filter methods， it doesn't happen so easily。



![](img/5a5d0c1ee86ef27f59165bd066ca08d0_281.png)