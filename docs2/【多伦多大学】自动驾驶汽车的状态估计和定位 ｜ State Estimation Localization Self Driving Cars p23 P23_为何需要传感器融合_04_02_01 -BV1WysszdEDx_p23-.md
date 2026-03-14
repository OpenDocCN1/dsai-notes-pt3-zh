# 【多伦多大学】自动驾驶汽车的状态估计和定位 ｜ State Estimation Localization Self Driving Cars p23 P23_为何需要传感器融合_04_02_01 -BV1WysszdEDx_p23-

![](img/45ce90073b9b4669b1e67a060d80ce26_0.png)

So we've agreed now that state estimation is kind of important。😊。

And I yoga by assertion that it's hard because you have this data association and the data is complex。

 And so the next question comes， well， how can you make life a bit easier for yourself。

 What should you do maybe we should say instead of using one sensor type， we should use many。

 So maybe we could get rid of the confusion between corner of building and corner of bus from laser by using a camera as well。

 Because buses look different normally to the corners of buildings。

 So then we're using two modality So we're getting the appearance from a camera in the form of what color the pixels are And we're getting meters and geometry from the bus on how far away stuff is。

 And so you might find that gets a lot easier。 And then we might say。

 oh but you know if I had a Doppler radar， I could measure how fast it's going as well。

 So now I've got a rate。 I've got its appearance。 I've got its shape。 and maybe。

could use a gyro and an accelerometer and I might know something about the rate of change of my own state。

 Fastic。 And now I want to feed all of those into my state estimation。

 so I want to use all of those different sensor streams to do a better job at figuring out where I am and what's around me in what those third-party entities are doing so you should absolutely do that。

 in fact I might argue it would be pretty daft to use just one modality because you will find an environment that's pathological to that one modality。

 So say I was using a laser and I went into a completely flat area with no change in reflection and it was huge that would be pretty difficult to use a laser in or harder than if it's in a closed cramped environment and if I'm using just a camera and the lights go out completely that might be hard as well。

 So you know a combination of these sensors seems to be the clever way to do it。

 And then the art of a good AV engineer and a good algorithms engineer in the space is someone who goes。

😊，I think I can write down an optimization problem perhaps。

 that uses all of those sensor streams and says， if I could only find the minimum of this function。

That explains all of the sensor data that I'm seeing。

 I'd have a great idea about where I am and what my state is。😊。

But then you need to do that in the context of all of those confusing conflicting data association problems that you have as well。

 so you get data association around the outside and state estimation and then you sort of roll around on themselves so it gets richer on every question。

But still remains important， still remains hard。Still remains exciting。



![](img/45ce90073b9b4669b1e67a060d80ce26_2.png)