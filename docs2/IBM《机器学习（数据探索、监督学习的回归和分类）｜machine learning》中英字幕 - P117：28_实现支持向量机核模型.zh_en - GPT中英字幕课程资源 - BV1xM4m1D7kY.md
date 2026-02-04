# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P117：28_实现支持向量机核模型.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

So how do we do this， what's the code to actually perform the nitroroom or the RBF sampler to come up with an approximate for this higher dimensional space？



![](img/f443b8657d8dc12b6691807f9af07549_1.png)

![](img/f443b8657d8dc12b6691807f9af07549_2.png)

The first thing that we're going to want to do as we always do， is import that class。

 so we're going to import NYhu from SKlearn。 kernelnel approximation。



![](img/f443b8657d8dc12b6691807f9af07549_4.png)

![](img/f443b8657d8dc12b6691807f9af07549_5.png)

We're then going to create an instance of the class we initiate that class calling Ntrom as well as the different hyperparameters。

 different kernels can be used as multiple nonlinearar kernels such as RBF。

 we talked about polynomial and you can look at the documentation for any more you may be interested in。



![](img/f443b8657d8dc12b6691807f9af07549_7.png)

![](img/f443b8657d8dc12b6691807f9af07549_8.png)

![](img/f443b8657d8dc12b6691807f9af07549_9.png)

![](img/f443b8657d8dc12b6691807f9af07549_10.png)

The kernel and gamma that we have here are going to be identical to those that we saw for the SVC model。



![](img/f443b8657d8dc12b6691807f9af07549_12.png)

![](img/f443b8657d8dc12b6691807f9af07549_13.png)

And then we have this argument end components and that's just going to be the number of samples that are used in order to come up with our kernel approximation so as we discussed generally speaking that kernel approximation will come from every single one of our different data points instead we say just sample 100 of those data points so that's going to be the end components the smaller that is the less components is sampling from the more you use the longer it'll take。

 the closer it'll be to an approximation of the whole data set。



![](img/f443b8657d8dc12b6691807f9af07549_15.png)

![](img/f443b8657d8dc12b6691807f9af07549_16.png)

![](img/f443b8657d8dc12b6691807f9af07549_17.png)

![](img/f443b8657d8dc12b6691807f9af07549_18.png)

![](img/f443b8657d8dc12b6691807f9af07549_19.png)

![](img/f443b8657d8dc12b6691807f9af07549_20.png)

We're then going to fit the instance on the data as we've done before。

 but this time we're doing a fit transform， so we're only passing in our one data set our X and we're calling fit transform on the X train。



![](img/f443b8657d8dc12b6691807f9af07549_22.png)

![](img/f443b8657d8dc12b6691807f9af07549_23.png)

Because the Xtrain needs to be fit and transformed using the fit from Xtrain。

 and we're going to be mapping it up to that higher dimensional space。



![](img/f443b8657d8dc12b6691807f9af07549_25.png)

![](img/f443b8657d8dc12b6691807f9af07549_26.png)

And then for the X test， we have to assume that we don't have that holdout set。



![](img/f443b8657d8dc12b6691807f9af07549_28.png)

So we can only use the fit that was。

![](img/f443b8657d8dc12b6691807f9af07549_30.png)

Learn from our Xtrain so as we discuss with the standard Scalar。

 this will be the same idea where we use the values that we learn from Xtrain in order to transform our X test。

 so we just call the transform using that fit from Xtrain in order to transform our X test。



![](img/f443b8657d8dc12b6691807f9af07549_32.png)

![](img/f443b8657d8dc12b6691807f9af07549_33.png)

![](img/f443b8657d8dc12b6691807f9af07549_34.png)

![](img/f443b8657d8dc12b6691807f9af07549_35.png)

And then we can again tune our kernel on the associated parameters using cross validationation。

 and here we'd probably want to in practice， create a pipeline as we discussed in earlier courses so that we can later use something like grid search CV to run through different hyperparameters for our transformer here so we'd run through all the hyperparameters for the transformer and within that pipeline we'd also have some type of linear classifier and we can see for the holdoutset which one performed best。



![](img/f443b8657d8dc12b6691807f9af07549_37.png)

![](img/f443b8657d8dc12b6691807f9af07549_38.png)

![](img/f443b8657d8dc12b6691807f9af07549_39.png)

![](img/f443b8657d8dc12b6691807f9af07549_40.png)

![](img/f443b8657d8dc12b6691807f9af07549_41.png)

![](img/f443b8657d8dc12b6691807f9af07549_42.png)

Another kernel approximation method is the RBF sampler， so again from SKLar。 kernel approximation。

 we import the RBF sampler this time。

![](img/f443b8657d8dc12b6691807f9af07549_44.png)

![](img/f443b8657d8dc12b6691807f9af07549_45.png)

We're then going to again create an instance of our class。

 initiate that class of a RBF sampler calling it RBF sample。



![](img/f443b8657d8dc12b6691807f9af07549_47.png)

![](img/f443b8657d8dc12b6691807f9af07549_48.png)

And for this for the RBF sampler， RBF is going to be the only kernel that can be used。

 so this will be specific to RBF。

![](img/f443b8657d8dc12b6691807f9af07549_50.png)

![](img/f443b8657d8dc12b6691807f9af07549_51.png)

And the parameter names are again going to be identical to what we just discussed in regards to the gamma and the number of components。



![](img/f443b8657d8dc12b6691807f9af07549_53.png)

![](img/f443b8657d8dc12b6691807f9af07549_54.png)

We're then going to fit the instance on the data and transform。

 so again this is the same exact method that we just discussed where you onfi transform on our X train and then just transform on our X test。



![](img/f443b8657d8dc12b6691807f9af07549_56.png)

![](img/f443b8657d8dc12b6691807f9af07549_57.png)

And again， we can tune the kernel parameters and components using cross validation， again。

 probably wanting to do a pipeline where we have both this RBF sampler as well as some type of linear classifier。



![](img/f443b8657d8dc12b6691807f9af07549_59.png)

![](img/f443b8657d8dc12b6691807f9af07549_60.png)

![](img/f443b8657d8dc12b6691807f9af07549_61.png)