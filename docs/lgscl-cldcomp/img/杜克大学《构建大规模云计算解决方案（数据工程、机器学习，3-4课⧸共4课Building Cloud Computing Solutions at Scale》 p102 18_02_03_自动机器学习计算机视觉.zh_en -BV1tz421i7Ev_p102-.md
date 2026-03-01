# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p102 18_02_03_自动机器学习计算机视觉.zh_en -BV1tz421i7Ev_p102-

![](img/4d4ae8ba3a1603cc5b14acebb88efa32_0.png)

Let's talk through an AutoML computer vision pipeline and how it can be used to build production quality models。

 First up， you'll need your source data and this could be。

 let's say images of birds and images of dogs and let's say you have 1000 images of birds and you have 1000 images of dogs and you want to train a machine learning model that does binary classification。

And what this would do is tell you of these photos， what is the picture is it a bird as a dog。

 and in this particular situation we could upload this directly into a cloud based environment。

 it could be， for example， GCP and that could be AutoM visions。

 that's one example of this it could also be maybe your own open source solution like Ludwig is an AutoML solution that does autocomputer vision。

 it also could be potentially not even on the cloud。

It could also be your laptop and your laptop could be running maybe some software like CML from Apple and CreL can do AutoM。

 there's lots of different solutions here， but the main idea is that you only need to specify the raw data。

 have the data itself and say what kind of model you want to do in this case we would want to classify the difference between a bird or a dog and then select train and it would go through and take whatever time it needed to train the model now。

Inside of here in the cloud itself， there may be some special characteristics like for example。

 it could need a GPU and that could you increase the accuracy because there's a fixed amount of time it could run or for example。

 there could be a selection of different types of models all happening beneath the hood。

 but the general idea here is that it's it's really touchless。

 there isn't a data scientist going inside of here and tweaking the neural network。

 it really is like using Excel。 Now once that's done。

 let's say again it takes let's just say 30 minutes to train the model what happens next here。 well。

 this model is now ready to be deployed depending on the framework that used the Autom technology in the case of let's say Google Automil。

You can go through here and download a ja version of it。

 or you could potentially do a prediction directly on a hosted version in an API right so this could be on a cloudbased service or another example could be you could download this into a mobile app like in the case of iOS you could have an iOS application that directly took that model so really we're at the phase now with Autom where it's really more about the logic especially with things like computer vision which is a fairly well-known problem now as long as you know that business logic that you're trying to solve you can use an Autom solution and in fact automatically train and update this model continuously as you get more data。



![](img/4d4ae8ba3a1603cc5b14acebb88efa32_2.png)

![](img/4d4ae8ba3a1603cc5b14acebb88efa32_3.png)