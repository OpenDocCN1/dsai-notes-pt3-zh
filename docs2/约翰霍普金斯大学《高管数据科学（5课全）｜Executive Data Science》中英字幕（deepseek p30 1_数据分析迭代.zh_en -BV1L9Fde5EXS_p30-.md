# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p30 1_数据分析迭代.zh_en -BV1L9Fde5EXS_p30-

Yeah。

![](img/666d22d07dceb91b01388b2e091a3fda_1.png)

This lecture is going to provide an overview of the cycle of data analysis。

Data analysis is a complex process that can involve many pieces and many different tools。

 but fundamentally there are only three parts to it really。The first part is setting expectations。

 Second part involves collecting information and comparing your expectations to data。

 And the last part involves reacting to data and revising your expectations。 So that's basically it。

 Those are the three parts of data analysis that you often will cycle through many times in the course of analyzing any given data set。

 So I'm going break down each one of these pieces to give you a little bit of a description of what they are。

 And I'll give you a little example of kind of how they might be applied in the real world。 so。



![](img/666d22d07dceb91b01388b2e091a3fda_3.png)

![](img/666d22d07dceb91b01388b2e091a3fda_4.png)

Setting expectations involves deliberately thinking about what you're going to do before you do it Now the idea in any part of data analysis is that everything you do is going to have some sort of consequence whether it's collecting data。

 whether it's fitting a model or whether it's asking a question or whether it's making some sort of plot。

 everything you do there will be some sort of action and the point is that you want to think about what that consequence is going to be。

 before you do it and in that way you set the expectations for yourself and you can determine kind of what whether the reality kind of meets that expectation right。

So that's the first part of the data analysis cycle once you've set your expectations。

 the next thing you want to do is collect some data or collect some information that will allow you to compare those expectations to reality so collecting that information is key because it'll tell you whether or not your expectations were right to whether they were wrong。

 whether theyre too high， too low whatever it is depending on the problem you're working on and then once you've collected that information and compare it to your expectations。

 you can react to it and maybe change your behavior in some way so the last part of the data analysis cycle is to think about what have we learned from the data from our expectations in their comparison what would we do differently next time did we match our expectations。

 did they not match why or why not so that's the third part and then once you've completed the third part and you've revised your expectations you may go back with these revised expectations。

And collect more data and try to match them up again。

 And then this iteration continues often from many different times in any given data analysis。

So I just want to give you a quick example of how you can use these three components in a kind of a generic or kind of commonplace setting So the basic example I'm going present here is going out to dinner with your friends so suppose you're going out to dinner and the restaurant you're going to is a cash only at place So the question you have to ask yourself is how much money should you bring and the basic activity that you're going to engage in is eating a meal and then you're going to get a check for the bill and you're gonna have to pay money to pay for the meal so but before you do that you got to figure out how much money you're going bring and so what you have to think about what's your expectation for the cost of this meal okay maybe you dine at this restaurant all the time so you know exactly how much is going cost maybe you know well in this city the typical meal costs this many dollars and so I'll just bring that much money because that's this is an average kind of restaurant maybe you know okay well the most expensive restaurant in this。



![](img/666d22d07dceb91b01388b2e091a3fda_6.png)

![](img/666d22d07dceb91b01388b2e091a3fda_7.png)

City cost this many dollars。 So I know it's not going cost this more than that。

 So I'll just bring that to kind of serve as an upper bound on how much money I might be end up spending at this restaurant。

 you might ask your friends if they've been there before。

 how much this place costs or you might Google the restaurant and maybe look up the menu to see kind of what the meal typically costs there at any rate。

 before you've gone to the restaurant and eating the meal。

 you can use any sort of a priori information to set up your expectations for what the cost is ultimately going to be。

 And before you observe the real thing So once you've set your expectations you can。

 you can figure out how much money to bring the actual collecting of the data involves going to the restaurant and getting the check so once you've gotten the check you've observed the reality of what the meal costs and there's a couple there's two possibilities。

 one is that that cost meets your expectation So suppose you thought it was gonna be $30 and it ended up being $30 then。



![](img/666d22d07dceb91b01388b2e091a3fda_9.png)

![](img/666d22d07dceb91b01388b2e091a3fda_10.png)

![](img/666d22d07dceb91b01388b2e091a3fda_11.png)

That's great。 And you know exactly， know， you brought the right amount of money and you know and that you can pay for the meal。

 The other possibility is that the expectations don't match what the reality is。

 So example when maybe you thought it was $30 and it ended up being $40 And so you have to ask yourself then why do you have that mismatch。

 Why is it that you thought it was $30 and the meal turned out to be $40。

 So there's two possibilities。 One is that your expectations were wrong。

 So you thought the restaurant it was cheaper than it actually was。

 Another possibility is that there's something wrong with the data， for example。

 so it's possible that they added up the check wrong。

 maybe they charged you for something that you didn't actually eat And so you can look at the check to see if there's a problem with the data that you've collected。



![](img/666d22d07dceb91b01388b2e091a3fda_13.png)

![](img/666d22d07dceb91b01388b2e091a3fda_14.png)

So one thing to note about this example。Is that？It's kind of it was easy to know whether your expectations were matched with the data or not。

 So for example， if your expectation was that the meal would cost $30 and then it actually cost $40。

 you know immediately that your expectations were not right。

 The meal was $10 more than you actually thought it was going be。

 And so you can make that kind of conclusion very quickly。 Another possibility， for example。

 is that you could have said， well， the meal will be between 0 and 1000。

 And so when when the data actually comes in and you see the check is 40。

 that actually your expectation it actually matches your expectation which is that it's between 0 and 1000。

 But because your original expectation was so diffuse and so kind of general。

 you didn't you don't really learn that much from collecting the data。

 given your very kind of diffuse expectation。 So this brings to us to an important point。

 which is that it's important to have a very sharp expectation or a sharp。

potheis about what you're trying to investigate when I said that I expected the meal to be $30。

 it was very easy to know when my expectations were not meant。

 but if my expectation was very diffuse and not sharp at all like between 0 and 1000 then collecting the data doesn't really help you or doesn't help you learn about the process that you're trying to study or in this case the cost of the meal of this place So ultimately what we're leading towards with setting your expectations in collecting data is kind of a change in behavior or an understanding of the mechanism what you're trying to study。

 what did we learn and what would you do differently next time。

 So in the scenario where you thought it was gonna to be $30 and it ended up being $40 well。

 then the next time you might bring an extra $10 if you originally thought it was going to be between 0 and 1000 then the cost ended up being $40。

 it's not clear that you would change anything about your behavior based on this data and so so。



![](img/666d22d07dceb91b01388b2e091a3fda_16.png)

![](img/666d22d07dceb91b01388b2e091a3fda_17.png)

If there is no change in what you might think or what you might do based on the collection of the data and matching it with your expectations。

 then that's often a sign that either the evidence from your experiment is not very strong or their data analysis was not able to generate enough evidence or there may be some other problem with your study or your data analysis process。

 so setting the right expectations and making them as sharp as possible is a really key element to this whole data analysis cycle。



![](img/666d22d07dceb91b01388b2e091a3fda_19.png)