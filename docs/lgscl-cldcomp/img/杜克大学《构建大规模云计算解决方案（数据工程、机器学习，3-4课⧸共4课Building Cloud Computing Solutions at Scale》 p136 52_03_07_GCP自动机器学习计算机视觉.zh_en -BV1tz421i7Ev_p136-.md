# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p136 52_03_07_GCP自动机器学习计算机视觉.zh_en -BV1tz421i7Ev_p136-

![](img/4d1b64d00b593d3705d715acfb61c722_0.png)

So GCP also has。

![](img/4d1b64d00b593d3705d715acfb61c722_2.png)

Computer vision， which is probably one of the better computer vision。

Capabilities that's out there right now for AutoL。And if you go to AutoM on GCP here。

 and there's some quick labs that you can go through that do this as well。

 what's neat about this is you can click new data set。And you can pick， for example。

 if I want to do single label classification， let's say I wanted to always just pick one thing like。

I don't know， cat or dog or whatever， and go through here。I can pick this。

I could either upload an image from the computer or select a CSV file that points to a bunch of images I put in Google Cloud St。

 so this is they're saying this exact example right is I would say I put in my bucket。A JPG file。

 and it's a cat。 and then here's my training data， and you have a bunch of training data。

 and then you also have some test data。Once you do that， it will store all the data for you。

 and then it will give you something that looks like this。 So if I go back。

I think I have to delete some of these， I have so many of these that I created。

Let me just still eat that。Let me delete some of these old ones。So if I go to this。

 this is something I did earlier。And this is the images that are uploaded。

And once I've uploaded these images， I can toggle between the filters。

 right So it's actually got a great interface for me to visualize all the data。

 And then if I click on train。What will happen is that I can train a new model。

And I have two choices I can either host it in the cloud。

 which is completely fine if you want to do predictions that accept user input。

Or you also could do edge and this is a class that I teach on this， but basic what's neat about edge。

 I'll show you both in the edge example， you can see this， the model type is edge。

If we go to test and use， you can actually download this model right here to a mobile device so I can click on this。



![](img/4d1b64d00b593d3705d715acfb61c722_4.png)

And use， let's say， Android Quickstar and train it in the cloud by just literally clicking buttons and then downloading it and deploying it to this physical device here。

 And what's nice about this is that it's very， very low code and at the very end。

 you would be using the model that you trained and put it onto your mobile device。

 So that's one of the advantages of something like AutoL。



![](img/4d1b64d00b593d3705d715acfb61c722_6.png)

The， the other option， which I had told you about。Would be in the case of。嗯。The cloud model。

 it would live in the cloud is if you say test and use， you could actually call an endpoint。

 I'm not going to do it because it'll spin up some servers。

 but but it'llll it'll serve up an endpoint。 and then I could just。

Have users put data into it like handwriting samples or whatever。

 so this is another option right is that you could try to just put INIS data or some kind of computer vision data into the cloud vision API。

Click train， it'll be pretty quick， actually， spin up an endpoint and then tell Google Append to call into that endpoint and pass a payload and then you've got a complete end to end pipeline working for a computer vision application。

So does that one make sense to everybody， is there any questions about this one？Yeah。

 so can we mimic that you。Eure and。Yeah， so if we go to let's go to， let's go to。Yeah。

 so with this one allows you to customize and train the model。



![](img/4d1b64d00b593d3705d715acfb61c722_8.png)

From scratch， and so it's your own data， which is really awesome。



![](img/4d1b64d00b593d3705d715acfb61c722_10.png)