# 杜克大学｜机器学习运维｜DevOps⧸DataOps、Azure、MLFlow和抱脸｜MLOps ｜ Machine Learning Operations p189 48_04_05_将Hugging-Face模型导出为ONNX格式.zh_en -BV1yE421c7uA_p189-

![](img/a0ebda7c93eb68bb8f36aa6b80f82584_0.png)

Now let's do a little bit of a handson experimentation here with hugging face and Onyx and when I look at exporting the exporting Jupyter notebook that I have here already running again make sure that you have the right kernel installed in this case I'm using the one that is from Conda that has all of the dependencies installed All right so first off let's find the features in this case you're going to import the features module from the Onyx library here on the Transers。

 Onyx module rather and you' going import a features manager and then for these specifically for these example specifically when I be doing with distilled bird and when I look at what those what those features are and I'll tell you in a second why that is important so let's it's connecting to the kernel this is going to take a second and well wait it out until that complete So right so this completed。

One are the features， Well， this model has different things。

 different tasks that you can do so you can have sequence classification， for example。

 multiple choice， token classification or question answering which is something that I really enjoy working with models that do question answering All right so why is this important。

 Why would you need to understand that if you know exactly what you need and have a model that is doing something very specific。

 then for example， question answering。 then you can say well。

 I want to port over distbi model to onyx just to do question answering and the way you accomplish that is by again working with the transformers that onx module acid commandline tool and you can pass in Python M transformer onyx actually let's just walk through some of these things that you will need to know for the first you're going to be using transformers onyx again you're using the module as a commandline tool because of the dash and flag right here。

Next were going to pass in the model like exactly what's the model youre want to be working with in this case is going to be that the Silbi base oncase finet SST2 English well that that's a mouthful。

 but that is exactly the model that we want to working with and then we're going to say the feature that we want is the question answering。

And lastly， and this is kind of hard to see here。 We have a dot Now this dot is pretty important because it means that we want to produce the model right here in this same directory。

 if we wanted something else we could do something like a path and then the name to the model that we want to I just want to generate that right there。

 So that is going to allow us to generate that so I'm going to run this is going to take a few seconds and it's going to start producing producing output So now right now downloading the stillber based case fine tune model So let's scroll through the output and see what's going on here what you need to look for at the end is specifically the model model validation So you can see here all good model saved and model that onx if I would have passed in a path you would have in something slightly different or if I wanted a different name and you can see here the model output names these are the ones that you will be needing to work with。

 So if I go back。Back to the Exper， you can see now the Exper is saying， hey。

 you have something going on here and that's our model that has been produced right here。

 the model that onyx which is exactly this one coming from right there so there you go that is how you would like let me scroll here all the way to the top you would find the features in this case we're producing one for question answering and this is how you would work with hugging phase in coordination with Onx to port models from from hugging phase over to Onyx and produce a working model for Onyx。



![](img/a0ebda7c93eb68bb8f36aa6b80f82584_2.png)