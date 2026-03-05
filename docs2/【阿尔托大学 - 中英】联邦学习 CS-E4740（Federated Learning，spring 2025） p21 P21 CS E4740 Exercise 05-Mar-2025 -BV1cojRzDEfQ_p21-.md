# 【阿尔托大学 - 中英】联邦学习 CS-E4740（Federated Learning，spring 2025） p21 P21 CS E4740 Exercise 05-Mar-2025 -BV1cojRzDEfQ_p21-

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_0.png)

Okay， so like the previous exercise session， we will go to our own Upiter hub of Alto and other students like the outside student have already got the email from Alex。

 right？

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_2.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_3.png)

Yeah， just a moment while。Server is running。啊。没有。Sorry， just a moment。



![](img/fbdef9fe63b3e2f50aff63fcc2f57381_5.png)

Okay， so right now we will go to and big rather and then check the assignment list like here and you will see the new assignment。

List here， assignment 2。And after that， like if you guys fetch this one。

 then you' will see the assignment here， then after that like you can see the assignment and also you can go from this folder like F 2025 after that assignment too。



![](img/fbdef9fe63b3e2f50aff63fcc2f57381_7.png)

Okay， so this assignment is about F networks and the concept of this assignment is from machine learning to the federated learning。

 So right now we are seeing the learning goals like this is the learning goals of this assignment。

 We will implement a federated learning network using the Python package network X。

 we will use this package to create the graph and their ages and also we are analyze。

 we will analyze this F network with their node degree and Laplaceian metrics。 and also after that。



![](img/fbdef9fe63b3e2f50aff63fcc2f57381_9.png)

We will use some graph learning network in this federal learning network and after that we will use some kind of distance metrics like local averaging to know about this network。



![](img/fbdef9fe63b3e2f50aff63fcc2f57381_11.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_12.png)

So these are like necessary libraries and packages which we have imported here and after that there is the first task like building one pered network。

 pered learning network and there has been the instructions as given like thoroughly like you have to make one I guess two yeah you have to make two graph we using network X1 is geograph and one is a statistical graph and here some preprocessed data like the random seed and how will be the station data has been encoded already。

 like the latitude will be within 60 to 65 and the longitude will be 284 to 30 and these values has already been discussed here like which value what will be the values。



![](img/fbdef9fe63b3e2f50aff63fcc2f57381_14.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_15.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_16.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_17.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_18.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_19.png)

And after that， the temperature mean and temperature standard deviation。



![](img/fbdef9fe63b3e2f50aff63fcc2f57381_21.png)

And after that like here is the like initialization of graph。

 but you have to implement some code like how we live inside those nodes or like simulate the data set of those00 temperature values here so here you have to complete it and then if you run this you will see。



![](img/fbdef9fe63b3e2f50aff63fcc2f57381_23.png)

And two graph will create and after the sative check like if it's passed then。You will。

 you can like understand that the two graphs has been created。



![](img/fbdef9fe63b3e2f50aff63fcc2f57381_25.png)

And after creating the graph we will create some ages of these networks and since there were two graphs here。

 one is geograph and one is statistical graph or sta graph so we will use some conditions here like here is the behavior。

 like if method is geo in this function like constructing ages。

 then you have to like use this coordinates using latitude and longitude and if you use if the path function parameter is sta then you have to use that temperature mean and temperature standard deviation。



![](img/fbdef9fe63b3e2f50aff63fcc2f57381_27.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_28.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_29.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_30.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_31.png)

So after that， you here， you will construct ages。 and there are some subtasks here。

 Like here is for geo。 and here is for sta。 And this is the like。

Creating the neighbors node like the five。 You have to take five closest node with。



![](img/fbdef9fe63b3e2f50aff63fcc2f57381_33.png)

With an age distance as late。After that， if you run this function， then the ages will be created。

 and after that， the federated learning。 and after that。

 you can see the plots from here like you will see there two similar plots。

 like the nodeds will be similar or I can say symmetric。

 but the ages will be different because one age is based on geological properties and another age is based on statistical properties。

 So that's why like the nodeds will be same， but the ages will be different for the networks。



![](img/fbdef9fe63b3e2f50aff63fcc2f57381_35.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_36.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_37.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_38.png)

And after then the third task is to analyze the connectivity like you will you have to compute leplian matrix here and after that you have to compute the second smallest eigenvalue like here and the eigenvectors and if you just。

Compute these values then you will see a graph like here analyzing graph and you will see two graphs like how the ages and the node are how much connected and what is the value of their connectivity and after that you can see a simple like algorithm of this network like local averaging。

 like except prediction here between the neighboring data like neighboring data level temperatures of each nodes。



![](img/fbdef9fe63b3e2f50aff63fcc2f57381_40.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_41.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_42.png)

So for this， you just have to like prediction error here。

 like here is a dictionary of prediction error， but you have to like create the differences。

 like calculate the differences like a hair is already been instructed。

 like you have to take the prediction temperature of the node。

 but if any node has no neighbors you have to take them in but it is a rare case because like almost every node has neighbors because already in the upper field here。

 maybe there is a just a moment。

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_44.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_45.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_46.png)

Maybe yeah， here is like determined managed five neighbor neighbors。

 That means every node must have five neighbors。 So if every node must have five neighbors。

 then that case is very rare。 but it's just because so that you guys know that if。



![](img/fbdef9fe63b3e2f50aff63fcc2f57381_48.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_49.png)

Anywhere in a project or any kind of experiment if there is no neighbor so what should you do so just for that backup but nothing more or nothing less so and after that you will you will see and after that just when you see the differences you will see the local averaging differences of the nodes and。



![](img/fbdef9fe63b3e2f50aff63fcc2f57381_51.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_52.png)

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_53.png)

That's all for this assignment， I guess this one is a bit shorter than the previous one。 So I hope。

 but it's a new thing like this fedated learning network and network X thing。

 So I hope you guys will like。Like it this assignment a lot。So this is from my end。

 so do you guys have any kind of question on these assignments or tasks or anything or like this assignment has already been shared yesterday。

 so have you guys faced any kind of problem in this assignment or anything。

You guys can't ask anything， so no worries。Let me just screen off my sharing。G I'm just呃。

Sitching off my screen just a moment。我的你。Yeah， sure。 does anyone have any question。いかなし。

So the whole purpose here is to build the fer learning network from scratch without using any inbu libraries like F or TFF is that correct yes。

 something like that we are just using one package like network X， but that's on before the graph so。

We are not using any other libraries or any kind of packages。Okay。

So would we be using them as well in future assembly？Yeah that maybe we will use it or maybe not。

 but it depends on the assignment requirements and other things。

 so let's see how it goes with the next assignments。

And I will not be here for next assignments like Boseng。

 the other teaching assistant will be will take the next two assignments and after that Alexander he will take the other two assignments like assignment five and seats。

 so maybe that time you can see those like packages or maybe or maybe not， so let's see。Thank you。

Okay， so does anyone have any kind of question？

![](img/fbdef9fe63b3e2f50aff63fcc2f57381_55.png)