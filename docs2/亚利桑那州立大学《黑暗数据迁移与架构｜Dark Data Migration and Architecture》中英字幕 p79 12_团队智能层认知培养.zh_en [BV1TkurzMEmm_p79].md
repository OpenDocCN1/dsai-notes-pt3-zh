# 亚利桑那州立大学《黑暗数据迁移与架构｜Dark Data Migration and Architecture》中英字幕 p79 12_团队智能层认知培养.zh_en [BV1TkurzMEmm_p79]

Welcome， in this lesson I'm going to take you through how to approach creating DIL's dynamic intelligence layers。



![](img/192a777e86db28e9c79aa3f3d2924dea_1.png)

Now this is one of the things you want to really think about as you move forward is that DILs are conceptual and they're dynamic in nature。

 you'd want to make sure that you focus on being able to create and spin it up as needed and create changes in adjustments to it which requires the granularity so understand that these DILs are exploratory you need to understand the data。

 understand the data patterns and take the time to understand the need right these pieces are critical so we talked about you lead。

 understand， learn you have to go through that whole process before you start developing this DIL that whole you lead process the understanding of fundamentally what the data is。

 what it means the patterns that you see the things that are not normal doing that analysis process is critical before you can really develop these DILs in a way that will allow you to experience the value that you can create and you need to understand the intended outcome right and not the intended outcome。



![](img/192a777e86db28e9c79aa3f3d2924dea_3.png)

![](img/192a777e86db28e9c79aa3f3d2924dea_4.png)

come from the standpoint of saying well we want to just we want to grow the bins。

 we want to make money， that's always going to be an outcome。

 but what is the intended of what do people expect to be able to do once you dove into the data and created more intelligence？



![](img/192a777e86db28e9c79aa3f3d2924dea_6.png)

![](img/192a777e86db28e9c79aa3f3d2924dea_7.png)

![](img/192a777e86db28e9c79aa3f3d2924dea_8.png)

Real quick， some examples of that just off the top are specifically about you know people seeing data。

 let's say if you're running an engineering organization they'll say。



![](img/192a777e86db28e9c79aa3f3d2924dea_10.png)

Do we have capacity to do the work and you have the data needed to understand engineering capacity？



![](img/192a777e86db28e9c79aa3f3d2924dea_12.png)

That type of a question means that you need to go and understand fundamentally not how many hours somebody is working。

 but what is the rate at which you complete things and how does the amount of headcount。

 plus the amount of time that it takes to build similar products。

 how does that impact the overall workflow？

![](img/192a777e86db28e9c79aa3f3d2924dea_14.png)

![](img/192a777e86db28e9c79aa3f3d2924dea_15.png)

And then you can create some numbers to answer that question of do we have capacity to do whatever project you have？



![](img/192a777e86db28e9c79aa3f3d2924dea_17.png)

Now， if you're looking at how to operate， right， so one of the things you want to think about is that the dynamic intelligence layer is at the top of this stack here。



![](img/192a777e86db28e9c79aa3f3d2924dea_19.png)

![](img/192a777e86db28e9c79aa3f3d2924dea_20.png)

It's at the very top。Everything under it is contributing to it。 Plus。

 some of the stuff that you'll create at the near top， right。

 right at the near source or right at the near user experience level。



![](img/192a777e86db28e9c79aa3f3d2924dea_22.png)

![](img/192a777e86db28e9c79aa3f3d2924dea_23.png)

So understanding the flow of the data as it gets to you。

 one of the keys understanding the timing of the data。

 so if the data that you get from a data lake or a warehouse， if that data takes a day to get there。

 the data that you receive is by default going to be one day old and if the data in the data marks before it gets to your DIL if it takes another day if it's batched every day。

 you're looking at 48 hours before you get what get the data in front of you。



![](img/192a777e86db28e9c79aa3f3d2924dea_25.png)

![](img/192a777e86db28e9c79aa3f3d2924dea_26.png)

![](img/192a777e86db28e9c79aa3f3d2924dea_27.png)

![](img/192a777e86db28e9c79aa3f3d2924dea_28.png)

So when you create these types of views in this intelligence and you're putting that dark data。

 you need to understand that so that people when they go to it。

 they know there's a lag and you know there's a lag and you're building according to it the timing is critical you also want to understand redundancy when systems are large like this。



![](img/192a777e86db28e9c79aa3f3d2924dea_30.png)

![](img/192a777e86db28e9c79aa3f3d2924dea_31.png)

![](img/192a777e86db28e9c79aa3f3d2924dea_32.png)

![](img/192a777e86db28e9c79aa3f3d2924dea_33.png)

You'll have different types of data coming in from different sources and stored all into that data lake。

 you'll want to make sure you don't copy similar data or you don't pull data that is the exact same but slightly different because it came from a different source。

 you'll need to know the source of that data so that you can decide which version of data set that you should use because the picture that you paint is going to be critical for decision making。



![](img/192a777e86db28e9c79aa3f3d2924dea_35.png)

![](img/192a777e86db28e9c79aa3f3d2924dea_36.png)

![](img/192a777e86db28e9c79aa3f3d2924dea_37.png)

![](img/192a777e86db28e9c79aa3f3d2924dea_38.png)

And lastly， when we think about indeliverables。That is what matters the most。

Did the indeliverable allow us to achieve the outcome results that we expected。

 did it meet our expectations so just going back to that picture of the diamond mind and remembering that it's not about what's hidden it's about the value that is out there that you can go attain and get and bring it back。

 right？So the indliverable should provide data products that expose dark data and solve the main question and the multiple derivatives of that question。

 so leadership comes to you with those questions and they need to know a little bit more。

 you should be able to build out the data products in the DIL， based on the dark data。

 get new dark data that you've created from what is there and provide that insight。

Thank you for your time。