# Daniel Bourke《PyTorch 深度学习｜PyTorch 101 Crash Course For Beginners in 2025》中英字幕 - P110：110_05_014 配置GPU实验设备无关代码.zh_en - GPT中英字幕课程资源 - BV1kTSKB1E9m

![](img/8c82edd2c2d9284bcb40732168f39f03_0.png)

How'd you go。Should you give it a shot。 Did you set up some device agnostic code。

 I hope you gave it a go。 But let's do it together。 This won't take too long。

 The last two videos have been quite long。😊。

![](img/8c82edd2c2d9284bcb40732168f39f03_2.png)

![](img/8c82edd2c2d9284bcb40732168f39f03_3.png)

So if I wanted to set device agnostic code， I wanted to see if I have a GPU available。

 do I I can check it from Navidia SMI that fails because I haven't activated a GPU in Google Coab yet。

 I can also check here Torch Kuda is available。That will。

Pytorch will check if there's a GPU available with Ka and it's not。

 So let's fix these two because we want to start using a GPU and we want to set up device agnostic code。

 So no matter what hardware our system is running， Pytorch leverages it。

 So we're going select GPU here。 I'm going to click save and you'll notice that our Google coab notebook will start to reset and we'll start to connect。

 there we go， we've got a GPU on the backend， Python 3 Google Comp engine backend GPU。

 Do we have to reset this。

![](img/8c82edd2c2d9284bcb40732168f39f03_5.png)

![](img/8c82edd2c2d9284bcb40732168f39f03_6.png)

N videodia SI， wonderful。 I have a Tesla T 4 GPU with 16 GB of memory。 That is wonderful。

 And now do we have a GPU available。😊，Oh， torch is not defined。

 Will do you notice the numbers of these cells。1，2。

 that means because we've reset our run time to have a GPU。

 we have to rerun all the cells above so we can go run before。 That's gonna run all the cells above。

 make sure that we download the data。 make sure that we download the helper functions file。

 If we go back up。 We should see our data may be downloading。 It shouldn't take too long。

 That is another advantage of using a relatively small data set that is already saved on Pytoch datas。

Just keep in mind that if you use a larger data set and you have to re downloadload it into Google CoLab。

 it may take a while to run。And if you build bigger models， they may take a while to run。

 so just keep that in mind for your experiments going forward， start small， increase when necessary。

So we'll rerun this。 We'll rerun this。 And finally， we're going to， oh， there we go。

 We've got a GPPU。 wonderful， but we'll write some device agnostic code here， Se up device。

 agnostic code。😊，So import torch Now realistically you will quite often do this at the start of every notebook。

 but I just wanted to highlight how we might do it if we're in the middle and I wanted to practice running a model on a CPU only before stepping things up and going to a GPU so device equals Kuda this is for our device agnostic code if torch。

 kuda is available and it looks like this is going to return true else use the CPU。😊。

And then we're going to check device。Wonderful， couda。

So we've got some device agnostic code ready to go。 I think it's time we built another model。😊。

And I asked the question before， do you think that the data that we're working with requires linearity？

So the shirts and the bags and the shoes， do we need nonlinear functions to model this？Well。

 it looks like our baseline model without nonlinearities did pretty well at modeling our data。

 so we've got a pretty good test accuracy value， so 83% so out of 100 images it predicts the right one 83% of the time。

 83 times out of 100。 It did pretty well without nonlinearities。

 Why don't we try a model that uses nonlinearities and it runs on the GPU so you won't want to give that a go see if you can create a model with nonlinear functions。

 try Nn dot Relu run it on the GPU and see how it goes。😊，Otherwise。

 we'll do it together in the next video。

![](img/8c82edd2c2d9284bcb40732168f39f03_8.png)

See you there。