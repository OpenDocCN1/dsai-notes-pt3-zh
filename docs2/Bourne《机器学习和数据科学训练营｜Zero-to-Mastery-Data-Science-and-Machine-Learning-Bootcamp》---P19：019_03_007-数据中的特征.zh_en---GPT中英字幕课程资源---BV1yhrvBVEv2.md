# Bourne《机器学习和数据科学训练营｜Zero to Mastery Data Science and Machine Learning Bootcamp》 - P19：019_03_007 数据中的特征.zh_en - GPT中英字幕课程资源 - BV1yhrvBVEv2

![](img/0642b1c0e15bf0ad58e1d4d23776e9a4_0.png)

We've gone through step 1， problem definition。 We've gone through step 2， data and step 3。

 we've defined what success means for us。 Now let's get on to step 4， which is。Features。Now here。

 the question we're trying to answer is， what do we already know about the data？

Now if you haven't worked with data before， you might hear this word features and be wondering what the elderers's features mean。

Well， you'll hear this world come up a lot in machine learning。

 maybe in the form of feature learning or feature variables or when someone asks。

 how many features are there or what kind of features are there？

Features is another word for different forms of data Now we've already discussed different kinds of data such as structured and unstructured。

 but features refers to the different forms of data within structured or unstructured data For example。

 let's go back to our predicting heart disease problem。

We might want to see if things such as a person's body weight， their sex。

 their addressing heart rate， and their chest pain rating can be used to predict if they have heart disease or not。

These three things are patient's body weight， sex， average addressing heart rate and chest pain are features of the data。

They could also be referred to as feature variables。 In other words。

 we want to use the feature variables。To predict the target variables。

 which is whether or not a person has heart disease or not。Now， when it comes to feature variables。

 again， there are different kinds you've got numerical， which means a number like bodyway。

 there's categorical， which means one thing or another like sex or whether a patient is a smoker or not。

And then there's derived， which is when someone like yourself looks at the data and creates a new feature using the existing ones。

😊，For example， you might look at someone's hospital visit history timests。

 and if they've had a visit in the last year， you could make a categorical feature called visited in last year。

😊，If someone had visited in the last year， they would get true。 or in our case， yes， if not。

 they would get false or in this case， no。The process of deriving features like this out of data is often referred to as feature engineering。

Our heart disease example is structure， but unstructured data has features， too。

 They're just a little less obvious。 If you looked at enough images of dogs。

 you'd start to figure out， okay， most of these creatures have four shapes coming out of their body。

 Their legs and a couple of circles up the front。 Their eyes。

As a machine learning algorithm looks at different images。

 it would start to learn these different shapes and much more and figure out how different pictures are similar or different to each other。

😊，Don't worry when it comes to figuring out the different patterns between features。

 such as the four rectangle sort of shapes coming out of a dog's body or the circles at the front of the dog's head。

You don't have to tell the machine learning algorithm what they are。

 The beautiful thing is it figures them out on its own。😊。

The final thing to remember is a feature works best within a machine learning algorithm if many of the samples have it。

For our predicting heart disease problem， say we had a feature which was called most Eden Foods。

 which had a list of the foods the patient ate most often。

But only 10% or 10 out of 100 patient records had it。

 so this one ID for patient ID 4328 has most eaten food which is fries not ideal and these other patients don't have it because remember only 10 out of 100 examples have the most eaten food they have data here so these ones are just missing and that'll be the same so if you can imagine there's 100 patients here。

 only 10 of them will have this most eaten food column field。

And since a machine learning algorithm learns best when all samples have similar information。

 we'd either leave this one out or try to collect more information before using it。😊。

The process of ensuring all samples have similar information is called feature coverage in an ideal data set。

 you've got complete feature coverage， so for us to want to be able to use this feature of most eaten foods。

 ideally we'd want all values here or at least more than 10% coverage。

 which means that over 10% or over 10 and 100 examples， have some sort of value in this column。😊。

We'll have plenty of practice looking at different features in coming lectures and projects and lessons。

 In the meantime， think about a problem you had to solve recently。 What features went into it。

Were they numerical or categorical， or did you combine them into your own derived feature？



![](img/0642b1c0e15bf0ad58e1d4d23776e9a4_2.png)